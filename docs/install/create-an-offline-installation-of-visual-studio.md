---
title: Vytvoření offline instalace
description: Zjistěte, jak v režimu offline instalace sady Visual Studio, když máte nespolehlivým připojení k Internetu nebo s malou šířkou pásma.
ms.date: 10/22/2019
ms.custom: seodec18
ms.topic: conceptual
f1_keywords:
- offline installation [Visual Studio]
- offline install [Visual Studio]
- layout [Visual Studio]
ms.assetid: f8625d5e-f6ea-4db0-83c0-619b77fab3cf
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: fd47e464eec0fc9bdbd20c854432f5954f8fbcb2
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/01/2020
ms.locfileid: "75591486"
---
# <a name="create-an-offline-installation-of-visual-studio"></a>Vytvoření offline instalace sady Visual Studio

::: moniker range="vs-2017"

Jsme navrhovali Visual Studio 2017, aby dobře fungovaly v různých konfiguracích sítě a počítače. Přestože doporučujeme vám vyzkoušet [webovou Instalační službu sady Visual Studio](https://visualstudio.microsoft.com/vs/older-downloads)&mdash;což je malý soubor a umožňuje aktuální nejnovější opravy a funkce&mdash;rozumí tomu, že nemusí být možné.

::: moniker-end

::: moniker range="vs-2019"

Navrhli jsme sadu Visual Studio 2019, aby dobře fungovala v nejrůznějších konfiguracích sítě a počítačů. Přestože doporučujeme vám vyzkoušet [webovou Instalační službu sady Visual Studio](https://visualstudio.microsoft.com/downloads)&mdash;což je malý soubor a umožňuje aktuální nejnovější opravy a funkce&mdash;rozumí tomu, že nemusí být možné.

::: moniker-end

Například může mít nespolehlivé připojení k Internetu nebo, pokud má s malou šířkou pásma. Pokud ano, máte několik možností: můžete použít novou "Vše stáhnout, potom nainstalovat" funkcí ke stažení souborů, před instalací nebo příkazového řádku můžete vytvořit místní mezipaměť souborů.

> [!NOTE]
> Pokud jste podnikovým správcem, který chce provést nasazení sady Visual Studio do sítě klientských pracovních stanic, které jsou brány firewall z Internetu, přečtěte si článek [Vytvoření síťové instalace sady Visual Studio](../install/create-a-network-installation-of-visual-studio.md) a [nainstalujte certifikáty vyžadované pro instalační stránky systému Visual Studio pro offline instalaci](../install/install-certificates-for-visual-studio-offline.md) .

## <a name="use-the-download-all-then-install-feature"></a>Používá "vše stáhnout, potom nainstalovat" funkce

::: moniker range="vs-2017"

[**Novinka ve verzi 15,8**](/visualstudio/releasenotes/vs2017-relnotes-v15.8#install): po stažení webového instalačního programu vyberte možnost nový **Stáhnout vše a pak** z instalační program pro Visual Studio nainstalujte. Pokračujte s instalací.

   !["Vše stáhnout, potom nainstalovat" možnost](media/download-all-then-install.png)

::: moniker-end

::: moniker range="vs-2019"

Po stažení webového instalačního programu vyberte možnost nové **Stáhnout vše a pak** z instalační program pro Visual Studio nainstalovat. Pokračujte s instalací.

   !["Vše stáhnout, potom nainstalovat" možnost](media/vs-2019/download-all-then-install-from-installer.png)

::: moniker-end

Navrhli jsme funkci stáhnout vše a pak nainstalovat, abyste mohli Visual Studio stáhnout jako jednu instalaci pro stejný počítač, na který jste ho stáhli. Tímto způsobem se můžete bezpečně odpojit od webu před instalací sady Visual Studio.

> [!IMPORTANT]
> Nepoužívejte funkci stáhnout vše a potom nainstalovat a vytvořte offline mezipaměť, kterou chcete přenést do jiného počítače. Tento postup není navržený tak, aby fungoval. <br><br>Pokud chcete vytvořit offline mezipaměť pro instalaci sady Visual Studio na jiném počítači, přečtěte si část [použití příkazového řádku k vytvoření místní mezipaměti](#use-the-command-line-to-create-a-local-cache) na této stránce, kde najdete informace o tom, jak vytvořit místní mezipaměť, nebo na stránce [vytvořit síťovou instalaci sady Visual Studio](../install/create-a-network-installation-of-visual-studio.md) , kde najdete informace o tom, jak vytvořit síťovou mezipaměť.

## <a name="use-the-command-line-to-create-a-local-cache"></a>Místní mezipaměť vytvořit pomocí příkazového řádku

Po stažení malé zaváděcí nástroj, použijte příkazový řádek k vytvoření místní mezipaměti. Potom použijte místní mezipaměti instalace sady Visual Studio. (Tento proces nahradí soubory ISO, které byly k dispozici pro předchozí verze).

Tady je způsob.

### <a name="step-1---download-the-visual-studio-bootstrapper"></a>Krok 1 – stažení zaváděcího nástroje Visual Studio

Musíte mít internetové připojení k dokončení tohoto kroku.

::: moniker range="vs-2017"

Další informace o tom, jak to udělat, najdete na stránce pro stažení [předchozích verzí sady Visual Studio](https://visualstudio.microsoft.com/vs/older-downloads/) , kde můžete získat zaváděcí nástroj pro visual Studio 2017.

Spustitelný soubor instalace&mdash;nebo má být konkrétnější,&mdash;souboru zaváděcího nástroje by se měla shodovat s jedním z následujících způsobů.

| Edice | Název souboru |
|-------------|-----------------------|
|Visual Studio Community | vs_community.exe |
|Visual Studio Professional | vs_professional.exe |
|Visual Studio Enterprise | vs_enterprise.exe |
|Visual Studio Build Tools   | vs_buildtools. exe |

::: moniker-end

::: moniker range="vs-2019"

Začněte tím, že stažení zaváděcího nástroje Visual Studio pro vaši zvolenou edici sady Visual Studio. Váš soubor&mdash;nebo zaváděcí nástroj&mdash;bude odpovídat nebo se podobně jako na jednu z následujících akcí.

| Edice                    | Soubor                                                                    |
|----------------------------|-------------------------------------------------------------------------|
| Visual Studio Community    | [vs_community.exe](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=community&rel=16&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=offline+install&utm_content=download+vs2019)       |
| Visual Studio Professional | [vs_professional.exe](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=professional&rel=16&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=offline+install&utm_content=download+vs2019) |
| Visual Studio Enterprise   | [vs_enterprise.exe](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=enterprise&rel=16&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=offline+install&utm_content=download+vs2019)     |
| Visual Studio Build Tools   | [vs_buildtools. exe](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=buildtools&rel=16&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=offline+install&utm_content=download+vs2019)     |

::: moniker-end

>[!TIP]
>Pokud jste dříve stáhli soubor zaváděcího nástroje a chcete ověřit jeho verzi, tady je postup. V systému Windows otevřete Průzkumníka souborů, klikněte pravým tlačítkem na soubor zaváděcího nástroje, zvolte **vlastnosti**, klikněte na kartu **Podrobnosti** a pak zobrazte číslo **verze produktu** . Chcete-li toto číslo porovnat s vydáním sady Visual Studio, přejděte na stránku [čísla sestavení sady Visual Studio a data verzí](visual-studio-build-numbers-and-release-dates.md) .

### <a name="step-2---create-a-local-install-cache"></a>Krok 2: vytvoření mezipaměti místní instalace

Musíte mít internetové připojení k dokončení tohoto kroku.

> [!IMPORTANT]
> Pokud nainstalujete Visual Studio Community, musíte ho aktivovat do 30 dnů od instalace. To vyžaduje připojení k Internetu.

Otevřete příkazový řádek a použijte jeden z příkazů z následujících příkladů. Příklady, které jsou zde uvedeny předpokládají, že používáte komunitní edice sady Visual Studio; Upravte příkaz v závislosti na edici.

> [!TIP]
> Aby se zabránilo chybě, ujistěte se, že úplná cesta k instalaci je kratší než 80 znaků.

- Vývoj desktopových aplikací .NET a webové rozhraní .NET spusťte:

   ```cmd
    vs_community.exe --layout c:\vslayout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US
    ```

- Vývoj pro Office a .NET desktop spusťte:

   ```cmd
    vs_community.exe --layout c:\vslayout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.Office --includeOptional --lang en-US
    ```

- Vývoje desktopových aplikací C++ pro spuštění:

   ```cmd
    vs_community.exe --layout c:\vslayout --add Microsoft.VisualStudio.Workload.NativeDesktop --includeRecommended --lang en-US
    ```

- Vytvoření kompletní místní rozložení se všemi funkcemi (bude to trvat dlouho&mdash;máme _velké_ funkcí!), spusťte:

   ```cmd
    vs_community.exe --layout c:\vslayout --lang en-US
    ```

::: moniker range="vs-2017"

   > [!NOTE]
   > Kompletní rozložení sady Visual Studio vyžaduje minimálně 35 GB místa na disku. Další informace najdete v tématu [požadavky na systém](/visualstudio/productinfo/vs2017-system-requirements-vs/). A informace o tom, jak vytvořit rozložení pouze s komponentami, které chcete nainstalovat, naleznete v tématu [použití parametrů příkazového řádku pro instalaci sady Visual Studio](use-command-line-parameters-to-install-visual-studio.md).

::: moniker-end

::: moniker range="vs-2019"

   > [!NOTE]
   > Kompletní rozložení sady Visual Studio vyžaduje minimálně 35 GB místa na disku. Další informace najdete v tématu [požadavky na systém](/visualstudio/releases/2019/system-requirements/). A informace o tom, jak vytvořit rozložení pouze s komponentami, které chcete nainstalovat, naleznete v tématu [použití parametrů příkazového řádku pro instalaci sady Visual Studio](use-command-line-parameters-to-install-visual-studio.md).

::: moniker-end

Pokud chcete nainstalovat jiný jazyk než angličtinu, změňte `en-US` národní prostředí z [seznam národních prostředí jazyka](#list-of-language-locales). Potom použijte [seznamu komponent a úlohy, které jsou k dispozici](workload-and-component-ids.md) můžete dále přizpůsobit vaše mezipaměť instalace.

### <a name="step-3---install-visual-studio-from-the-local-cache"></a>Krok 3: instalace sady Visual Studio z místní mezipaměti

> [!TIP]
> Při spuštění z mezipaměti místní instalace instalační program používal místní verze každý z těchto souborů. Ale pokud vyberete součásti během instalace, které nejsou v mezipaměti, instalační program se pokusí stáhnout z Internetu.

::: moniker range="vs-2019"
> [!IMPORTANT]
> V případě instalace offline se zobrazí chybová zpráva s informacemi o tom, že produkt odpovídající následujícím parametrům nebyl nalezen, ujistěte se, že používáte přepínač `--noweb` s verzí 16.3.5 nebo novější.
>
::: moniker-end

Chcete-li mít jistotu, že můžete nainstalovat pouze soubory, které jste předtím stáhli, použijte stejné možnosti příkazového řádku, které jste použili k vytvoření mezipaměti rozložení. Například, pokud jste vytvořili mezipaměť rozložení pomocí následujícího příkazu:

```cmd
vs_community.exe --layout c:\vslayout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US
```

Spuštění instalace pak použijte tento příkaz:

```cmd
c:\vslayout\vs_community.exe --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional
```

Další příklady použití [parametrů příkazového řádku](use-command-line-parameters-to-install-visual-studio.md)naleznete na stránce s [Příklady parametrů příkazového řádku pro instalaci sady Visual Studio](command-line-parameter-examples.md) . 

> [!NOTE]
> Pokud dojde k chybě, podpis je neplatný, je nutné nainstalovat aktualizace certifikátů. Otevřete složku pro certifikáty v offline mezipaměti. Klikněte dvakrát na každém ze souborů certifikátu a klikněte na Průvodce správce certifikátů. Pokud budete vyzváni k zadání hesla, ponechte prázdné.

### <a name="list-of-language-locales"></a>Seznam národních prostředí jazyka

| **Jazyk národního prostředí** | **Jazyk** |
| ----------------------- | --------------- |
| cs-CZ | Čeština |
| de-DE | Němčina |
| en-US | angličtina |
| es-ES | Španělština |
| fr-FR | Francouzština |
| IT-IT | Italština |
| ja-JP | Japonština |
| ko-KR | Korejština |
| pl-PL | Polština |
| pt-BR | Portugalština – Brazílie |
| ru-RU | Ruština |
| tr-TR | Turečtina |
| zh-CN | Čínština (zjednodušená) |
| zh-TW | Čínština (tradiční) |

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

- [Vytvoření síťové instalace sady Visual Studio](../install/create-a-network-installation-of-visual-studio.md)
- [Aktualizace síťové instalace sady Visual Studio](update-a-network-installation-of-visual-studio.md)
- [Instalace certifikátů vyžadovaných pro offline instalace sady Visual Studio](../install/install-certificates-for-visual-studio-offline.md)
- [Instalace sady Visual Studio s použitím parametrů příkazového řádku](use-command-line-parameters-to-install-visual-studio.md)
- [ID úloh a komponent sady Visual Studio](workload-and-component-ids.md)
