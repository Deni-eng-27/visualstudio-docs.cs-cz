---
title: 'Krok 9: Vyzkoušejte jiné funkce | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 1b0c5c80-e5a6-4f69-a4a4-0e89a82d4de0
caps.latest.revision: 13
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 9e05fc6615fb2d836f3ea029912374f49b4d97a1
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72646888"
---
# <a name="step-9-try-other-features"></a>Krok 9: Vyzkoušejte jiné funkce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Chcete-li získat další informace, zkuste změnit ikony a barvy, přidat časovač hry a zvuky. Chcete-li, aby hra byla náročnější, zkuste zvětšit hrací plochu a upravte časovač.

 Pokud si chcete stáhnout dokončenou verzi ukázky, přečtěte si [ukázku s kurzem kompletní porovnávací hru](http://code.msdn.microsoft.com/Complete-Matching-Game-4cffddba).

### <a name="to-try-other-features"></a>Vyzkoušení dalších funkcí

- Nahraďte ikony a barvy těmi, které zvolíte.

    > [!TIP]
    > Zkuste se podívat na vlastnost [ForeColor](https://msdn.microsoft.com/library/system.windows.forms.control.forecolor%28v=vs.110%29.aspx) popisku.

- Přidejte časovač hry, který sleduje, jak dlouho hráči trvá, než vyhraje.

    > [!TIP]
    > K tomu můžete přidat popisek, který ve formuláři nad kontejnerem TableLayoutPanel zobrazí uplynulý čas, a do formuláře přidat další časovač pro sledování času. Použijte kód ke spuštění časovače, když hráč zahájí hru, a zastavení časovače, jakmile hráč spojí poslední dvě ikony.

- Pokud hráč najde shodu, přidejte zvuk, jiný zvuk, když hráč odkryje dvě ikony, které neodpovídají, a třetí zvuk, když program znovu skryje ikony.

    > [!TIP]
    > Chcete-li přehrát zvuky, můžete použít obor názvů System.media. Další informace najdete v tématu [přehráníC# zvuku v aplikaci model Windows Forms App (.NET)](http://youtu.be/qOh4ooHg1UU) nebo [o tom, jak přehrát zvuk v Visual Basic](http://youtu.be/-4oPDeQrtMs) .

- Udělejte hru obtížnější tím, že zvětšíte hrací plochu.

    > [!TIP]
    > Bude potřeba udělat více než jen přidat řádky a sloupce do kontejneru TableLayoutPanel – bude také nutné zvážit počet ikon, které vytvoříte.

- Udělejte hru náročnější tím, že skryjete první ikonu, pokud je hráč příliš pomalý a nezvolí druhou ikonu do vypršení určitého časového limitu.

### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Pokud si nevíte rady nebo máte otázky k programování, můžete zveřejnit svůj dotaz na jednom z diskuzních fór MSDN. Viz [Visual Basic Fórum](http://social.msdn.microsoft.com/Forums/home?forum=vbgeneral) a [vizuální C# Fórum](http://social.msdn.microsoft.com/Forums/home?forum=csharpgeneral).

- K dispozici jsou užitečné bezplatné video výukové materiály. Další informace o programování v Visual Basic najdete v tématu [Visual Basic základy: vývoj pro absolutní začátečníky](http://channel9.msdn.com/Series/Visual-Basic-Development-for-Absolute-Beginners). Další informace o programování v vizuálů C#najdete v tématu [ C# základy: vývoj pro absolutní začátečníky](http://channel9.msdn.com/Series/C-Sharp-Fundamentals-Development-for-Absolute-Beginners).

- Pokud se chcete vrátit k předchozímu kroku kurzu, přečtěte si [Krok 8: Přidání metody pro ověření, zda hráč zvítězil](../ide/step-8-add-a-method-to-verify-whether-the-player-won.md).
