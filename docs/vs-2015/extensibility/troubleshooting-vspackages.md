---
title: Řešení potíží s rozšířením VSPackages | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: troubleshooting
helpviewer_keywords:
- VSPackages, troubleshooting
- debugging, VSPackages
ms.assetid: 274673e7-72e7-476f-a263-3411b5b874be
caps.latest.revision: 23
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: eda92d27781ec26fd33cfd82d18257015b494236
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63430130"
---
# <a name="troubleshooting-vspackages"></a>Řešení potíží s rozšířením VSPackages
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tady jsou běžné problémy, které může mít s vaší VSPackage a tipy pro řešení problémů.  
  
### <a name="to-troubleshoot-a-vspackage-that-keeps-visual-studio-from-starting"></a>Řešení potíží s VSPackage, která zajišťuje spuštění sady Visual Studio  
  
- Spustit [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] v nouzovém režimu.  
  
     Chcete-li spustit [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] v nouzovém režimu, na příkazovém řádku, zadejte **/safemode devenv.exe**.  
  
     Během tohoto procesu jsou načteny žádné balíčky VSPackages, s výjimkou rozšíření VSPackages, které jsou součástí [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
### <a name="to-troubleshoot-a-vspackage-that-does-not-load"></a>Řešení potíží s VSPackage, která se nenačte  
  
1. Ujistěte se, že používáte kořenový klíč registru, ve které je zaregistrovaný sady VSPackage ke spuštění, obvykle kořenový klíč registru experimentální.  
  
     Další informace najdete v tématu [experimentální instanci](../extensibility/the-experimental-instance.md).  
  
2. Pokud sady VSPackage cílí na spouštění v kořenovém adresáři registru experimentální, ujistěte se, že spustíte experimentální verzi [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
     Chcete-li spustit experimentální verzi, zadejte následující příkaz v příkazovém okně: **devenv /rootsuffix exp**.  
  
3. Zkontrolujte položky registru VSPackage.  
  
     Další informace najdete v tématu [registrace rozšíření VSPackages](internals/registering-vspackages.md) a [Správa balíčky VSPackages](../extensibility/managing-vspackages.md).  
  
4. Otevřít **výstup** okno instance [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , které se nedaří načíst sady VSPackage. Informace o proč sady VSPackage nedaří se načíst může být zobrazen v tomto okně.  
  
    > [!NOTE]
    > Pokud začínáte experimentální verzi [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] z [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] integrované vývojové prostředí (IDE), zkontrolujte **výstup** okno obě verze.  
  
5. Vyhledejte v protokolu aktivit.  
  
     Další informace najdete v tématu [jak: Použití protokolu aktivit](../extensibility/how-to-use-the-activity-log.md).  
  
6. Další informace o výjimky vyvolané z integrovaného vývojového prostředí, klikněte na tlačítko **výjimky** na **ladění** nabídka umožňující výjimky. V **výjimky** dialogové okno Vybrat typy výjimek, které chcete získat další informace.  
  
### <a name="to-troubleshoot-a-vspackage-that-does-not-register"></a>Řešení potíží s VSPackage, která nezaregistruje  
  
1. Ujistěte se, že VSPackage sestavení se nachází v důvěryhodném umístění. RegPkg nejde zaregistrovat sestavení v částečně důvěryhodných nebo nedůvěryhodných umístění, například sdílené síťové složky ve výchozí konfiguraci zabezpečení rozhraní .net. I když se upozornění zobrazí vždycky, když uživatel vytvoří projekt v nedůvěryhodném umístění, můžete toto upozornění nevyskytla zabránit zaškrtávací políčko "tuto zprávu znovu nezobrazovat".  
  
### <a name="to-troubleshoot-a-command-that-is-not-visible-or-that-generates-an-error-when-you-click-a-command"></a>Řešení potíží s příkaz, který není viditelný, nebo po kliknutí na příkaz, který generuje chybu  
  
1. Sloučit příkazy nabídky nové nebo změněné. ti se již v integrovaném vývojovém prostředí pomocí následujícího příkazu na [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] příkazového řádku: **/rootsuffix devenv/Setup Exp**.  
  
2. Ujistěte se, že [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] UI.dll vyhledat vašeho balíčku VSPackage.  
  
    1. Identifikátor CLSID sady VSPackage najdete v části balíčků z registru:  
  
         HKLM\Software\Microsoft\Visual Studio\\*\<version>* \Packages  
  
    2. Ověřte správnost cesty Dal podklíč SatelliteDll.  
  
### <a name="to-troubleshoot-a-vspackage-that-behaves-unexpectedly"></a>Řešení potíží s, který se chová neočekávaně VSPackage  
  
1. Nastavte zarážky v kódu.  
  
     Dobrým výchozím bodem pro ladění jsou konstruktor a inicializační metoda. Můžete také nastavit zarážky v oblasti, kterou chcete vyhodnotit, například příkaz nabídky. Pokud chcete povolit zarážky, je nutné spustit v ladicím programu.  
  
    1. Na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
    2. Na **stránky vlastností** dialogové okno, vyberte **ladění** kartu.  
  
    3. V **argumenty příkazového řádku** zadejte příponu kořenové vývojového prostředí, které vaše cíle VSPackage. Pokud chcete vybrat experimentální sestavení, zadejte například: **RootSuffix Exp**.  
  
    4. Na **ladění** nabídky, klikněte na tlačítko **spustit ladění** nebo stiskněte klávesu F5.  
  
        > [!NOTE]
        > Když provádíte ladění projektu, vytvořit nebo načíst existující instanci projektu nyní.  
  
2. Použití protokolu aktivit.  
  
     Sledujte chování balíčku VSPackage pomocí zápisu informací do protokolu aktivit se zapsaly klíčové body. Tato technika je užitečná při spuštění v prostředí maloobchodu VSPackage. Další informace najdete v tématu [jak: Použití protokolu aktivit](../extensibility/how-to-use-the-activity-log.md).  
  
3. Použití veřejných symbolů.  
  
     Aby se zlepšila čitelnost při ladění, můžete připojit symboly v ladicím programu.  
  
    1. Z **Nástroje/možnosti** nabídky, přejděte **ladění/symboly** dialogové okno.  
  
    2. Přidejte tuto **Symbol umístění souboru souborů (.pdb)**:  
  
         [http://msdl.microsoft.com/download/symbols](http://msdl.microsoft.com/download/symbols)  
  
    3. Ke zlepšení výkonu, zadejte složku mezipaměti symbolů, například:  
  
        ```  
        C:\symbols  
        ```  
  
### <a name="to-troubleshoot-a-missing-vspackage-or-one-of-its-dependencies"></a>Řešení potíží s chybějící VSPackage nebo některá z jeho závislostí  
  
1. Pro spravovaný kód Ujistěte se, že cesty odkazů jsou správné.  
  
   1. Na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
   2. Vyberte **odkazy** kartu **stránky vlastností** dialogové okno a ujistěte se, že všechny cesty mají správný. Alternativně můžete použít **prohlížeče objektů** a vyhledejte odkazované objekty.  
  
        Pro spravovaný kód, můžete použít [Fuslogvw.exe (Assembly Binding Log Viewer)](http://msdn.microsoft.com/library/e32fa443-0778-4cc3-bf36-5c8ea297d296) zobrazíte podrobnosti o načtení sestavení se nezdařilo.  
  
2. Nespravovaný kód, najít identifikátor CLSID VSPackage v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] uzlu registru CLSID:  
  
    HKLM\Software\Microsoft\Visual Studio\\*\<version>* \CLSID  
  
   Ujistěte se, že položka InprocServer32 má správnou cestu knihovny dll balíčku VSPackage.  
  
## <a name="see-also"></a>Viz také  
 [Balíčky VSPackage](../extensibility/internals/vspackages.md)
