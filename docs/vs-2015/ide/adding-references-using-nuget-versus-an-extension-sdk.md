---
title: Přidání odkazů pomocí NuGet oproti rozšíření SDK | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.toolsoptionspages.nuget_package_manager.general
- vs.toolsoptionspages.nuget_package_manager.package_sources
ms.assetid: 2175581e-83cb-444c-bb52-cc1fca8ea196
caps.latest.revision: 24
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 95927385ce3218d73ba6b94819429163178bb65b
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "75917337"
---
# <a name="adding-references-using-nuget-versus-an-extension-sdk"></a>Přidání odkazů pomocí nástroje NuGet a sady Extension SDK
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Balíček pro spotřebu v rámci projektů aplikace Visual Studio můžete poskytnout pomocí rozšíření NuGet pro sadu Visual Studio nebo sady SDK (Software Development Kit). Popisem podobností a rozdílů mezi těmito dvěma mechanismy vám toto téma může pomáhat při výběru nejlepšího z nich pro vaši úlohu.

- NuGet je open source systém pro správu balíčků, který zjednodušuje proces začleňování knihoven do řešení projektu. Další informace najdete v tématu [Přehled NuGet](/nuget/what-is-nuget).

- Sada SDK je kolekce souborů, které Visual Studio považuje za položku s jedinou referencí. Dialogové okno **Správce odkazů** obsahuje seznam všech sad SDK, které jsou relevantní pro projekt, který je otevřený při zobrazení tohoto dialogového okna. Když přidáte sadu SDK do projektu, můžete ke všem obsahem této sady SDK přistupovat prostřednictvím technologie IntelliSense, **sady nástrojů**, návrháře, **Prohlížeč objektů**, MSBuild, nasazení, ladění a balení. Další informace o sadách SDK naleznete v tématu [Creating a Software Development Kit](../extensibility/creating-a-software-development-kit.md).

## <a name="which-mechanism-should-i-use"></a>Který mechanismus mám použít?
 Následující tabulka vám pomůže porovnat referenční funkce sady SDK s referenčními funkcemi NuGet.

|Příznak|Podpora sady SDK|Poznámky k sadě SDK|Podpora NuGet|Poznámky k NuGetu|
|-------------|-----------------|---------------|-------------------|-----------------|
|Mechanismus odkazuje na jednu entitu a všechny soubory a funkce jsou k dispozici.|Y|Sadu SDK můžete přidat pomocí dialogového okna **Správce odkazů** a všechny soubory a funkce jsou k dispozici během vývojového pracovního postupu.|Y||
|Nástroj MSBuild automaticky spotřebovává sestavení a soubory metadat Windows (. winmd).|Y|Odkazy v sadě SDK jsou automaticky předány kompilátoru.|Y||
|Nástroj MSBuild automaticky spotřebovává soubory. h nebo. lib.|Y|Soubor *SDKName*. props oznamuje sadě Visual Studio, jak nastavit adresář Visual C++ a tak dále pro automatickou spotřebu souborů. h nebo. lib.|N||
|Nástroj MSBuild automaticky spotřebovává soubory. js nebo. CSS.|Y|V **Průzkumník řešení**můžete rozbalit referenční uzel sady JavaScript SDK pro zobrazení individuálních souborů. js nebo. potom je možné vygenerovat `<source include/>` značky přetažením těchto souborů do zdrojových souborů. Sada SDK podporuje F5 a automatickou instalaci balíčků.|Y||
|Nástroj MSBuild automaticky přidá ovládací prvek do **panelu nástrojů**.|Y|**Sada nástrojů** může využívat sady SDK a zobrazovat ovládací prvky na kartách, které zadáte.|N||
|Mechanismus podporuje Instalační program pro Visual Studio pro rozšíření (VSIX).|Y|VSIX má speciální manifest a logiku pro vytváření balíčků sady SDK.|Y|VSIX lze vložit do jiného instalačního programu.|
|**Prohlížeč objektů** výčtu odkazů.|Y|**Prohlížeč objektů** automaticky získá seznam odkazů v sadách SDK a vytvoří jejich výčet.|N||
|Soubory a odkazy se automaticky přidají do dialogového okna **Správce odkazů** (odkazy Nápověda a automaticky naplní se tak dál).|Y|V dialogovém okně **Správce odkazů** se automaticky vyčíslují sady SDK společně s odkazy na Help a seznamem závislostí SDK.|N|NuGet poskytuje vlastní dialogové okno **Spravovat balíčky NuGet** .|
|Mechanismus podporuje více architektur.|Y|Sady SDK mohou dodávat více konfigurací. Nástroj MSBuild využívá příslušné soubory pro každou konfiguraci projektu.|N||
|Mechanismus podporuje více konfigurací.|Y|Sady SDK mohou dodávat více konfigurací. V závislosti na architektuře projektu nástroj MSBuild spotřebovává příslušné soubory pro každou architekturu projektu.|N||
|Mechanismus může určovat "ne pro kopírování".|Y|V závislosti na tom, jestli jsou soubory vyřazené ve složce \redist nebo \designtime, můžete určit, které soubory se mají zkopírovat do balíčku náročné aplikace.|N|Deklarujete, které soubory se mají zkopírovat v manifestu balíčku.|
|Obsah se zobrazí v lokalizovaných souborech.|Y|Lokalizované dokumenty XML v sadách SDK jsou automaticky zahrnuty pro lepší prostředí pro dobu návrhu.|N||
|Nástroj MSBuild podporuje současně více verzí sady SDK.|Y|Sada SDK podporuje současné využívání více verzí současně.|N|Neodkazuje se na. V projektu nemůžete mít více než jednu verzi souborů NuGet.|
|Mechanismus podporuje určení příslušných cílových rozhraní, verzí sady Visual Studio a typů projektů.|Y|Dialogové okno **Správce odkazů** a **panel nástrojů** zobrazují pouze sady SDK, které se vztahují k projektu, takže uživatelé mohou snadněji zvolit příslušné sady SDK.|Y (částečně)|Pivot je cílová architektura. Neexistuje žádné filtrování na uživatelském rozhraní. V době instalace může vrátit chybu.|
|Mechanismus podporuje určení registračních informací pro nativní soubory WinMD.|Y|Můžete zadat korelaci mezi souborem. winmd a souborem. dll v SDKManifest.xml.|N||
|Mechanismus podporuje určení závislostí na jiných sadách SDK.|Y|Sada SDK upozorní uživatele pouze na to, uživatel je musí pořád nainstalovat a odkazovat na ně ručně.|Y|NuGet je automaticky vyžádá; uživatel není upozorněn.|
|Mechanismus se integruje s  [!INCLUDE[win8_appstore_long](../includes/win8-appstore-long-md.md)] Koncepty, jako je manifest aplikace a ID rozhraní.|Y|Sada SDK musí předat koncepty specifické pro, [!INCLUDE[win8_appstore_short](../includes/win8-appstore-short-md.md)] aby balíčky a F5 správně fungovaly se sadami SDK, které jsou k dispozici v nástroji [!INCLUDE[win8_appstore_short](../includes/win8-appstore-short-md.md)] .|N||
|Mechanismus se integruje s kanálem ladění aplikace pro [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)] aplikace.|Y|Sada SDK musí předávat [!INCLUDE[win8_appstore_short](../includes/win8-appstore-short-md.md)] konkrétní koncepce, aby balíčky a F5 správně pracovaly se sadami SDK dostupnými v nástroji [!INCLUDE[win8_appstore_short](../includes/win8-appstore-short-md.md)] .|Y|Obsah NuGet se stal součástí projektu. Nevyžaduje se žádný zvláštní aspekt F5.|
|Mechanismus se integruje s manifesty aplikací.|Y|Sada SDK musí předávat [!INCLUDE[win8_appstore_short](../includes/win8-appstore-short-md.md)] konkrétní koncepce, aby balíčky a F5 správně pracovaly se sadami SDK dostupnými v nástroji [!INCLUDE[win8_appstore_short](../includes/win8-appstore-short-md.md)] .|Y|Obsah NuGet se stal součástí projektu. Nevyžaduje se žádný zvláštní aspekt F5.|
|Mechanismus nasadí nereferenční soubory (například nasazení testovacího rozhraní, na kterém se mají spouštět testy [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)] aplikací).|Y|Pokud soubory odstraníte ve složce \redist, soubory se automaticky nasadí.|Y||
|Mechanismus automaticky přidá sady SDK platformy v integrovaném vývojovém prostředí sady Visual Studio.|Y|Pokud [!INCLUDE[win8](../includes/win8-md.md)] sadu SDK nebo sadu Windows Phone SDK z konkrétního umístění vyřadíte pomocí konkrétního rozložení, sada SDK se automaticky integruje se všemi funkcemi sady Visual Studio.|N||
|Mechanismus podporuje čistý vývojový počítač. (To znamená, že není nutná žádná instalace a jednoduché načtení ze správy zdrojového kódu bude fungovat.)|N|Vzhledem k tomu, že odkazujete na sadu SDK, je nutné vrátit se změnami řešení a sadu SDK samostatně. Sadu SDK můžete vrátit se změnami ze dvou výchozích umístění, ze kterých nástroj MSBuild prochází sady SDK (podrobnosti najdete v tématu [Vytvoření sady Software Development Kit](../extensibility/creating-a-software-development-kit.md)). Alternativně, pokud se vlastní umístění skládá ze sad SDK, můžete zadat následující kód v souboru projektu:<br /><br /> `<PropertyGroup>    <SDKReferenceDirectoryRoot>C:\MySDKs</SDKReferenceDirectoryRoot>   </PropertyGroup>`<br /><br /> Pak zkontrolujte sady SDK do tohoto umístění.|Y|Můžete se podívat na řešení a Visual Studio okamžitě rozpoznává a funguje na souborech.|
|Můžete se připojit k velkému stávajícímu komunitnímu tvůrci balíčků.|–|Komunita je nová.|Y||
|Můžete se připojit k velkému stávajícímu komunitě uživatelů balíčku.|–|Komunita je nová.|Y||
|Můžete se připojit k ekosystému partnerů (vlastní galerie, úložiště a tak dále).|–|Mezi dostupná úložiště patří galerie sady Visual Studio, Microsoft Download Center a [!INCLUDE[win8_appstore_long](../includes/win8-appstore-long-md.md)] .|Y||
|Mechanismus se integruje se servery sestavení průběžné integrace pro vytváření a spotřebu balíčku.|Y|Sada SDK musí předat umístění vráceného se změnami (vlastnost SDKReferenceDirectoryRoot) na příkazovém řádku do nástroje MSBuild.|Y||
|Mechanismus podporuje jak stabilní, tak i předběžné verze balíčků.|Y|Sada SDK podporuje přidávání odkazů na více verzí.|Y||
|Mechanismus podporuje automatické aktualizace nainstalovaných balíčků.|Y|Pokud je dodán jako VSIX nebo součást automatických aktualizací sady Visual Studio, poskytuje sada SDK automatická oznámení.|Y||
|Mechanismus obsahuje samostatný soubor. exe pro vytváření a využívání balíčků.|Y|Sada SDK obsahuje MSBuild.exe.|Y||
|Balíčky lze vrátit se změnami do řízení verze.|Y|Nemůžete vrátit cokoli mimo uzel dokumenty, což znamená, že sady SDK rozšíření nemusí být vráceny se změnami. Velikost sady SDK rozšíření může být velká.|Y||
|K vytváření a využívání balíčků můžete použít rozhraní PowerShellu.|Y (spotřeba), N (vytváření)|Žádné nástroje pro vytvoření sady SDK. Spotřeba spouští nástroj MSBuild na příkazovém řádku.|Y||
|Pro podporu ladění můžete použít balíček symbolů.|Y|Při vyřazení souborů. pdb v sadě SDK se soubory automaticky vybírají.|Y||
|Mechanismus podporuje automatické aktualizace správce balíčků.|–|Sada SDK se bude revidována pomocí nástroje MSBuild.|Y||
|Mechanismus podporuje odlehčený formát manifestu.|Y|SDKManifest.xml podporuje mnoho atributů, ale je obvykle zapotřebí malá podmnožina.|Y||
|Mechanismus je k dispozici pro všechny edice sady Visual Studio.|Y|Sada SDK podporuje všechny edice sady Visual Studio od Visual Studio Express až po [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)] .|Y|NuGet podporuje všechny edice sady Visual Studio, které se vyjadřují až [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)] .|
|Mechanismus je k dispozici pro všechny typy projektů.|N|Sada SDK podporuje [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)] aplikace, které začínají na [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)] .|N|Můžete zkontrolovat seznam povolených projektů.|

## <a name="see-also"></a>Viz také
 [Správa odkazů v projektu](../ide/managing-references-in-a-project.md)
