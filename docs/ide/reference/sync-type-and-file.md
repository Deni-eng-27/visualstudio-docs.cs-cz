---
title: Přejmenovat název souboru tak, aby odpovídal typu
ms.date: 01/26/2018
ms.topic: reference
author: TerryGLee
ms.author: tglee
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 5b7a42a174fecd078e804f2ab3c35fbe442364a6
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "75594393"
---
# <a name="sync-a-type-to-a-filename-or-a-filename-to-a-type-refactoring"></a>Synchronizovat typ s názvem souboru nebo název souboru pro refaktoring typu

Tento refaktoring platí pro:

- C#

- Visual Basic

**Co:** Umožňuje přejmenovat typ tak, aby odpovídal názvu souboru, nebo přejmenovat název souboru tak, aby odpovídal typu, který obsahuje.

**Když:** Přejmenovali jste soubor nebo typ a dosud jste neaktualizovali odpovídající soubor nebo typ tak, aby odpovídal.

**Proč:** Umístění typu do souboru s jiným názvem, nebo naopak, je obtížné najít, co hledáte. Přejmenováním typu nebo názvu souboru se kód bude čitelnější a jednodušší ho navigovat.

> [!NOTE]
> Tento refaktoring ještě není k dispozici pro projekty .NET Standard a .NET Core.

## <a name="how-to"></a>Postupy

1. Zvýrazněte nebo umístěte textový kurzor do názvu typu, který chcete synchronizovat:

   - C#:

       ![Zvýrazněný kód-C #](media/synctype-highlight-cs.png)

   - Visual Basic:

       ![Zvýrazněný kód – Visual Basic](media/synctype-highlight-vb.png)

2. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
      - Stiskněte klávesu **CTRL** + **.** Chcete-li aktivovat nabídku **rychlé akce a refaktoringu** a v okně náhledu vyberte **Přejmenovat soubor na *TypeName*. cs** , kde *TypeName* je název typu, který jste vybrali.
      - Stiskněte klávesu **CTRL** + **.** Chcete-li aktivovat nabídku **rychlé akce a refaktoringy** a v okně Náhled vyberte možnost **Přejmenovat typ názvu _souboru_ ** , kde *filename* je název aktuálního souboru.
   - **Myš**
      - Klikněte pravým tlačítkem na kód, vyberte nabídku **rychlé akce a refaktoring** a v okně Náhled vyberte **Přejmenovat soubor na *TypeName*. cs** , kde *TypeName* je název typu, který jste vybrali.
      - Klikněte pravým tlačítkem na kód, vyberte nabídku **rychlé akce a refaktoring** a v okně Náhled vyberte **Přejmenovat typ na _název souboru_ ** , kde *filename* je název aktuálního souboru.

   Typ nebo soubor se přejmenují.

   - C#: v následujícím příkladu byl soubor **MyClass.cs** přejmenován na **MyNewClass.cs** tak, aby odpovídal názvu typu.

       ![Vložený výsledek C #](media/synctype-result-cs.png)

   - Visual Basic: v následujícím příkladu se soubor **Employee. vb** přejmenoval na **Person. vb** , aby odpovídal názvu typu.

       ![Visual Basic vloženého výsledku](media/synctype-result-vb.png)

## <a name="see-also"></a>Viz také

- [Refactoring](../refactoring-in-visual-studio.md)
