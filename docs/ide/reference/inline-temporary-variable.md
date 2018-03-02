---
title: "Nahraďte proměnnou dočasné s hodnotou v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 836f7b847a2a57de83f6bea7f05bed83571e7485
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2018
---
# <a name="inline-a-temporary-variable-refactoring"></a>Vložené dočasné proměnné refaktoring

Tato refaktoring platí pro:

- C#

- Visual Basic

**Co:** umožňuje odebrání dočasné proměnné a nahraďte ji metodou jeho hodnotu.

**Kdy:** použití dočasné proměnné díky těžší pochopit kód.

**Důvod:** odebrání dočasné proměnné může usnadnit kód čtení.

## <a name="how-to"></a>Postupy

1. Zvýrazněte nebo umístěte kurzor text do dočasné proměnné být vložená:

   - C#:

    ![Zvýrazněný - C#](media/inline-highlight-cs.png)

   - Visual Basic:

    ![Zvýrazněný kód – Visual Basic](media/inline-highlight-vb.png)

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stiskněte klávesu **Ctrl**+**.** spuštění **rychlé akce a refaktoring** nabídky.
   - **Myš**
     - Klikněte pravým tlačítkem na kód a vyberte **rychlé akce a refaktoring** nabídky.

1. Vyberte **dočasné vloženou proměnnou** z okna náhledu – místní nabídka.

   Proměnná se odebere a jeho použití nahrazen hodnotou proměnné.

   - C#:

    ![Vložené result - C#](media/inline-result-cs.png)

   - Visual Basic:

    ![Vložené result - jazyka Visual Basic](media/inline-result-vb.png)

## <a name="see-also"></a>Viz také

[Refactoring](../refactoring-in-visual-studio.md)