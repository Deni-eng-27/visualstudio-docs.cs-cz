---
title: "Úpravy Python kódu v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 07/10/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 016ba0478ace36dc9492641dcb95f793cdda5fb7
ms.sourcegitcommit: f36eb7f989efbdbed0d0a087afea8ffe27d8ca15
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/14/2017
---
# <a name="editing-python-code"></a>Úpravy kódu jazyka Python

Vývojáři stráví velkou část doba pro jejich v editoru kódu, takže [Python podporují v sadě Visual Studio](installation.md) poskytuje funkce, které vám pomohou být produktivnější. Funkce zahrnují IntelliSense zvýraznění syntaxe, automatické doplňování, podpis Nápověda, metoda přepsání, hledání a navigace. 

V tomto tématu:

- [IntelliSense](#intellisense) včetně dokončených, podpis Nápověda, rychlé informace a barevné zvýrazňování kódu.
- [Fragmenty kódu](#code-snippets)
- [Procházení kódu](#navigating-your-code)

Obecné dokumentaci na úpravy kódu v sadě Visual Studio najdete v tématu [psaní kódu v editoru kódu a textovém editoru](../ide/writing-code-in-the-code-and-text-editor.md). Viz také [osnovy v sadě Visual Studio](../ide/outlining.md), což vám usnadní zaměřené na konkrétní části kódu. Podpora Python zahrnuje použití prohlížeče objektů Visual Studio (**zobrazení > ostatní okna > Prohlížeč objektů** nebo Ctrl + W, J) pro zkontrolujete tříd definovaných v každé modulu a funkce definované v těchto tříd. 

Editor integrována se interaktivních okna v sadě Visual Studio, což usnadňuje exchange kód mezi nimi. Najdete v části [kurzu krok 3: použití okna interaktivní REPL](vs-tutorial-01-03.md) a [pomocí okna interaktivní - odeslání kódu interaktivního příkazu](interactive-repl.md#send-code-to-interactive-command) podrobnosti.

Úvod k úpravám kód Python, najdete v části [kód Python úpravy](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=r2iQH5LWE_4605918567) (Microsoft Virtual Academy, 2m30s):

> [!VIDEO https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Editing-Python-Code-r2iQH5LWE_4605918567]

## <a name="intellisense"></a>IntelliSense

Poskytuje IntelliSense [dokončených](#completions), [podpis nápovědy](#signature-help), [rychlé informace](#quick-info), a [barevné zvýrazňování kódu](#code-coloring). Chcete-li zvýšit výkon, IntelliSense závisí na databázi dokončení, který se vygeneruje pro každé prostředí Python ve vašem projektu. Databáze může být potřeba aktualizovat, je-li přidat, odebrat nebo aktualizovat balíčky. Stav databáze se zobrazuje v **prostředí Python** okno (na stejné úrovni jako Průzkumník řešení) na **IntelliSense** karta (najdete v části [prostředí Python](python-environments.md)). 

### <a name="completions"></a>Dokončování

Dokončování se zobrazí jako příkazy, identifikátory a ostatní slova, která může být zadány správně aktuální umístění v editoru. Co se zobrazí v seznamu je na základě kontextu a je filtrovaná vynechejte nesprávné nebo rušivě možnosti. Dokončování často aktivaci zadáním jiné příkazy (například `import`) a operátory (včetně dobou), ale může mít je zobrazí kdykoli zadáním Ctrl-J, místo.

![Člen dokončení](media/code-editing-completions-simple.png)

V otevřeném seznamu dokončení, můžete hledat na dokončení můžete určit pomocí klávesy se šipkami, myši, nebo pokračovat v psaní. Jak budete zadávat více znaků, seznam je filtrovaný Další zobrazíte pravděpodobně dokončování. Zástupce můžete také použít jako:

- Zadáním písmena, které nejsou na začátku názvu, jako je například "analýzy, najít 'argparse.
- Zadáním pouze písmena, které jsou na začátku slova, jako jsou "abc" najít "AbstractBaseClass" nebo "vzduchem" najít 'as_integer_ratio.
- Přeskočení písmena, například "b64' najít 'base64.

Příklady:

![Dokončení člena s filtrováním](media/code-editing-completion-filtering.png)

Při zadejte tečku za hodnotu, společně s metody a atributy potenciální typů nebo proměnná se automaticky zobrazí dokončených člen. Pokud proměnná může být více než jeden typ, seznam obsahuje všechny možnosti ze všech typů s doplňující informace k označení, které typy podporovat každé dokončení. Tam, kde je dokončení podporovány všechny možné typy, se zobrazí bez poznámky.

![Dokončení člena na více typů](media/code-editing-completion-types.png)

Ve výchozím nastavení "dunder" členy (členy počáteční a koncové s dvojité podtržítko) nejsou zobrazeny. Obecně platí tito členové by neměl být k nim přistupuje přímo. Pokud budete potřebovat jeden, ale zadáním začátku dvojité podtržítko přidá tyto dokončených do seznamu:

![Dokončení privátního člena](media/code-editing-completion-dunder.png)

`import` a `from ... import` příkazy Zobrazit seznam modulů, které lze importovat. S `from ... import`, seznam obsahuje členy, které lze importovat z zadaný modul.

![Dokončení importu](media/code-editing-completion-import.png)

`raise` a `except` příkazy Zobrazit seznam třídy, které mohou být typů chyb. V seznamu nemusí zahrnovat všechny uživatelem definované výjimky, ale vám pomůže rychle najít vhodný předdefinované výjimky:

![Dokončení výjimky](media/code-editing-completion-exception.png)

Zadáním spustí dekoratéra a zobrazuje potenciální dekorátory. Mnoho z těchto položek nejsou použitelné jako dekoratéry; Zkontrolujte dokumentaci ke knihovně k určení, který se použije.

![Dokončení dekoratéra](media/code-editing-completion-decorator.png)

> [!Tip]
> Můžete nakonfigurovat chování dokončených prostřednictvím **nástroje > Možnosti > textový Editor > Python > Upřesnit "**. Mezi tyto **seznam filtrů podle hledaný řetězec**: použije filtry dokončení návrhů při psaní (výchozím nastavení je zaškrtnuto), a **dokončení člen zobrazí průnik členů** se zobrazí pouze dokončování operací, které jsou podporovány všechny možné typy (výchozí nastavení je zaškrtnuté políčko). V tématu [možnosti - dokončení výsledky](options.md#completion-results).

### <a name="signature-help"></a>Podpis nápovědy

Při psaní kódu, který volá funkci, podpis nápovědy se zobrazí, když zadáte otevření `(` a zobrazí informace o dostupné dokumentaci a parametr. Můžete také nastavit zobrazí s Ctrl + Shift + mezerník uvnitř volání funkce. Informace zobrazené závisí na dokumentaci řetězce ve zdrojovém kódu funkce, ale zahrnuje všechny výchozí hodnoty.

![Podpis nápovědy](media/code-editing-signature-help.png)

> [!Tip]
> Chcete-li zakázat podpis nápovědy, přejděte na **nástroje > Možnosti > textový Editor > Python > Obecné** a zrušte zaškrtnutí **dokončování > informace o parametrech**.

### <a name="quick-info"></a>Rychlé informace

Ukazatele ukazatel myši nad identifikátor zobrazí popisek rychlé informace. V závislosti na identifikátor rychlé informace může zobrazit na potenciální hodnoty nebo typy, dostupnou dokumentaci, vrátí typy a definice umístění:

![Rychlé informace](media/code-editing-quick-info.png)

### <a name="code-coloring"></a>Barevné zvýrazňování kódu

Barevné zvýrazňování kód používá informace z analýza kódu do proměnné barvy, příkazy a další části kódu. Například proměnné, které odkazují na moduly nebo třídy se může zobrazit v barvu než funkce nebo jiné hodnoty, a názvy parametrů, zobrazují v barvu než místní nebo globální proměnné. (Ve výchozím nastavení, nejsou zobrazeny funkce tučným písmem):

![Barevné zvýrazňování kódu](media/code-editing-code-coloring.png)

Chcete-li přizpůsobit barvy, přejděte na **nástroje > Možnosti > prostředí > písma a barev** a změnit Python položky v **zobrazení položek** seznamu:

![Možnosti písma a barev](media/code-editing-customize-colors.png)

> [!Tip]
> Kód zvýrazňování zakázat, přejděte na **nástroje > Možnosti > textový Editor > Python > Upřesnit** a zrušte zaškrtnutí **různé možnosti > Barva názvy založený na typu**. V tématu [možnosti - různé možnosti](options.md#miscellaneous-options).


## <a name="code-snippets"></a>Fragmenty kódu

Fragmenty kódu jsou fragmenty kódu, kterou lze vložit do souborů zadáním zástupce a stisknutím klávesy Tab nebo pomocí **Upravit > IntelliSense > Vložit fragment kódu** **příkazu Obklopit s** příkazy. Například zadáním `class` a kartou, vygeneruje klíč rest třídy. Přepište název a základů seznamu přesun mezi zvýrazněná pole s kartě, stiskněte klávesu Enter pro zadávání textu.

![Fragmenty kódu](media/code-editing-code-snippets.png)

Můžete zobrazit fragmenty kódu k dispozici ve Správci fragmentů kódu (**nástroje > Správce fragmentů kódu**), vyberete **Python** jako jazyk:

![Správce fragmentů kódu](media/code-editing-code-snippets-manager.png)

Pokud chcete vytvořit vlastní fragmenty, najdete v části [návod: Vytvoření fragmentu kódu](../ide/walkthrough-creating-a-code-snippet.md). 

Pokud píšete fragment skvělé kódu, který chcete sdílet, klidně odeslat v gist a [dejte nám vědět](https://github.com/Microsoft/PTVS/issues). Jsme pravděpodobně možné zahrnout do budoucích vydání sady Visual Studio.


## <a name="navigating-your-code"></a>Procházení kódu

Podpora jazyka Python v sadě Visual Studio poskytuje několik způsob, jak rychle přejděte v kódu, včetně knihovny, pro které zdrojový kód je k dispozici: [navigační panel](#navigation-bar), [přejít k definici](#go-to-definition), [Přejděte na](#navigate-to), a [najít všechny odkazy](#find-all-references). Visual Studio můžete také použít [Prohlížeč objektů](../ide/viewing-the-structure-of-code.md#BKMK_ObjectBrowser).

### <a name="navigation-bar"></a>Navigační panel

Na navigačním panelu se zobrazí v horní části každé okno editoru a zahrnuje dvě úrovně seznam definic. Vlevo rozevírací seznam obsahuje třídy nejvyšší úrovně a definice funkcí v aktuální soubor; pravé rozevíracího seznamu zobrazí seznam definic v rámci oboru ukazuje na levé straně. Při procházení v editoru, seznamy aktualizují a zobrazují aktuální kontext a můžete také vybrat položku z tyto seznamy přejít přímo na v.

![Navigační panel](media/code-editing-navigation-bar.png)

> [!Tip]
> Skrytí navigačního panelu, přejděte na **nástroje > Možnosti > textový Editor > Python > Obecné** a zrušte zaškrtnutí **Nastavení > Navigační panel**.

### <a name="go-to-definition"></a>Přechod na definici

**Přejít k definici** rychle přejde z používání identifikátoru (například název funkce, třída nebo proměnná), zdrojový kód je-li definován. Vyvolání identifikátor kliknete pravým tlačítkem a výběrem **přejít k definici** nebo umístění znak v identifikátoru a stisknutím klávesy F12. Funguje napříč kód a externí knihovny za předpokladu, že zdrojový kód je k dispozici. Pokud není k dispozici, zdrojový kód knihovny **přejít k definici** přejde do odpovídajícího `import` příkaz pro odkaz na modul, nebo zobrazení k chybě.

![Přechod na definici](media/code-editing-go-to-definition.png)

### <a name="navigate-to"></a>Přejděte na

**Upravit > přejděte do...**  příkaz (Ctrl čárkou) zobrazí v editoru, kde můžete zadat libovolný řetězec a zjistit možné shody ve vašem kódu, který definuje funkci, třída nebo proměnné, který tento řetězec obsahuje vyhledávací pole. Tato funkce poskytuje podobné funkce jako **přejít k definici** , ale bez nutnosti najít pomocí identifikátoru.

Dvakrát klikněte na libovolný název, nebo vyberte pomocí klávesy se šipkami a Enter, přejde na definici tohoto identifikátoru.

![Přejděte na](media/code-editing-navigate-to.png)

### <a name="find-all-references"></a>Najít všechny odkazy

**Najít všechny odkazy** je užitečné způsob zjišťování, kde i jakékoli daným identifikátorem je definovaný a použít, včetně importy a přiřazení. Vyvolání identifikátor kliknete pravým tlačítkem a výběrem **najít všechny odkazy**, nebo umístění znak v identifikátoru a stisknutím klávesy Shift + F12. Dvakrát klikněte na položku v seznamu přejde na jeho umístění.

![Najít všechny odkazy na výsledky](media/code-editing-find-all-references.png)