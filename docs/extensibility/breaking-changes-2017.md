---
title: Rozbíjející změny v rozšíření sady Visual Studio 2017
titleSuffix: ''
ms.date: 11/09/2016
ms.topic: conceptual
ms.assetid: 54d5af60-0b44-4ae1-aa57-45aa03f89f3d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
monikerRange: vs-2017
ms.openlocfilehash: e7363a0779721e4fb36106d6ee77324c341517ba
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62926832"
---
# <a name="changes-in-visual-studio-2017-extensibility"></a>Změny v rozšíření sady Visual Studio 2017

Poskytuje Visual Studio 2017 [rychlejší, nenáročný prostředí instalace sady Visual Studio](https://devblogs.microsoft.com/visualstudio/faster-leaner-visual-studio-installer) , která snižuje dopad sady Visual Studio v systémech uživatelů současně uživatelům poskytuje větší výběr úloh a funkcí, které jsou nainstalovat. Pro podporu těchto vylepšení jsme udělali změny model rozšiřitelnosti, včetně odstraňuje některé narušující změny. Tento článek popisuje technické podrobnosti o tyto změny a co se dá dělat k jejich řešení.

> [!NOTE]
> Některé informace se podrobnosti implementace v daném okamžiku a může být později změnit.

## <a name="changes-affecting-vsix-format-and-installation"></a>Změny, které mají vliv formát VSIX a instalace

Zavedená VSIX v. 3 sady Visual Studio 2017 (verze 3) formát pro podporu prostředí odlehčenou instalaci.

Změny formátu VSIX patří:

* Prohlášení o požadovaných součástí instalace. K doručování na příslib odlehčený, rychlý instalace sady Visual Studio, instalační program teď nabízí další možnosti konfigurace pro uživatele. Kvůli tomu aby se zajistilo, že jsou nainstalované funkce a součásti vyžadované pro rozšíření, rozšíření potřeba deklarovat jejich závislosti.

  * Instalační program sady Visual Studio 2017 nabízí automaticky chcete získat a nainstalovat komponenty potřebné pro daného uživatele jako součást instalace příslušného rozšíření.
  * Uživatelé se také zobrazí upozornění při pokusu o instalaci rozšíření, které nebylo vytvořené pomocí nového formátu VSIX v3, i když bylo označeno ve svém manifestu jako cílení na verzi 15.0.

* Vylepšené funkce pro formát VSIX. Dodržujeme [nízkým dopadem instalace](https://devblogs.microsoft.com/visualstudio/anatomy-of-a-low-impact-visual-studio-install) sady Visual Studio, která podporuje také nainstaluje vedle sebe, už většina konfigurační data uložit do registru systému jsme přesunuli Visual Studio konkrétní sestavení z mezipaměti GAC. Také jsme zvýšili funkce formát VSIX a instalace modulu VSIX, abyste mohli používat ho místo MSI nebo EXE instalace rozšíření pro některé typy instalace.

Mezi nové schopnosti patří:

* Registrace do zadané instance sady Visual Studio.
* Instalace mimo [složku rozšíření](set-install-root.md).
* Zjišťování na architektuře procesoru.
* Závislost na oddělené jazyk jazykových sad.
* Instalace s [podpora technologie NGEN](ngen-support.md).

## <a name="build-an-extension-for-visual-studio-2017"></a>Sestavení rozšíření pro Visual Studio 2017

Návrhářské nástroje pro vytváření nového formát manifestu VSIX v3 je k dispozici v sadě Visual Studio 2017. Zobrazit související dokument [jak: Migrace projektů rozšíření do sady Visual Studio 2017](how-to-migrate-extensibility-projects-to-visual-studio-2017.md) podrobnosti o použití návrhářské nástroje nebo provádění ruční aktualizací do projektu a manifest pro vývoj rozšíření VSIX v3.

## <a name="change-visual-studio-user-data-path"></a>Změna: Visual Studio cesta k datům uživatele

Dříve může existovat pouze jedna instalace každá hlavní verze produktu Visual Studio na každém počítači. Pro podporu-souběžnými instalacemi sady Visual Studio 2017, může existovat více cesty k datům uživatelů pro sadu Visual Studio na počítači uživatele.

Chcete-li použít nastavení správce sady Visual Studio se musí aktualizovat kód spuštěný v procesu sady Visual Studio. Kód spuštěný mimo proces sady Visual Studio můžete najít cestu uživatele konkrétní instalaci sady Visual Studio [podle pokynů tady](locating-visual-studio.md).

## <a name="change-global-assembly-cache-gac"></a>Změna: Globální mezipaměť sestavení (GAC)

Většina základních sestavení sady Visual Studio jsou již nainstalovány do mezipaměti GAC. Byly provedeny následující změny tak, aby kód spuštěný v procesu sady Visual Studio, stále můžete najít požadovaná sestavení za běhu.

> [!NOTE]
> [INSTALLDIR] tady odkazuje na kořenový adresář instalace sady Visual Studio. *VSIXInstaller.exe* se to automaticky vyplní, ale k psaní kódu, vlastní nasazení, přečtěte si prosím [vyhledání sady Visual Studio](locating-visual-studio.md).

* Sestavení, které byly nainstalovány pouze do GAC:

   Tato sestavení jsou teď nainstalované v adresáři <em>[INSTALLDIR] \Common7\IDE\*, * [INSTALLDIR] \Common7\IDE\PublicAssemblies</em> nebo *[INSTALLDIR] \Common7\IDE\PrivateAssemblies*. Tyto složky jsou součástí definovaných cest proces sady Visual Studio.

* Sestavení, které byly nainstalovány do cesty – testování a do mezipaměti GAC:

   * Kopie v mezipaměti GAC byl odebrán z instalačního programu.
   * A *.pkgdef* soubor se přidal k určení základní záznam kódu pro sestavení.

      Příklad:

      ```xml
      [$RootKey$\RuntimeConfiguration\dependentAssembly\codeBase\{UniqueGUID}]
      "name"="AssemblyName" "codeBase"="$PackageFolder$\AssemblyName.dll"
      "publicKeyToken"="Public Key Token"
      "culture"="neutral"
      "version"=15.0.0.0
      ```

      Za běhu, subsystému pkgdef sady Visual Studio slučuje tyto položky do konfigurační soubor procesu Visual Studio modulu runtime (v části *[VSAPPDATA]\devenv.exe.config*) jako [ `<codeBase>` ](/dotnet/framework/configure-apps/file-schema/runtime/codebase-element) elementy. Toto je doporučeným způsobem, jak umožnit proces sady Visual Studio najít sestavení, protože se eliminuje prohledávat zjišťování cesty.

### <a name="reacting-to-this-breaking-change"></a>Reakce na tento zásadní změna

* Pokud v rámci procesu Visual Studio běží vaše rozšíření:

   * Váš kód bude moct vyhledat sestavení sady Visual Studio core.
   * Zvažte použití *.pkgdef* soubor v případě potřeby zadejte cestu k sestavení.

* Pokud vaše rozšíření běží mimo proces sady Visual Studio:

   Vezměte v úvahu hledáte Visual Studio core sestavení v rámci <em>[INSTALLDIR] \Common7\IDE\*, * [INSTALLDIR] \Common7\IDE\PublicAssemblies</em> nebo *[INSTALLDIR] \Common7\IDE\PrivateAssemblies*použitím překladač konfigurační soubor nebo sestavení.

## <a name="change-reduce-registry-impact"></a>Změna: Dopad registru

### <a name="global-com-registration"></a>Globální registrace modelu COM

* Dříve nainstalované sady Visual Studio do HKEY_CLASSES_ROOT a HKEY_LOCAL_MACHINE podregistry pro podporu nativních registrace modelu COM mnoho klíče registru. Chcete-li odstranit tento dopad, Visual Studio nyní používá [Bezregistrační aktivace komponent COM](https://msdn.microsoft.com/library/ms973913.aspx).
* V důsledku toho většina vyrovnávací paměti TLB / OLB / knihovny DLL v části % ProgramFiles (x86) %\Common Files\Microsoft Shared\MSEnv nebudou nainstalované ve výchozím nastavení sada Visual Studio. Tyto soubory jsou teď nainstalované v [INSTALLDIR] s odpovídající manifesty COM bez registrace používá hostitelský proces sady Visual Studio.
* V důsledku toho najdete externí kód, který využívá globální registrace modelu COM pro rozhraní Visual Studio COM už tyto registrace. Kód spuštěný v procesu sady Visual Studio se nezobrazí rozdíl.

### <a name="visual-studio-registry"></a>Visual Studio registru

* Dříve nainstalované sady Visual Studio mnoho klíče registru do systému **HKEY_LOCAL_MACHINE** a **HKEY_CURRENT_USER** podregistry v rámci Visual Studio konkrétní klíče:

  * **HKLM\Software\Microsoft\VisualStudio\{Version}**: Klíče registru vytvořené pomocí Instalační služby MSI a rozšíření vázaná na počítač.
  * **HKCU\Software\Microsoft\VisualStudio\{Version}**: Klíče registru vytvořené pomocí sady Visual Studio k ukládání nastavení specifických pro uživatele.
  * **HKCU\Software\Microsoft\VisualStudio\{Version}_Config**: Kopii aplikace Visual Studio HKLM klávesy výše a klíče registru sloučením *.pkgdef* souborů podle přípony.

* Pokud chcete snížit dopad na registru, Visual Studio nyní používá [RegLoadAppKey](/windows/desktop/api/winreg/nf-winreg-regloadappkeya) funkce pro ukládání klíčů registru v privátní binárního souboru v rámci *[VSAPPDATA]\privateregistry.bin*. Velmi malý počet Visual Studio zkratky specifické pro zůstat v systémovém registru.
* Stávající kód spuštěný v procesu sady Visual Studio to neovlivní. Visual Studio přesměruje do privátního registru, všechny operace registru pod klíčem konkrétní HKCU Visual Studio. Čtení a zápis do jiných umístění registru bude nadále používat systémového registru.
* Externí kód bude potřebovat k načtení a čtení z tohoto souboru pro položky registru sady Visual Studio.

### <a name="react-to-this-breaking-change"></a>Reakce na tento zásadní změna

* Pro účely Bezregistrační aktivace komponent COM také mají být převedeny externí kód.
* Externí komponenty můžete vyhledat umístění sady Visual Studio [podle pokynů tady](https://devblogs.microsoft.com/setup/changes-to-visual-studio-15-setup).
* Doporučujeme použít externí komponenty [externí prostřednictvím Správce nastavení](/dotnet/api/microsoft.visualstudio.settings.externalsettingsmanager) místo čtení/zápis přímo na klíče registru sady Visual Studio.
* Zkontrolujte, jestli komponenty, které používá vaše rozšíření může implementovat další techniku pro registraci. Rozšíření ladicího programu může být například moct využívat nové [msvsmon registrace modelu COM soubor JSON](migrate-debugger-COM-registration.md).
