---
title: Uživatelské rozhraní ladicího programu (XSLT)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
ms.assetid: 846fdabd-e5c3-4688-9b0d-a93fbeea1b96
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 612fa233ceaa2fdee16a75b25f15576d631bd30b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54917530"
---
# <a name="debugger-user-interface-xslt"></a>Uživatelské rozhraní ladicího programu (XSLT)

Toto téma popisuje oknech ladicího programu a dialogových oknech. Popisuje pouze uživatelské rozhraní části, ze kterých mají ladění chování specifické pro XSLT.

Další informace najdete v tématu [ladění odkazu uživatelského rozhraní](../debugger/debugging-user-interface-reference.md).

## <a name="locals-window"></a>Místní hodnoty – okno
 V okně místních hodnot zobrazí informace o všechny proměnné definované v šabloně stylů. V okně místních hodnot obsahuje tři sloupce informací:

 **Název**

 Tento sloupec obsahuje názvy všech místních proměnných v aktuálním oboru. Uzel sady mají ovládacím prvkem strom, který je můžete přejít na najdete v jejích podsložkách.

 **Hodnota**

 Tento sloupec zobrazuje hodnota obsažená v každé proměnné. Atribut zpracování instrukce, komentáře, text a CData uzlů zobrazovat textové hodnoty uzlu. Uzly Namespace zobrazit identifikátor URI oboru názvů.

 **Typ**

 V tomto sloupci určuje datový typ uvedených v proměnných **název** sloupce.

 V okně místních hodnot také zobrazí předdefinovaný kontextové proměnné, které sledují kontextu transformace XSLT. Následující tabulka popisuje předdefinované kontextové proměnné použít ladicí program XSLT.

|Název|Popis|
|-|-----------------|
|`last()`|Velikost kontextu.|
|`position()`|Pozici nebo číslo indexu, vzhledem k velikosti kontextu kontextu uzlu.|
|`self::node()`|Hodnota kontextu uzlu.|

## <a name="output-window"></a>Výstup – okno
 V okně výstupu se zobrazí všechny chybové zprávy nebo zabezpečení, ke kterým dochází během ladění.

 Ladicí program XSLT používá samostatné okno k zobrazení výstupu ladicího programu. Toto je stejné okno sloužící k zobrazení výstupu z **zobrazení výstupu XSL** příkazu.

## <a name="task-list"></a>Seznam úloh
 **Seznamu úkolů** zobrazí seznam všech chyb kompilace v šabloně stylů. Poklepáním chybu přesměruje kurzor na řádku s chybou.

 **Seznamu úkolů** zahrnuje všechny chyby, ke kterým dochází v blocích skriptu v souboru XSLT.

> [!NOTE]
> Ladicí program XSLT nemá žádná varování, tak se nikdy objeví v **seznamu úkolů**.

## <a name="breakpoints-window"></a>Zarážky – okno
 V okně zarážek se zobrazí všechny zarážky nastavené v aktuálním projektu. Pokud přidáte zarážku v okně je v zobrazení, v okně automaticky aktualizuje a zobrazí novou zarážku.

 V okně zarážek by se měly chovat stejně jako ostatní ladicích programů sady Visual Studio.

## <a name="command-windowimmediate-window"></a>Příkazové okno a okamžité okno
 V této verzi ladicí program XSLT není implementováno.

## <a name="watch-window"></a>Kukátko – okno
 V okně kukátko se používá k vyhodnocení proměnné. Můžete také změnit hodnoty proměnných.

 Proměnné zobrazí v okně kukátka jsou pro aktuální kontext (položka úplně nahoře v zásobníku volání). Pokud změníte kontext, okna kukátka aktualizuje a zobrazí proměnné nastavené pro tento kontext.

## <a name="call-stack-window"></a>okno Zásobník volání
 **Zásobník volání** okno se používá k zobrazení názvy funkcí v zásobníku volání, typy parametrů a hodnot parametrů. Informace v zásobníku volání se zobrazí, pouze pokud laděnému programu je ve stavu přerušení.

 Zásobník volání představuje různé kontexty, které právě probíhá zpracování XSLT. Například, pokud je volání z šablony "a" do šablony "b", šablona "a" a zobrazí se v šabloně "b" **zásobník volání** okno s aktuálním kontextu na začátek seznamu. Uživatel se může zobrazit dotaz, který aktuálně spouští.

 Pokud se šablony nemají název v souboru XSLT, se používají názvy generovaných procesoru XSLT.

 Kliknutí na položku než v horní části seznamu označuje do prohlížeče, kde větev provedení transformace XSLT pomocí standardní zelené zvýraznění se stalo a zelené šipky.

## <a name="quickwatch-dialog-box"></a>QuickWatch – dialogové okno
 **QuickWatch** dialogové okno se používá k vyhodnocení výrazů XPath 1.0. Kontextový uzel ( `self::node()` uzel v okně místní hodnoty) poskytuje kontext pro provádění výrazu XPath. Výsledek provedení výraz XPath se zobrazí v okně kukátko.

 Následující seznam popisuje některé omezení pro vyhodnocení výrazu XPath.

-   Jsou povoleny pouze integrované funkce XPath.

-   XSLT integrované funkce, jako například `document()`, `key()`, a tak dále, nejsou povoleny.

-   Uživatelem definované funkce nejsou povoleny.

Další informace najdete v tématu [jak: Vyhodnocení výrazu XPath](../xml-tools/how-to-evaluate-an-xpath-expression.md).

## <a name="disassembly-window"></a>okno Zpětný překlad
 V okně zpětný překlad zobrazí kód sestavení generovaný kompilátorem XSLT. Toto okno lze použít stejně jako všechny ostatní okna zpětného překladu sady Visual Studio.

 Další informace najdete [jak: Použití okna zpětného překladu](../debugger/how-to-use-the-disassembly-window.md).

## <a name="see-also"></a>Viz také:

- [Ladění XSLT](../xml-tools/debugging-xslt.md)
- [První seznámení s ladicím programem](../debugger/debugger-feature-tour.md)
- [Kontrolovat proměnné v okně Automatické hodnoty a místní hodnoty v sadě Visual Studio](../debugger/autos-and-locals-windows.md)