---
title: Použití trasováním v ladicím programu | Microsoft Docs
ms.date: 9/17/2019
ms.topic: conceptual
helpviewer_keywords:
- tracepoints, about tracepoints
author: Sagar-S-S
ms.author: sashe
manager: AndSter
ms.workload:
- multiple
ms.openlocfilehash: 7680b305fad6f8ea1d7961ec5a70ddafd578c77d
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/25/2019
ms.locfileid: "71095257"
---
# <a name="use-tracepoints-in-the-visual-studio-debugger"></a>Použití trasováním v ladicím programu sady Visual Studio

Trasováním umožňuje protokolovat informace do okna výstup v části konfigurovatelné podmínky bez nutnosti změny nebo zastavení kódu. Tato funkce je podporována pro spravovaný i nativní kód i pro několik jazyků, jako je například JavaScript a C#.

## <a name="let39s-take-an-example"></a>Pojďme&#39;si příklad

Následující vzorový program je jednoduchá `for` smyčka s proměnnou čítače, která se zvyšuje o jednu pokaždé, když smyčka spustí jinou iteraci.

![Příklad čítače](../debugger/media/counterexample.png "Příklad čítače")

## <a name="set-tracepoints-in-source-code"></a>Nastavení trasováním ve zdrojovém kódu

Trasováním můžete nastavit zadáním výstupního řetězce v okně **Nastavení zarážky** v políčku **Akce** .

1. Chcete-li inicializovat zarážka s trasováním, nejprve klikněte na hřbet vlevo od čísla řádku, kde chcete nastavit zarážka s trasováním.

   ![Inicializace zarážky](../debugger/media/breakpointinitialization.png "Inicializace zarážky")

2. Najeďte myší na červený kroužek a pak klikněte na ikonu ozubeného kolečka.
3. Tím se otevře okno **Nastavení zarážky** .

   ![Okno zarážky](../debugger/media/breakpointwindow.png "Okno zarážky")

4. Zaškrtněte políčko **Akce** .

   ![Pole zaškrtnuté akce](../debugger/media/checkedactionsbox.png "Pole zaškrtnuté akce")

   Všimněte si, jak se červené kolečko změní na kosočtverec, který indikuje, že jste přešli ze zarážky na zarážka s trasováním.

5. Zadejte zprávu, kterou chcete přihlašovat k **zobrazení zprávy v** textovém poli okno výstup (podrobnosti najdete v dalších částech tohoto článku).

   Vaše zarážka s trasováním je teď nastavené. &quot;Tlačítko Zavřít&quot; se zobrazí, pokud chcete provést protokolování informací do okno výstup.

6. Pokud chcete přidat podmínky, které určují, jestli se vaše zpráva zobrazuje, zaškrtněte políčko **podmínky** .

   ![Políčko zaškrtnuté podmínky](../debugger/media/checkedconditionsbox.png "Políčko zaškrtnuté podmínky")

   Máte tři možnosti pro podmínky: **Podmíněný výraz**, **Filtr**a **Počet volání**.

## <a name="actions-menu"></a>Nabídka akce

Tato nabídka umožňuje protokolovat zprávu do okna výstup. Do pole pro zprávu zadejte řetězce, které chcete výstup (nejsou nutné žádné uvozovky). Pokud chcete zobrazit hodnoty proměnných, ujistěte se, že je uzavíráte do složených závorek.

Pokud například chcete zobrazit hodnotu `counter` proměnné v konzole výstupu, zadejte do textového pole zpráva text {Counter}.

![Výstupní zpráva čítače](../debugger/media/counteroutputmessage.png "Výstupní zpráva čítače")

Pokud kliknete na **Zavřít** a pak na ladit program (**F5**), zobrazí se následující výstup v okně výstup.

![Zpráva akcí v okno výstup](../debugger/media/actionsmessageinoutputwindow.png "Zpráva akcí v okno výstup")

K zobrazení konkrétnějších informací můžete použít také speciální klíčová slova. Zadejte klíčové slovo přesně tak, jak je uvedeno níže (použijte "$" před každým klíčovým slovem a všechna velká písmena pro samotné klíčové slovo).

| Klíčové slovo | Co se zobrazí |
| --- | --- |
| $ADDRESS | Aktuální instrukce |
| $CALLER | Název volající funkce |
| $CALLSTACK | Zásobník volání |
| $FUNCTION | Název aktuální funkce |
| $PID | ID procesu |
| $PNAME | Název procesu |
| $TID | ID vlákna |
| $TNAME   | Název vlákna |
| $TICK | Počet impulsů (z funkce GetTickCount systému Windows) |

## <a name="conditions-menu"></a>Nabídka podmínky

Podmínky umožňují filtrovat výstupní zprávy tak, aby se zobrazovaly pouze v určitých situacích. Existují tři hlavní druhy podmínek, které máte k dispozici.

### <a name="conditional-expression"></a>Podmíněný výraz
V případě podmíněného výrazu se výstupní zpráva zobrazí pouze v případě, že jsou splněny určité podmínky.

Pro podmíněné výrazy můžete nastavit zarážka s trasováním na výstup zprávy, když je určitá podmínka pravdivá nebo když se změní. Například pokud chcete zobrazit pouze hodnotu čítače během dokonce iterací `for` smyčky, můžete vybrat možnost **je true** a poté zadat `i%2 == 0` do textového pole zpráva.

![Podmíněný výraz má hodnotu true] . (../debugger/media/conditionalexpressionistrue.png "Podmíněný výraz má hodnotu true") .

Chcete-li vytisknout hodnotu čítače při změně iterace `for` smyčky, vyberte možnost **při změně** a zadejte `i` do textového pole zpráva.

![Podmíněný výraz při změně](../debugger/media/conditionalexpressionwhenchanged.png "Podmíněný výraz při změně")

Chování možnosti **při změně** se liší v různých programovacích jazycích.

- V případě nativního kódu ladicí program nepovažuje první vyhodnocení podmínky za účelem změny, takže nezarážka s trasováním při prvním vyhodnocení.
- V případě spravovaného kódu ladicí program **při výběru změny změní** zarážka s trasováním na první vyhodnocení.

Komplexnější pohled na platné výrazy, které můžete použít při nastavování podmínek, najdete v tématu [výrazy v ladicím programu](expressions-in-the-debugger.md) .

### <a name="hit-count"></a>Počet volání
Podmínka počet průchodů umožňuje odeslat výstup pouze po řádku kódu, kde je zarážka s trasováním nastaveno, který provedl zadaný počet opakování.

V případě počtu volání můžete zvolit výstup zprávy, když je řádek kódu, kde je zarážka s trasováním, spuštěný, kolikrát je stejný, je násobek, nebo je větší nebo roven zadané hodnotě počtu volání. Vyberte možnost, která nejlépe vyhovuje vašim potřebám, a v poli zadejte celočíselnou hodnotu (například 5), která představuje tuto iteraci zájmu.

![Počet přístupů do podmíněného výrazu](../debugger/media/conditionalexpressionhitcount.png "Počet přístupů do podmíněného výrazu")

### <a name="filter"></a>Filtr
U podmínky filtru určete, pro která zařízení, procesy nebo výstup vláken se zobrazuje výstup.

![Filtr podmíněného výrazu](../debugger/media/conditionalexpressionfilter.png "Filtr podmíněného výrazu")

Seznam výrazů filtru:

- MachineName = "name"
- ProcessId = hodnota
- ProcessName = "name"
- ThreadId = hodnota
- ThreadName = "name"

Uzavřete řetězce (například názvy) do dvojitých uvozovek. Hodnoty lze zadat bez uvozovek. `&` Klauzule lze kombinovat pomocí ( `||` `AND`),`OR`(),`NOT`() a závorek. `!`

## <a name="considerations"></a>Požadavky

I když jsou trasováním určeny pro ladění čisticího a plynulejšího prostředí, je potřeba mít na paměti několik důležitých informací, o kterých byste měli vědět, kdy je budete používat.

Při kontrole vlastnosti nebo atributu objektu se někdy může změnit jeho hodnota. Nejedná se o chybu způsobenou funkcí zarážka s trasováním, ale je třeba uvést, že použití trasováním ke kontrole objektů nevylučuje tyto nechtěné úpravy.

Způsob, jakým jsou výrazy vyhodnocovány v okně zprávy **Akce** , se může lišit od jazyka, který aktuálně používáte pro vývoj. Například pro výstup řetězce nemusíte zabalit zprávu v uvozovkách, a to i v případě, že byste normálně `Debug.WriteLine()` používali nebo `console.log()`. Také syntaxe složené závorky (`{ }`) na výstupní výrazy se může lišit od konvence pro výstup hodnot ve vývojovém jazyce. (Obsah ve složených závorkách (`{ }`) by se ale měl pořád zapsat pomocí syntaxe vašeho vývojového jazyka).

## <a name="see-also"></a>Viz také:

- [Co je ladění?](../debugger/what-is-debugging.md)
- [Psali lepší C# kódu pomocí sady Visual Studio](../debugger/write-better-code-with-visual-studio.md)
- [První pohled na ladění](../debugger/debugger-feature-tour.md)
- [Výrazy v ladicím programu](expressions-in-the-debugger.md)
- [Použití zarážek](../debugger/using-breakpoints.md)