---
title: Refaktorujte pole na vlastnost
ms.date: 01/26/2018
ms.topic: reference
author: TerryGLee
ms.author: tglee
manager: jillfra
f1_keywords:
- vs.csharp.refactoring.encapsulatefield
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: db0bd17cd0bead3807f857b2198b8d4ea4c72ffb
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "75569709"
---
# <a name="encapsulate-a-field-refactoring"></a>Zapouzdření refaktoringu pole

Tento refaktoring platí pro:

- C#

- Visual Basic

**Co:** Umožňuje změnit pole na vlastnost a aktualizovat všechna použití tohoto pole na použití nově vytvořené vlastnosti.

**Když:** Chcete přesunout pole do vlastnosti a aktualizovat všechny odkazy na toto pole.

**Proč:** Chcete udělit přístup k poli jiným třídám, ale nechcete, aby tyto třídy měly přímý přístup.  Po zabalení pole ve vlastnosti můžete napsat kód pro ověření přiřazené hodnoty, například.

## <a name="how-to"></a>Postupy

1. Zvýrazněte nebo umístěte textový kurzor do názvu pole, které chcete zapouzdřit:

   - C#:

       ![Zvýrazněný kód-C #](media/encapsulate-highlight-cs.png)

   - Visual Basic:

       ![Zvýrazněný kód – Visual Basic](media/encapsulate-highlight-vb.png)

2. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
      - Stiskněte klávesy **CTRL + R**a pak **kombinaci kláves CTRL + E**.  (Všimněte si, že se vaše klávesová zkratka může lišit v závislosti na vybraném profilu.)
      - Stiskněte klávesu **CTRL** + **.** Chcete-li aktivovat nabídku **rychlé akce a refaktoring** a v okně náhledu vyberte položku **zapouzdřit pole** .
   - **Myš**
      - Vyberte možnost **upravit > refaktoring > zapouzdřit pole**.
      - Klikněte pravým tlačítkem na kód, vyberte nabídku **rychlé akce a refaktoring** a v okně Náhled vyberte možnost **zapouzdření pole** .

   Výběr | Popis
   --------- | -----------
   **Zapouzdřit pole (a použít vlastnost)** | Zapouzdřuje pole s vlastností a aktualizuje všechna použití pole na použití vygenerované vlastnosti.
   **Zapouzdřit pole (ale dál používat pole)** | Zapouzdřuje pole s vlastností, ale ponechá všechna použití pole bez dotyku.

   Vlastnost je vytvořena a odkazy na pole jsou aktualizovány, pokud jsou vybrány.

   > [!TIP]
   > Pomocí odkazu **Náhled změn** v místním okně [zjistíte, co bude výsledek](../../ide/preview-changes.md) před potvrzením.

   - C#:

      ![Výsledek zapouzdření vlastnosti-C #](media/encapsulate-result-cs.png)

   - Visual Basic:

      ![Výsledek zapouzdření vlastnosti – Visual Basic](media/encapsulate-result-vb.png)

## <a name="see-also"></a>Viz také

- [Refactoring](../refactoring-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)
