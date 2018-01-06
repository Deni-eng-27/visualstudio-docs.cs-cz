---
title: "Přesuňte deklaraci téměř odkaz - refaktoring (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
ms.assetid: d79d55ae-f6bb-4902-8db2-e7fe01bdb0bf
author: kuhlenh
ms.author: kaseyu
manager: ghogen
dev_langs: csharp
ms.workload: dotnet
ms.openlocfilehash: c274fd758fdae468bee884fcf1686abc16ec1d7e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="move-declaration-near-reference-in-c"></a>Přesuňte deklaraci téměř odkaz v jazyce C# #
**Co:** můžete přesouvat deklarace proměnných blíže k jejich využití.

**Kdy:** máte deklarace proměnných, které se dají v užší oboru.

**Důvod:** může nechat, jak je, ale které může způsobit problémy čitelnost nebo skrytí informace. Toto je možnost refactor ke zlepšení čitelnosti.

**Postupy:**

1. Umístěte kurzor deklarace proměnné.

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** k aktivační události **rychlé akce a refaktoring** nabídku a vyberte **přesunout deklarace téměř odkaz** z okna náhledu – místní nabídka.
   * **Myš**
     * Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídku a vyberte **přesunout deklarace téměř odkaz** z okna náhledu – místní nabídka.

1. Když budete spokojeni se změnami, stiskněte **Enter** nebo klikněte na opravit v nabídce a změny budou potvrzeny.

Příklad:
```csharp
// Before
int x;
if (condition)
{
    x = 1;
    Console.WriteLine(x);
}

// Move declaration near reference

// After
if (condition)
{
    int x = 1;
    Console.WriteLine(x);
}
```

## <a name="see-also"></a>Viz také  
[Refaktoring (C#)](../refactoring-csharp.md)  
[Náhled změn](../../ide/preview-changes.md)