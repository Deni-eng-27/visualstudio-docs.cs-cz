---
title: "Nepodporované scénáře v Návrháři pracovních postupů ladění | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 6adbe379-41d0-4681-9cd0-b91f187c3c2c
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 958937e8d846c07cafc8293b4592ad6c67479849
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="unsupported-debugging-scenarios-in-the-workflow-designer"></a>Nepodporované scénáře ladění v Návrháři pracovních postupů
Návrhář postupu provádění v [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] přidali mnoho nových funkcí, ale stále existují některé ladění scénáře, které nejsou podporovány. Tento dokument podrobně popisuje ladění scénáře nepodporované návrháře pracovních postupů.  
  
-   Provádění nemůže pokračovat, po kód bylo upraveno.  
  
-   Provádění nemůže pokračovat z libovolného bodu v pracovním postupu (nastavit další).  
  
-   Provádění nelze pokračovat, dokud kurzor je dosaženo (Spustit ke kurzoru).  
  
-   Návrhář postupu provádění nelze použít k ladění vytvořených v kódu bez použití návrháře pracovních postupů.  
  
-   Pracovní postupy vytvořené v dřívějších verzích [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] nemůžete ladit v [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] designer.  
  
-   Zarážky nelze definovat na propojení mezi aktivitami nebo <xref:System.Activities.Statements.Flowchart> uzlů.  
  
-   Během ladění není k dispozici do schránky.  
  
-   Zarážky nezachovají, při aktivity se kopírování a vložení.  
  
-   V okně zásobník volání nelze nastavit zarážky pracovního postupu.  
  
-   Při vytváření zarážky v návrháři **řádku** a **znak** nastavení v **nové zarážek** dialogové okno se nepoužívají.  
  
-   Breakpoint – okno nebo v místní nabídce nepodporuje následující sloupce nebo možnosti pro ladění pracovního postupu:  
  
    -   Podmínka  
  
    -   Počet volání  
  
    -   Při průchodu  
  
    -   Funkce  
  
    -   Data  
  
    -   Proces  
  
    -   Přejděte na zpětný překlad