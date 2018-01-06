---
title: "Odebrat nedostupný kódu - refaktoring (C#) | Microsoft Docs"
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
dev_langs: csharp
ms.workload: dotnet
ms.openlocfilehash: e57db74ea431d9090df1dc34fd3cff3cf03dd475
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="remove-unreachable-code-in-c"></a>Odebrat nedostupný kód v jazyce C# #
**Co:** odebere kód, který bude nikdy spuštěn.

**Kdy:** vašeho programu nemá žádnou cestu na fragment kódu, provedení nepotřebné tento fragment kódu.

**Důvod:** zlepšení čitelnosti a jeho udržovatelnost odebráním kód, který je nadbytečné a nebude nikdy provedena.

**Postupy:**

1. Umístěte ukazatel myši na libovolné místo v vybledlé se kód, který nedostupný:

![Barevně nedostupný kódu](media/unreachablecode_faded.png)  

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** spuštění **rychlé akce a refaktoring** nabídku a vyberte **odebrat nedostupný kód** z okna náhledu – místní nabídka.
   * **Myš**
     * Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídku a vyberte **odebrat nedostupný kód** z okna náhledu – místní nabídka.

1. Když budete spokojeni se změnami, stiskněte **Enter** nebo klikněte na opravit v nabídce a změny budou potvrzeny.

Příklad:
```csharp
// Before
private void Method()
{
    throw new Exception(nameof(Method));
    Console.WriteLine($"Exception for method {nameof(Method)}");
}

// Remove unreachable code

// After
private void Method()
{
    throw new Exception(nameof(Method));
}
```

## <a name="see-also"></a>Viz také  
[Refaktoring (C#)](../refactoring-csharp.md)  
[Náhled změn](../../ide/preview-changes.md)