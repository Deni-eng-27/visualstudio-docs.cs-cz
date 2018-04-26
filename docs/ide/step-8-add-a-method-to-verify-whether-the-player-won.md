---
title: 'Krok 8: Přidejte metodu k ověření, zda hráč vyhrál'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 6e317f6e-ba4c-4306-8924-300b0c2f65c6
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b4a7d51a9f88d7ecb7425a2b72740169d03077b5
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="step-8-add-a-method-to-verify-whether-the-player-won"></a>Krok 8: Přidejte metodu k ověření, zda hráč vyhrál
Vytvořili jste zábavnou hru, která však potřebuje ještě něco. Hra by měla skončit při přehrávač služby wins, proto je nutné přidat `CheckForWinner()` metodu k ověření, zda hráč vyhrál.  

### <a name="to-add-a-method-to-verify-whether-the-player-won"></a>Přidání metody k ověření, zda hráč zvítězil  

1.  Přidat `CheckForWinner()` metoda do dolní části kódu, níže `timer1_Tick()` obslužné rutiny události, jak je znázorněno v následujícím kódu.  

     [!code-csharp[VbExpressTutorial4Step8#10](../ide/codesnippet/CSharp/step-8-add-a-method-to-verify-whether-the-player-won_1.cs)]
     [!code-vb[VbExpressTutorial4Step8#10](../ide/codesnippet/VisualBasic/step-8-add-a-method-to-verify-whether-the-player-won_1.vb)]  

     Metoda používá další `foreach` smyčky v jazyce Visual C# nebo `For Each` v jazyce Visual Basic projít každý popisek v kontejneru TableLayoutPanel. Používá operátor rovnosti (`==` v jazyce Visual C# a `=` v jazyce Visual Basic) ke kontrole barvy ikony každý popisek k ověření, zda odpovídá na pozadí. Pokud se barvy shodují, zůstane ikona skryta a hráč nespároval všechny zbývající ikony. V takovém případě se používá program `return` příkaz tak, aby přeskočil zbytek metodu. Pokud získá prostřednictvím všechny popisky smyčky bez spuštění `return` příkaz, který znamená všechny ikony na formuláři byly odpovídá. Program zobrazí MessageBox k Blahopřání player v hodnocený a pak zavolá formuláře `Close()` metoda k ukončení hry.  

2.  V dalším kroku mít kliknutí jmenovky obslužné rutiny události zavolat novou `CheckForWinner()` metoda. Ujistěte se, že váš program kontroluje vítěze ihned po tom, co zobrazí druhou ikonu, kterou hráč vybere. Vyhledejte řádek, kde nastavíte barvy druhý zvolené ikony a pak zavolají `CheckForWinner()` metoda hned po tomto, jak je znázorněno v následujícím kódu.  

     [!code-csharp[VbExpressTutorial4Step8#11](../ide/codesnippet/CSharp/step-8-add-a-method-to-verify-whether-the-player-won_2.cs)]
     [!code-vb[VbExpressTutorial4Step8#11](../ide/codesnippet/VisualBasic/step-8-add-a-method-to-verify-whether-the-player-won_2.vb)]  

3.  Program uložte a spusťte jej. Zahrajte si hru a spárujte všechny ikony. Když vyhrajete, program zobrazí prvek MessageBox s blahopřáním (jak je ukázáno na následujícím obrázku) a potom jej zavře.  

     ![Odpovídající hru s MessageBox](../ide/media/express_tut4step8.png "Express_Tut4Step8")  
Porovnávací hra s ovládacím prvkem MessageBox  

### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  

-   Chcete-li přejít k dalšímu kroku kurzu, přečtěte si téma [krok 9: Vyzkoušejte jiné funkce](../ide/step-9-try-other-features.md).  

-   Chcete-li vrátit k předchozímu kroku kurzu, přečtěte si téma [kroku 7: Zachovat dvojice viditelné](../ide/step-7-keep-pairs-visible.md).
