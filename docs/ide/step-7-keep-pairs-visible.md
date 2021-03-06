---
title: 'Krok 7: Zachování dvojic ve viditelném stavu'
ms.date: 11/04/2016
ms.topic: tutorial
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
dev_langs:
- CSharp
- VB
ms.assetid: 42e1d08c-7b2e-4efd-9f47-85d6206afe35
author: ornellaalt
ms.author: ornella
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e854425bab10174220188b23fb7e292371e9cb48
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "88168720"
---
# <a name="step-7-keep-pairs-visible"></a>Krok 7: Zachování dvojic ve viditelném stavu
Hra funguje dobře tak dlouho, dokud hráč vybírá pouze dvojice ikon, které neodpovídají. Ale zvažte, co by mělo nastat, pokud hráč vybere shodnou dvojici. Místo toho, aby ikony zmizely zapnutím časovače (pomocí <xref:System.Windows.Forms.Timer.Start> metody), by se hra měla resetovat sama tak, aby již nesledovala popisky pomocí `firstClicked` `secondClicked` proměnných a, aniž by bylo nutné resetovat barvy pro dva popisky, které byly zvoleny.

## <a name="to-keep-pairs-visible"></a>Zachování dvojic viditelných

1. `if`Do `label_Click()` metody obslužné rutiny události přidejte následující příkaz, poblíž konce kódu těsně nad příkazem, kde spouštíte časovač. Při přidávání do programu si kód pořádně prohlédněte. Zamyslete se nad tím, jak kód funguje.

     [!code-csharp[VbExpressTutorial4Step7#9](../ide/codesnippet/CSharp/step-7-keep-pairs-visible_1.cs)]
     [!code-vb[VbExpressTutorial4Step7#9](../ide/codesnippet/VisualBasic/step-7-keep-pairs-visible_1.vb)]

     > [!IMPORTANT]
     > Pomocí ovládacího prvku programovací jazyk v pravém horním rohu této stránky můžete zobrazit fragment kódu jazyka C# nebo Visual Basic fragment kódu.<br><br>![Řízení programovacího jazyka pro Docs.Microsoft.com](../ide/media/docs-programming-language-control.png)

     První řádek `if` příkazu, který jste právě přidali, kontroluje, zda ikona v prvním popisku, kterou hráč zvolí, je stejná jako ikona ve druhém popisku. Pokud jsou ikony stejné, program provede tři příkazy mezi složenou závorkou v jazyce C# nebo třemi příkazy v rámci `if` příkazu v Visual Basic. První dva příkazy obnovily `firstClicked` `secondClicked` referenční proměnné a, aby již nesledovaly žádný z popisků. (Tyto dva příkazy můžete rozpoznat z <xref:System.Windows.Forms.Timer.Tick> obslužné rutiny události časovače.) Třetí příkaz je `return` příkaz, který oznamuje programu, aby přeskočil zbytek příkazů v metodě bez jejich spuštění.

     Pokud programování v jazyce C# jste si všimli, že část kódu používá jediný znak rovná se ( `=` ), zatímco jiné příkazy používají dva symboly rovná se ( `==` ). Zvažte, proč `=` se na některých místech používá, ale `==` používá se na jiných místech.

     Toto je typický příklad, který ukazuje rozdíl. Pozorně se podívejte na kód mezi závorkami v `if` příkazu.

    ```vb
    firstClicked.Text = secondClicked.Text
    ```

    ```csharp
    firstClicked.Text == secondClicked.Text
    ```

     Pak se pečlivě podívejte na první příkaz v bloku kódu po `if` příkazu.

    ```vb
    firstClicked = Nothing
    ```

    ```csharp
    firstClicked = null;
    ```

     První z těchto dvou příkazů ověří, zda jsou dvě ikony stejné. Vzhledem k tomu, že se porovnávají dvě hodnoty, použije program C# `==` operátor rovnosti. Druhý příkaz skutečně změní hodnotu (označované jako *přiřazení*) a nastaví `firstClicked` referenční proměnnou rovnou na `null` resetování. To je důvod, proč `=` místo toho používá operátor přiřazení. Jazyk C# používá `=` k nastavení hodnot a `==` k jejich porovnání. Visual Basic používá `=` pro přiřazování a porovnávání proměnných.

2. Uložte a spusťte program a začněte vybírat ikony ve formuláři. Pokud zvolíte dvojici, která neodpovídá, událost časovače Tick se aktivuje a obě ikony zmizí. Pokud zvolíte odpovídající dvojici, příkaz New se `if` spustí a příkaz return způsobí, že metoda přeskočí kód, který spouští časovač, takže ikony zůstanou viditelné, jak je znázorněno na následujícím obrázku.

     ![Hra, kterou vytvoříte v tomto tutoriálu](../ide/media/express_finishedgame.png)<br/>
***Porovnávací hra*** *s viditelnými páry ikon*

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Pokud chcete přejít na další krok kurzu, přečtěte si **[Krok 8: Přidání metody pro ověření, zda hráč zvítězil](../ide/step-8-add-a-method-to-verify-whether-the-player-won.md)**.

- Pokud se chcete vrátit k předchozímu kroku kurzu, přečtěte si [Krok 6: Přidání časovače](../ide/step-6-add-a-timer.md).
