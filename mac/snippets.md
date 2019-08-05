---
title: Fragmenty kódu
description: Jak používat fragmenty kódu k efektivnímu programování v Visual Studio pro Mac
author: cobey
ms.author: cobey
ms.date: 02/07/2019
ms.assetid: 0FE27C0C-A861-4133-A74E-8D0505CF5342
ms.openlocfilehash: 1dacc935549d738ff1b5e84c3ac4420c343155fd
ms.sourcegitcommit: a124076dfd6b4e5aecda4d01984fee7b0c034745
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2019
ms.locfileid: "68787689"
---
# <a name="code-snippets"></a>Fragmenty kódu

Fragmenty kódu, často označované jako _šablony kódu_, jsou užitečné pro efektivní programování, protože umožňují vkládání a úpravy předem zapsaných bloků kódu. Používání fragmentů kódu může být pohodlné pro rychlé přidávání běžných vzorů nebo dokonce i pro učení nových vzorů, pokud vývojář si nejste jisti syntaxí. K dispozici jsou šablony C#pro F#,, HTML, XML, Python a Razor.

Tato část vysvětluje, jak vytvářet, vkládat a používat fragmenty kódu v kódu.

## <a name="inserting-a-snippet"></a>Vložení fragmentu

Existují různé způsoby, jak přidat fragmenty kódu, některé z nich jsou popsány níže:

- **Rozšíření karty** Začněte psát název šablony, vyberte ji ze seznamu a stiskněte klávesu **TAB**a **kartu přidejte:** &ndash;

  ![Rozšíření tabulátoru v kódu](media/source-editor-image13.png)

- **Sada nástrojů** &ndash; Pomocí panelu nástrojů zobrazte seznam všech fragmentů kódu. Přetáhněte libovolnou šablonu ze sady nástrojů do správné pozice ve zdrojovém kódu:

  [![Fragmenty kódu v sadě nástrojů](media/source-editor-image14-sml.png)](media/source-editor-image14.png#lightbox)

- **Vložit šablony – příkaz** &ndash; Pro vložení šablony není aktuálně k dispozici žádná výchozí sada vazeb klíčů. Pokud ho chcete vytvořit, přejděte do sady **Visual Studio > předvolby > klíčové vazby** a `template`vyhledejte. To umožňuje přidat požadovanou vazbu klíče do pole Upravit vazbu a pak kliknout na **použít**:

  ![Příkaz vsazení Template](media/source-editor-image15.png)

## <a name="creating-a-new-template"></a>Vytvoření nové šablony

I když existuje mnoho existujících šablon v různých jazycích, které lze použít a upravit, lze přidat nové šablony také tak, že přejdete do sady **Visual Studio > předvolby > textový Editor > fragmenty kódu**:

![Odkrýt novou šablonu](media/source-editor-image12.png)

Chcete-li vytvořit nebo upravit fragmenty, stiskněte tlačítko **Přidat** nebo **Upravit** .

## <a name="keywords-in-code-snippets"></a>Klíčová slova v fragmentech kódu

Po vložení fragmentu kódu do editoru jsou všechna definovaná klíčová slova zvýrazněna a lze je upravit pomocí tabulátorů mezi nimi. Klíčová slova se chovají jako "proměnná" ve fragmentu kódu a jsou definovány umístěním znaku `$` dolaru před a za názvem klíčového slova. 

V následujícím seznamu se zobrazí okno **Upravit šablonu** , ve kterém se upraví vestavěný `prop` fragment kódu. Fragment kódu obsahuje dvě klíčová `$name$` slova &ndash; `$type$` a &ndash; na pravé straně okna můžou mít nastavené další vlastnosti (například výchozí hodnotu a popis):

![Okno Upravit šablonu](media/source-editor-image12z.png)

Následující pole slouží k definování fragmentu:

- **Zástupce** &ndash; Text, který uživatel zadá pro vložení fragmentu.
- **Skupina** &ndash; Fragmenty kódu jsou seskupeny dohromady v nabídce obsah fragmentů, a to pomocí této hodnoty.
- **Popis** &ndash; Vysvětlení účelu fragmentu
- **MIME** &ndash; Určuje typy souborů, ve kterých je fragment kódu k dispozici.
- **Je rozšiřitelná šablona** &ndash; Ujistěte se, že je toto políčko zaškrtnuté, aby se fragment kódu mohl vložit na kurzor zadáním zástupce.
- **Je obklopen šablonou** Tuto možnost zaškrtnete, pokud chcete tento zástupce zobrazit v nabídce **Surround with...** Content v editoru. &ndash;
- **Text šablony** &ndash; Skutečný fragment kódu, který bude vložen do editoru. Zástupné symboly klíčového slova lze definovat v rámci tokenu s označením dolaru. `$type$`.
- **Panel vlastností klíčového slova** Na pravé straně okna pomocí rozevíracího seznamu v horní části vyberte klíčové slovo (například `type`) a upravte vlastnosti, jako je například výchozí hodnota a popis. &ndash;

## <a name="using-keywords-in-the-editor"></a>Použití klíčových slov v editoru

Chcete-li použít fragment kódu s klíčovými slovy, jako je například definováno výše, zadejte zástupce a stiskněte klávesu **TAB** dvakrát a obsah fragmentu bude vložen na kurzor:

![Vložený fragment znázorňující klíčová slova](media/source-editor-image12a.png)

Stiskněte klávesu **tabulátor** pro pohyb mezi `object` a `MyProperty` k přizpůsobení fragmentu pro vaši třídu.

Klíčové slovo se může opakovat ve fragmentu, například v tomto `for` příkladu, Všimněte si `$i$` , že klíčové slovo se zobrazí třikrát:

![Šablona fragmentu s opakovanými klíčovými slovy](media/source-editor-image12b.png)

Při použití v editoru se klávesa **TAB** přepíná mezi prvními `i` a `max`. Pokud převedete `i` na jiný název proměnné, aktualizují se všechny tři instance:

![Vložený fragment zobrazující více klíčových slov](media/source-editor-image12c.png)

### <a name="reserved-keywords"></a>Vyhrazená klíčová slova

Existují dvě vyhrazená klíčová slova, která lze použít ve fragmentu:

- `$selected$`Pokud je fragment kódu ohraničený zaškrtnutou šablonou, toto klíčové slovo bude nahrazeno textem zvýrazněným v editoru při výběru fragmentu. &ndash;
- `$end$`Když uživatel dokončil úpravy klíčových slov ve fragmentu, kurzor se umístí do umístění `$end$` klíčového slova. &ndash;

`for` Fragment kódu v předchozí části je příkladem obou vyhrazených klíčových slov.

## <a name="see-also"></a>Viz také:

- [Fragmenty kódu (Visual Studio ve Windows)](/visualstudio/ide/code-snippets)
