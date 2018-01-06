---
title: "Převést metodu Get pro vlastnost - refaktoring (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
author: kuhlenh
ms.author: kaseyu
manager: ghogen
f1_keywords: vs.csharp.refactoring.convertmethodtoproperty
dev_langs: csharp
ms.workload: dotnet
ms.openlocfilehash: 71ff3db81be256bdb82413d04b2f939b706c6586
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="convert-get-method-to-property--convert-property-to-get-method"></a>Převést metodu Get pro vlastnost / převést vlastnosti na metodu Get
## <a name="convert-get-method-to-property"></a>Převést metodu Get pro vlastnost
**Co:** umožňuje převést metodu Get vlastnost (a volitelně metodu sada) a naopak.

**Kdy:** máte metodu Get, která neobsahuje žádné logiku.

**Postupy:**

1. Umístěte kurzor název Metoda Get.

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** k aktivační události **rychlé akce a refaktoring** nabídku a vyberte **metoda nahraďte vlastnost** z okna náhledu – místní nabídka. Pokud máte sadu metodu, můžete také metodu Set v tuto chvíli převést tak, že vyberete **metoda nahradit Get a Set – metoda s vlastností**.
   * **Myš**
     * Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídku a vyberte **metoda nahraďte vlastnost** z okna náhledu – místní nabídka. Pokud máte sadu metodu, můžete také metodu Set v tuto chvíli převést tak, že vyberete **metoda nahradit Get a Set – metoda s vlastností**.

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

**Postupy:**

1. Umístěte kurzor název Metoda Get.

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** spuštění **rychlé akce a refaktoring** nabídku a vyberte **vlastnost nahraďte metody** z okna náhledu – místní nabídka.
   * **Myš**
     * Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídku a vyberte **vlastnost nahraďte metody** z okna náhledu – místní nabídka.

1. Pokud jste spokojeni se změnami ve verzi preview kód, stiskněte klávesu **Enter** nebo klikněte na opravu z nabídky a změny budou potvrzeny.

## <a name="see-also"></a>Viz také  
[Refaktoring (C#)](../refactoring-csharp.md)  
[Náhled změn](../../ide/preview-changes.md)