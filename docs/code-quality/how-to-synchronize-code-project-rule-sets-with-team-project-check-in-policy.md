---
title: "Postupy: synchronizace sady pravidel projektu kódu s týmového projektu vrácení se změnami zásad | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.selecttfsruleset
ms.assetid: 9b02f934-2db6-41ec-aaff-9c31ceec2f04
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: de3a7bfaccec45dc6b7fce1def45a6e6de8e75f2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-synchronize-code-project-rule-sets-with-team-project-check-in-policy"></a>Postupy: Synchronizace sady pravidel projektu kódu se zásadou vracení se změnami týmového projektu
Můžete synchronizovat nastavení analýzy kódu pro kód projekty zásad vrácení se změnami pro týmový projekt tak, že zadáte sadu pravidel, která obsahuje alespoň pravidla, která jsou zadaná v pravidle nastavení zásad vrácení se změnami. Vaše vývojáře realizace může informovat o název a umístění pravidla pro nastavení zásady vrácení se změnami. Chcete-li zajistit, aby používal analýzy kódu pro projekt správnou sadu pravidel, můžete použít jednu z následujících možností:  
  
-   Pokud zásad vrácení se změnami používá jednu z sady předdefinovaných pravidel Microsoft, otevřete dialogové okno Vlastnosti projektu kódu, zobrazit stránku Analýza kódu a vyberte pravidlo, nastavte na stránce nastavení projektu kódu analýza kódu. Microsoft sady standardních pravidel jsou automaticky nainstalovány pomocí sady Visual Studio jsou nastaveny na jen pro čtení a by neměla být upravována. Pokud nejsou upravovat sady pravidel, je zaručeno pravidla v zásady a sady pravidel místní, tak, aby odpovídaly.  
  
-   Pokud zásad vrácení se změnami používá vlastní sady pravidel, proveďte operaci get na soubor sady pravidel ve správě verzí vytvořit místní kopii. Potom zadejte tohoto místní umístění do nastavení analýzy kódu pro kód projektu. Pravidla je zaručeno splněno, pokud sada pravidel pro zásad vrácení se změnami je aktuální.  
  
     Pokud namapujete verze umístění ovládacího prvku do místní složky, který je ve stejné relaci do kořenového adresáře projektu team jako projektu kódu, umístění pravidlo nastavené pomocí relativní cesty. Relativní cesta zajistí, že nastavení projektu kódu pro analýzu kódu je možné přesouvat na jiné počítače.  
  
-   Upravte kopii pravidlo pro nastavení zásady vrácení se změnami pro projekt kódu. Ujistěte se, zda je sada pravidel pro nové obsahuje všechna pravidla v zásad vrácení se změnami a ostatní pravidla, které chcete zahrnout. Musí se ujistěte, že vaše sada pravidel obsahuje všechna pravidla v pravidle nastavení zásad vrácení se změnami.  
  
### <a name="to-specify-a-microsoft-standard-rule-set"></a>Chcete-li určit standardní pravidla Microsoft nastavit  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt kódu a pak klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte na tlačítko **analýza kódu**.  
  
3.  V **spuštění této sady pravidel** klikněte na sadu pravidel zásad vrácení se změnami.  
  
### <a name="to-specify-a-custom-check-in-policy-rule-set"></a>Chcete-li určit sadu pravidel vlastních zásad vrácení se změnami  
  
1.  V případě potřeby proveďte operaci get na soubor sadu pravidel, který určuje zásad vrácení se změnami.  
  
2.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt kódu a pak klikněte na tlačítko **vlastnosti**.  
  
3.  Klikněte na tlačítko **analýza kódu**.  
  
4.  V **spuštění této sady pravidel** seznamu, klikněte na tlačítko  **\<Procházet... >**.  
  
5.  V **otevřete** dialogovém okně zadejte soubor nastavit pravidlo zásad vrácení se změnami.  
  
### <a name="to-create-a-custom-rule-set-for-a-code-project"></a>Chcete-li vytvořit vlastní pravidlo nastavte pro projekt kódu  
  
1.  Postupujte podle jednoho z postupů dříve v tomto tématu, vyberte pomocí zásad vrácení se změnami týmového projektu na stránce Analýza kódu v dialogovém okně nastavení projektu.  
  
2.  Klikněte na tlačítko **otevřete**.  
  
3.  Přidat nebo odebrat pravidla pomocí editoru sadu pravidel.  
  
     Další informace najdete v tématu [vytváření vlastní sady pravidel](../code-quality/creating-custom-code-analysis-rule-sets.md).  
  
4.  Uložte upravený pravidlo nastaven na soubor analýza v místním počítači nebo na cestu UNC.  
  
5.  Otevřete dialogové okno Vlastnosti pro projekt kódu a zobrazení **analýza kódu** stránky.  
  
6.  V **spuštění této sady pravidel** seznamu, klikněte na tlačítko  **\<Procházet... >**.  
  
7.  V **otevřete** dialogovém okně zadejte soubor sady pravidel.