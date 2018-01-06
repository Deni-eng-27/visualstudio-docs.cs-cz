---
title: "Vložené proměnné dočasné - refaktoringu (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a63d6407-5acb-4d5f-8c0e-ecedddc07177
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3607e646f5f1ccc6121e5ee8a5b71772008f1ce8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="inline-a-temporary-variable-in-visual-basic"></a>Vložené dočasné proměnné v jazyce Visual Basic
**Co:** vám umožní odebrat použití dočasné proměnné a nahraďte ji metodou skutečný kód.

**Kdy:** použití dočasné proměnné díky těžší pochopit kód.  

**Důvod:** odebrání dočasné proměnné může usnadnit kód čtení v určitých situacích

**Postupy:**

1. Zvýrazněte nebo umístěte kurzor text do dočasné proměnné být vložená:

   ![Zvýrazněný kód](media/inline_highlight.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** spuštění **rychlé akce a refaktoring** nabídku a vyberte **dočasné vloženou proměnnou** z okna náhledu – místní nabídka.
   * **Myš**
     * Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídku a vyberte **dočasné vloženou proměnnou** z okna náhledu – místní nabídka.

   Proměnná se odeberou a jeho použití nahrazen hodnotou proměnné okamžitě.

   ![Vložené výsledek](media/inline_result.png)

## <a name="see-also"></a>Viz také
[Refaktoringu (Visual Basic)](../refactoring-vb.md)