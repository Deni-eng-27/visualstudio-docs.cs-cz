---
title: "Implementace abstraktní třídy v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: ecb86d6870e4a9d67e5994e33098a7d964d24410
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="implement-an-abstract-class-in-visual-studio"></a>Implementace abstraktní třídy v sadě Visual Studio

Generování kódu platí pro:

- C#

- Visual Basic

**Co:** umožňuje okamžitě generování kódu potřebnou k implementaci abstraktní třídu.

**Kdy:** chcete použít dědění z abstraktní třídy.

**Důvod:** ručně může implementovat všechny abstraktní členy jeden po druhém, ale tato funkce bude automaticky generovat všechny podpisy metoda.

## <a name="how-to"></a>Postupy

1. Umístěte kurzor na řádek níž se nachází red vlnovka, označující mít dědí z abstraktní třídy, ale ještě implementována všechny požadované členy.

   - C#:

    ![Zvýrazněný kód C#](media/abstract-highlight-cs.png)

   - Visual Basic:

    ![Zvýrazněný kód jazyka Visual Basic](media/abstract-highlight-vb.png)

1. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
     - Stiskněte klávesu **Ctrl +.** spuštění **rychlé akce a refaktoring** nabídky.
   - **Myš**
     - Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídky.
     - Pozastavte ukazatel myši nad červenou vlnovkou a klikněte na ![Žárovek](media/bulb-cs.png) ikona, která se zobrazí.
     - Klikněte ![Žárovek](media/bulb-cs.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s červenou vlnovkou.

   ![Implementace třídy preview](media/abstract-preview-cs.png)

1. Vyberte **abstraktní třída implementace** z rozevírací nabídky.

   > [!TIP]
   > - Použití **zobrazení náhledu změn** odkaz v dolní části okna náhledu [zobrazíte všechny změny](../../ide/preview-changes.md) , budou provedeny před provedením váš výběr.
   > - Použití **dokumentu**, **projektu**, a **řešení** odkazy v dolní části okna náhledu k vytvoření podpisy správné metody napříč více tříd, které dědí vlastnosti z abstraktní třída.

   Abstraktní metodu podpisy jsou vytvářeny a jsou připraveny k implementaci.

   - C#:

      ![Implementace třídy výsledek C#](media/abstract-result-cs.png)

   - Visual Basic:

      ![Implementace třídy výsledek jazyka Visual Basic](media/abstract-result-vb.png)

## <a name="see-also"></a>Viz také

[Generování kódu](../code-generation-in-visual-studio.md)  
[Náhled změn](../../ide/preview-changes.md)
