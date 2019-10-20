---
title: Událost před sestavením – dialogové okno Příkazový řádek události po sestavení | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- cs.ProjectPropertiesBuildEventsBuilder
- vb.ProjectPropertiesBuildEventsBuilder
helpviewer_keywords:
- $(SolutionExt)
- $(ProjectDir)
- $(TargetPath)
- $(ProjectExt)
- $(TargetFileName)
- $(PlatformName)
- $(SolutionName)
- macros, build events
- $(SolutionPath)
- $(ProjectPath)
- $(ProjectFileName)
- $(DevEnvDir)
- $(TargetName)
- $(TargetDir)
- $(SolutionDir)
- $(TargetExt)
- $(OutDir)
- $(ConfigurationName)
- $(SolutionFileName)
- $(ProjectName)
- build events, macros
ms.assetid: d49b2c57-24bf-4fb2-8351-5c4b6cca938f
caps.latest.revision: 17
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: b42c219620a669a8fa27a7ce847dc571a4075288
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72662170"
---
# <a name="pre-build-eventpost-build-event-command-line-dialog-box"></a>Dialogové okno Příkazový řádek události před sestavením/po sestavení
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Můžete zadat události před nebo po sestavení pro [stránku události sestavení, Návrhář projektuC#()](../../ide/reference/build-events-page-project-designer-csharp.md) přímo v poli pro úpravy nebo můžete vybrat možnost makra před a po sestavení ze seznamu dostupných maker.

> [!NOTE]
> Události před sestavením se nespustí, pokud je projekt aktuální a není spuštěno žádné sestavení.

## <a name="ui-element-list"></a>Seznam prvků uživatelského rozhraní
 **Textové pole příkazového řádku** Obsahuje události pro spuštění před sestavením nebo po sestavení.

> [!NOTE]
> Přidejte příkaz `call` před všechny příkazy po sestavení, které spouštějí soubory. bat. Například `call C:\MyFile.bat` nebo `call C:\MyFile.bat call C:\MyFile2.bat`.

 **Makra** Rozbalí pole pro úpravy a zobrazí seznam maker, která se mají vložit do příkazového řádku pro úpravy.

 **Tabulka maker** Vypíše dostupná makra a její hodnotu. Popis každého najdete v tématu makra níže. V případě, že chcete vložit do textového pole příkazového řádku, můžete vybrat pouze jedno makro.

 **Vložit** Vloží do příkazového řádku textové pole makro vybrané v tabulce maker.

### <a name="macros"></a>Makra
 Pomocí kterékoli z těchto maker můžete určit umístění souborů nebo získat skutečný název vstupního souboru v případě vícenásobného výběru. U těchto maker nejsou rozlišována velká a malá písmena.

|Podokně|Popis|
|-----------|-----------------|
|`$(ConfigurationName)`|Název aktuální konfigurace projektu, například "ladit".|
|`$(OutDir)`|Cesta k adresáři výstupního souboru, relativní vzhledem k adresáři projektu. Tím se přeloží hodnota vlastnosti výstupní adresář. Obsahuje koncové zpětné lomítko ' \\ '.|
|`$(DevEnvDir)`|Instalační adresář aplikace Visual Studio (definovaný s jednotkou a cestou); obsahuje koncové zpětné lomítko ' \\ '.|
|`$(PlatformName)`|Název aktuálně cílené platformy. Například "AnyCPU".|
|`$(ProjectDir)`|Adresář projektu (definovaný s jednotkou a cestou); obsahuje koncové zpětné lomítko ' \\ '.|
|`$(ProjectPath)`|Absolutní cesta k názvu projektu (definovaná s jednotkou, cestou, základním názvem a příponou souboru).|
|`$(ProjectName)`|Základní název projektu|
|`$(ProjectFileName)`|Název souboru projektu (definovaný s názvem základní a příponou souboru)|
|`$(ProjectExt)`|Přípona souboru projektu. Obsahuje znak "." před příponou souboru.|
|`$(SolutionDir)`|Adresář řešení (definovaný s jednotkou a cestou); obsahuje koncové zpětné lomítko ' \\ '.|
|`$(SolutionPath)`|Absolutní cesta k názvu řešení (definovaného pomocí jednotky, cesty, základního názvu a přípony souboru).|
|`$(SolutionName)`|Základní název řešení|
|`$(SolutionFileName)`|Název souboru řešení (definovaného základním názvem a příponou souboru).|
|`$(SolutionExt)`|Přípona souboru řešení. Obsahuje znak "." před příponou souboru.|
|`$(TargetDir)`|Adresář primárního výstupního souboru pro sestavení (definovaný s jednotkou a cestou). Obsahuje koncové zpětné lomítko ' \\ '.|
|`$(TargetPath)`|Absolutní cesta k primárnímu výstupnímu souboru pro sestavení (definovaného s jednotkou, cestou, základním názvem a příponou souboru).|
|`$(TargetName)`|Základní název primárního výstupního souboru pro sestavení.|
|`$(TargetFileName)`|Název souboru primárního výstupního souboru pro sestavení (definované jako základní název a Přípona souboru).|
|`$(TargetExt)`|Přípona souboru primárního výstupního souboru pro sestavení. Obsahuje znak "." před příponou souboru.|

## <a name="see-also"></a>Viz také
 [Určení vlastních událostí sestavení na](../../ide/specifying-custom-build-events-in-visual-studio.md) [stránce události sestavení sady Visual Studio, Návrháře projektuC#()](../../ide/reference/build-events-page-project-designer-csharp.md) [Postupy: určení událostí sestavení (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md) [Postupy: určení událostí sestavení (C#)](../../ide/how-to-specify-build-events-csharp.md)
