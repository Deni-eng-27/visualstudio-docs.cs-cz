---
title: "Použití sad pravidel k seskupování pravidel analýzy kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.rulesets.learnmore
helpviewer_keywords: code analysis, rule sets
ms.assetid: ed0f3a2a-1516-42e2-92de-b8986dc75d42
caps.latest.revision: "36"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 44d64b7371f1b27afaa7796dc42d4b7864d20819
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="using-rule-sets-to-group-code-analysis-rules"></a>Použití sad pravidel k seskupování pravidel analýzy kódu
Když konfigurujete analýza kódu v [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], nebo [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)], můžete ze seznamu předdefinovaných Microsoft *sad pravidel*. Sada pravidel je logické seskupení pravidel analýzy kódu, která vyhledávají cílené problémy a zvláštní podmínky. Například můžete použít sadu pravidel, která je určená pro hledání kódu veřejně dostupné rozhraní API, nebo můžete použít sadu pravidel, která obsahuje jenom Minimální doporučená pravidla. Můžete také použít sadu pravidel, která zahrnuje všechna pravidla.  
  
 Můžete upravit pravidlo nastavit přidání nebo odstranění pravidla nebo změnou pravidla se objeví v **seznam chyb** okno jako varování nebo chyby. Sada vlastních pravidel může splnit potřebu konkrétního vývojového prostředí. Při přizpůsobování sady vlastních pravidel poskytuje stránka sady pravidel nástroje pro vyhledávání a filtrování, které vám s tím pomohou.  
  
## <a name="common-tasks"></a>Obecné úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Získání praktické zkušenosti:** pomocí nástrojů pro analýzu kódu k určení vlastního pravidla nastavenou najít a opravit problémy v jednoduchou aplikaci pro rozhraní .NET Framework.|-   [Návod: Konfigurace a používání vlastní sady pravidel](../code-quality/walkthrough-configuring-and-using-a-custom-rule-set.md)|  
|**Konfigurace analýzy kódu pro projekt:** zvolit existující pravidlo pro projekt, webu nebo řešení.|-   [Postupy: Konfigurace analýzy kódu pro spravovaný projekt kódu](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)<br />-   [Použití sad pravidel k určování pravidel C++ pro spuštění](../code-quality/using-rule-sets-to-specify-the-cpp-rules-to-run.md)<br />-   [Postupy: Konfigurace analýzy kódu pro webovou aplikaci ASP.NET](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md)<br />-   [Postupy: určení sad pravidel pro více projektů v určitém řešení](../code-quality/how-to-specify-managed-code-rule-sets-for-multiple-projects-in-a-solution.md)|  
|**Přizpůsobit sadu pravidel:** zadejte pravidla, která platí pro váš projekt.|-   [Vytváření vlastních sad pravidel](../code-quality/creating-custom-code-analysis-rule-sets.md)|  
|**Pochopení sady předdefinovaných pravidel:** zobrazení pravidel analýzy kódu, které tvoří sady předdefinovaných pravidel.|-   [Referenční dokumentace sady pravidel nástroje Analýza kódu](../code-quality/code-analysis-rule-set-reference.md)|  
|**Analýza kódu integraci se sadou Team Foundation Server:** [!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)] vrácení se změnami zásady umožňují vývojové týmy a ujistěte se, že splňují všechny kód vrácení se změnami společnou sadu standardy analýzy kódu.|-   [Postupy: synchronizace sady pravidel projektu kódu zásadám týmového projektu vrácení se změnami](../code-quality/how-to-synchronize-code-project-rule-sets-with-team-project-check-in-policy.md)|