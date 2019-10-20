---
title: 'Postupy: zobrazení a úpravy kódu pomocí funkce Náhled definice (Alt + F12) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 45f3dd20-902a-4047-8cca-9f18216123f4
caps.latest.revision: 20
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 40772919031200466999df2dfbf651fae3ee01e7
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72670572"
---
# <a name="how-to-view-and-edit-code-by-using-peek-definition-altf12"></a>Postupy: Zobrazení a úpravy kódu s použitím funkce Náhled definice (ALT+F12)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pomocí příkazu **Náhled definice** můžete zobrazit a upravit kód bez přepínání mimo kód, který píšete. **Náhled definice** a **Přejít k definici** zobrazí stejné informace, ale **Náhled definice** je zobrazí v místním okně a **Přejít k definici** zobrazuje kód v samostatném okně kódu. **Přejít k definici** způsobí, že váš kontext (tj. aktivní okno kódu, aktuální řádek a pozice kurzoru) přepne do okna kód definice. Pomocí **náhledu definice**můžete zobrazit a upravit definici a přesunout se v rámci souboru definice a přitom zachovat místo v původním souboru kódu.

 Můžete použít **Náhled definice** s C#, Visual Basic a C++ Code. V Visual Basic **Náhled definice** zobrazuje odkaz na **Prohlížeč objektů** pro symboly, které nemají metadata definice (například .NET Framework typů, které jsou integrovány).

> [!IMPORTANT]
> Tento příkaz nelze použít v žádné verzi Express sady Visual Studio 2013.

## <a name="working-with-peek-definition"></a>Práce s náhledem definice

#### <a name="to-open-a-peek-definition-window"></a>Otevření okna Náhled definice

1. **Náhled definice** můžete najít tak, že otevřete místní nabídku pro metodu, kterou chcete prozkoumat. (Klávesnice: Alt+F12)

     Tento obrázek ukazuje okno **Náhled definice** pro metodu s názvem `Print()`:

     ![Náhled okna](../ide/media/peekwindow.png "PeekWindow")

     Okno definice se zobrazí pod `printer.Print(“Hello World!”)`m řádkem v původním souboru. Okno neskryje žádný kód v původním souboru. Řádky, které následují volání `printer.Print(“Hello World!”)`, se zobrazí pod oknem definice.

2. Kurzor můžete přesunout na jiné místo v okně definice kódu. Můžete se i nadále pohybovat v původním okně kódu nad nebo pod oknem definice.

3. Můžete zkopírovat řetězec v okně definice a vložit ho do původního kódu. Můžete také přetáhnout řetězec z okna definice do původního kódu, aniž by byl v okně definice odstraněn.

4. Okno definice můžete zavřít kliknutím na klávesu ESC nebo tlačítkem **Zavřít** na kartě okno definice.

#### <a name="to-open-a-peek-definition-window-from-within-a-peek-definition-window"></a>Otevření okna Náhled definice z okna Náhled definice

- Pokud již máte otevřené okno **Náhled definice** , můžete znovu zavolat **Náhled definice** na kód v tomto okně. Otevře se jiné okno definice. Vedle karty okna definice se zobrazí sada teček s popisem cesty, která slouží k navigaci mezi okny definice. Popisek tlačítka na každé tečce zobrazuje název souboru a cestu k souboru definice, který tečka přestavuje.

     ![Náhled okna v náhledu](../ide/media/peekwithinpeek.png "PeekWithinPeek")

#### <a name="to-use-peek-definition-with-multiple-results"></a>Použití náhledu definice s více výsledky

- Použijete-li **Náhled definice** v kódu, který má více než jednu definici (například částečné třídy), seznam výsledků se zobrazí napravo od zobrazení definice kódu. Můžete zvolit některý z výsledků v seznamu k zobrazení jeho definice.

     ![Náhled okna z více výsledků](../ide/media/peekmultiple.png "PeekMultiple")

#### <a name="to-edit-inside-the-peek-definition-window"></a>Provádění úprav v okně Náhled definice

- Když začnete upravovat v okně **Náhled definice** , soubor, který upravujete, se automaticky otevře jako samostatná karta v editoru kódu a projeví se změny, které jste již provedli. V okně **Náhled definice** můžete dál dělat, vracet a ukládat změny a karta bude tyto změny dál zobrazovat. I když toto okno zavřete bez uložení změn, lze na této kartě provádět, rušit a ukládat změny, což vás přenese přesně tam, kde jste v tomto okně skončili.

     ![Úpravy v náhledu okna](../ide/media/peekedit.png "PeekEdit")

#### <a name="to-use-keyboard-shortcuts-for-peek-definition"></a>Použití klávesových zkratek pro náhled definice

- Tyto klávesové zkratky můžete použít v okně **Náhled definice** :

    |Funkce|Klávesová zkratka|
    |-------------------|-----------------------|
    |Otevřít okno definice|Alt+F12|
    |Zavřít okno definice|Esc|
    |Povýšit okno definice na běžnou kartu dokumentu|Shift+Alt+Home|
    |Navigace mezi okny definice|Ctrl+Alt+- a Ctrl+Alt+=|
    |Navigace mezi několika výsledky|F8 a Shift+F8|
    |Přepnout mezi oknem editoru kódu a oknem definice|Shift+Esc|

    > [!NOTE]
    > Můžete také použít stejné klávesové zkratky pro úpravu kódu v okně **Náhled definice** při použití jinde v aplikaci Visual Studio.

## <a name="see-also"></a>Viz také
 [Tipy pro vyšší produktivitu](../ide/productivity-tips-for-visual-studio.md)
