---
title: Generovat rovná C# a metoda GetHashCode přepsání v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 01/26/2018
ms.technology: vs-ide-general
ms.topic: conceptual
author: kuhlenh
ms.author: kaseyu
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 3768659ce6c4e52c9e4f6473207fc74513797f17
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="generate-equals-and-gethashcode-method-overrides-in-visual-studio"></a>Generovat rovná a metoda GetHashCode přepsání v sadě Visual Studio

Generování kódu platí pro:

- C#

**Co:** umožňuje vygenerovat **rovná** a **GetHashCode** metody.

**Kdy:** generovat tato přepsání, až budete mít typ, který by měl být ve srovnání jedno či více polí, místo podle umístění objektu v paměti.

**Proč:**

- Pokud implementujete typ hodnoty, měli byste zvážit přepsání **rovná** metodu k získání vyšší výkon přes výchozí implementace metody Equals na typ hodnoty.

- Pokud implementujete odkazového typu, měli byste zvážit přepsání **rovná** metoda Pokud vašeho typu vypadá jako základní typ, jako je například bod, řetězec, BigNumber a tak dále.

- Přepsání **GetHashCode** metoda umožňující typu fungovat správně v zatřiďovací tabulku. Přečtěte si další pokyny [operátory rovnosti](/dotnet/standard/design-guidelines/equality-operators).

## <a name="how-to"></a>Postupy

1. Umístěte kurzor vaší deklaraci typu.

   ![Zvýrazněný kód](media/overrides-highlight-cs.png)

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stiskněte klávesu **Ctrl**+**.** spuštění **rychlé akce a refaktoring** nabídky.
   - **Myš**
     - Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídky.
     - Klikněte na ![Žárovek](media/bulb-cs.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s deklarace typu.

   ![Vytvoření náhledu přepsání](media/overrides-preview-cs.png)

1. Vyberte **generovat Equals(object)** nebo **generovat rovná se a GetHashCode** z rozevírací nabídky.

1. V **vyberte členy** dialogové okno, vyberte členy, které chcete generovat metody pro:

    ![Generovat přepsání dialogové okno](media/overrides-dialog-cs.png)

    > [!TIP]
    > Můžete také vygenerovat operátory z tohoto dialogového okna pomocí zaškrtávacích políček pod seznam členů.

   Rovná se a GetHashCode přepsání se generují s výchozí implementace.

   ![Generování výsledků – metoda](media/overrides-result-cs.png)

## <a name="see-also"></a>Viz také

- [Generování kódu](../code-generation-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)
