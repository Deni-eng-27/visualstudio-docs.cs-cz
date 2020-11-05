---
title: Převedení typeof na nameof
ms.date: 08/12/2020
ms.topic: reference
author: m-redding
ms.author: midumont
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 96bd4d67302fb09e5c1cb7837ad73b345ad88c81
ms.sourcegitcommit: f4b49f1fc50ffcb39c6b87e2716b4dc7085c7fb5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400321"
---
# <a name="convert-typeof-to-nameof"></a>Převést `typeof` na `nameof`

Tento refaktoring platí pro:

- C#
- Visual Basic

**Co:** Umožňuje převést instanci typu `typeof(<QualifiedType>).Name` na `nameof(<QualifiedType>)` v jazyce C# a instanci `GetType(<QualifiedType>).Name` na do `NameOf(<QualifiedType>)` v Visual Basic.

**Když:**  Všechny instance, `typeof(<QualifiedType>).Name` kde `someType` není obecný typ. Toto vyloučení je nezbytné, protože tento případ nevrací stejnou řetězcovou hodnotu jako `nameof(<QualifiedType>)` . Totéž platí pro instanci Visual Basic.

**Proč:** Použití `nameof` namísto názvu `type` zabraňuje odrazu při načítání `type` objektu a je výkonnějším způsobem jeho zápisu.

## <a name="how-to"></a>Postupy

1. Umístěte kurzor do `typeof(<QualifiedType>).Name` instance pro C# nebo `GetType(<QualifiedType>).Name` v Visual Basic.

2. Stiskněte klávesu **CTRL** + **.** pro aktivaci nabídky **rychlé akce a refaktoringy** .

3. Vyberte jednu z následujících možností:

    - C#
      <br>Vyberte **převést typeof na nameof** : ![ Převod typeof na nameof.](media/convert-type-of.PNG)

    - Visual Basic
      <br>Vyberte **převést GetType na nameof** : ![ Převod typeof na nameof.](media/convert-get-type.PNG)

## <a name="see-also"></a>Viz také

- [Refactoring](../refactoring-in-visual-studio.md)
