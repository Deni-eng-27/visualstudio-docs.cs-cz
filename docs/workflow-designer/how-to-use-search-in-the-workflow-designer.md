---
title: "Postupy: použití hledání v Návrháři pracovních postupů | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: f42d3115-2ed2-4941-8f1e-92dac41c30fa
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 0ab8fe2ca639dd4660dfbabc8c5497f4ab0b3487
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-use-search-in-the-workflow-designer"></a>Postupy: použití hledání v Návrháři pracovních postupů
Usnadňuje vytváření rozsáhlejších, složitějších pracovních postupů vyhledávání můžete použít v Návrháři pracovních postupů k vyhledání položky podle klíčového slova. Všimněte si, že návrháře nepodporuje nahrazení. Hledání v Návrháři najdete následující:  
  
## <a name="quick-find"></a>Rychle najít  
 Rychle najít v Návrháři najdete následující:  
  
-   Vlastnosti <xref:System.Activities.Activity> objekty, <xref:System.Activities.Statements.FlowNode> objekty, <xref:System.Activities.Statements.State> objekty, přechody a další položky vlastní řízení toku.  
  
-   Proměnné  
  
-   Arguments  
  
-   Výrazy  
  
#### <a name="using-quick-find"></a>Použití rychlého hledání  
  
1.  Pomocí návrháře pracovních postupů otevřete, stiskněte klávesu **Ctrl + F**, nebo vyberte **upravit**, **najít a nahradit**, **rychlého hledání**.  
  
2.  Zadejte hledaný termín do **najít** textové pole a klikněte na tlačítko **najít další**.  
  
3.  Hledaný termín budou umístěny v aktuálním pracovním postupu. Následující snímek obrazovky ukazuje název zobrazení aktivity se nachází v návrháři.  
  
     ![Výsledek hledání v Návrháři pracovních postupů](../workflow-designer/media/designersearch.png "DesignerSearch")  
  
## <a name="find-in-files"></a>Hledání v souborech  
 Použití funkce hledání v souborech vyhledá řetězce v soubory pracovního postupu, včetně souborů XAML.  
  
#### <a name="using-find-in-files"></a>Použití funkce hledání v souborech  
  
1.  V sadě Visual Studio, stiskněte klávesu **Ctrl + Shift + F**, nebo vyberte **upravit**, **najít a nahradit**, **hledání v souborech**  
  
2.  Zadejte hledanou položku do **najít** textové pole a klikněte na tlačítko **najít všechny**  
  
3.  Výsledek hledání se zobrazí v [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] **najít výsledek** zobrazení. Dvakrát klikněte na položku výsledek bude přejděte do aktivity, který obsahuje shody v Návrháři pracovních postupů.