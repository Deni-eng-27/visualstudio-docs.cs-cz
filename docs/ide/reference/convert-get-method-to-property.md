---
title: "Převést metodu Get pro vlastnost a proveďte převod vlastnosti na metodu Get v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
ms.devlang: csharp
author: kuhlenh
ms.author: kaseyu
manager: ghogen
f1_keywords:
- vs.csharp.refactoring.convertmethodtoproperty
dev_langs:
- csharp
ms.workload:
- dotnet
ms.openlocfilehash: ab91e95d699b4a7fcc27ca1f6bcdf43b51af9c26
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2018
---
# <a name="convert-get-method-to-property--convert-property-to-get-method-refactorings"></a>Převést metodu Get pro vlastnost / převést vlastnost na refaktoring Metoda Get

Tyto refaktoring platí pro:

- C#

## <a name="convert-get-method-to-property"></a>Převést metodu Get pro vlastnost

**Co:** umožňuje převést metodu Get vlastnost (a volitelně metodu sada) a naopak.

**Kdy:** máte metodu Get, která neobsahuje žádné logiku.

### <a name="how-to"></a>Postupy

1. Umístěte kurzor název Metoda Get.

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stiskněte klávesu **Ctrl**+**.** k aktivační události **rychlé akce a refaktoring** nabídce a vyberte **metoda nahraďte vlastnost** z okna náhledu – místní nabídka.
   - **Myš**
     - Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídce a vyberte **metoda nahraďte vlastnost** z okna náhledu – místní nabídka.

1. (Volitelné) Pokud máte sadu metodu, můžete také metodu Set v tuto chvíli převést tak, že vyberete **metoda nahradit Get a Set – metoda s vlastností**.

1. Pokud jste spokojeni se změnami ve verzi preview kód, stiskněte klávesu **Enter** nebo klikněte na opravu z nabídky a změny budou potvrzeny.

Příklad:

```csharp
private int MyValue;

// Before
public int GetMyValue()
{
    return MyValue;
}

// Replace 'GetMyValue' with property

// After
public int MyValue
{
    get { return MyValue; }
}
```

## <a name="convert-property-to-get-method"></a>Převést vlastnosti na metodu Get

**Co:** umožňuje převod vlastnosti na metodu Get

**Kdy:** máte vlastnost, která zahrnuje více než okamžitě nastavení a získání hodnotu

### <a name="how-to"></a>Postupy

1. Umístěte kurzor název Metoda Get.

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stiskněte klávesu **Ctrl**+**.** spuštění **rychlé akce a refaktoring** nabídku a vyberte **vlastnost nahraďte metody** z okna náhledu – místní nabídka.
   - **Myš**
     - Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídku a vyberte **vlastnost nahraďte metody** z okna náhledu – místní nabídka.

1. Pokud jste spokojeni se změnami ve verzi preview kód, stiskněte klávesu **Enter** nebo klikněte na opravu z nabídky a změny budou potvrzeny.

## <a name="see-also"></a>Viz také

- [Refactoring](../refactoring-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)