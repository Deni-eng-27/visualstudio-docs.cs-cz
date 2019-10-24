---
title: Použití map kódu k ladění aplikací
ms.date: 09/28/2018
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio Ultimate, visualizing code
- Visual Studio Ultimate, navigating code visually
- Visual Studio Ultimate, understanding code
- Visual Studio Ultimate, mapping code relationships
- Visual Studio Ultimate, code maps
- mapping code relationships
- code maps
- mapping relationships in code
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d0b3c65c0a7e5cb08869a6d756ce0c443fa3bf2e
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2019
ms.locfileid: "72748277"
---
# <a name="use-code-maps-to-debug-your-applications"></a>Použití map kódu k ladění aplikací

Mapy kódu vám mohou přispět k tomu, abyste se ztratili v rozsáhlých základech kódu, neznámém kódu nebo starším kódu. Například při ladění může být nutné podívat se na kód v mnoha souborech a projektech. Pomocí map kódu se můžete pohybovat v jednotlivých částech kódu a pochopit vztahy mezi nimi. Tímto způsobem není nutné sledovat tento kód ve vaší hlavě nebo nakreslit samostatný diagram. Takže když dojde k přerušení práce, mapy kódu vám pomůžou aktualizovat vaši paměť o kódu, se kterým pracujete.

![Vztahy mapy &#45; mapy kódu v kódu](../modeling/media/codemapstoryboardpaint.png)

**Zelená šipka ukazuje, kde se kurzor zobrazuje v editoru.**

Podrobnosti o příkazech a akcích, které můžete použít při práci s mapami kódu, naleznete v tématu [procházení a změna uspořádání map kódu](../modeling/browse-and-rearrange-code-maps.md).

> [!NOTE]
> Chcete-li vytvářet a upravovat mapy kódu, potřebujete Visual Studio Enterprise edici. V edicích Visual Studio Community a Professional můžete otevřít diagramy vygenerované v Enterprise Edition, ale nemůžete je upravovat.

## <a name="understand-the-problem"></a>Pochopení problému
 Předpokládejme, že je chyba v programu kreslení, na kterém právě pracujete. Chcete-li reprodukování chyby, otevřete řešení v aplikaci Visual Studio a stisknutím klávesy **F5** spusťte ladění.

 Když nakreslíte čáru a kliknete na tlačítko **vrátit poslední tah**, nic se nestane, dokud nebudete kreslit další řádek.

 ![Chyba reprodukci &#45; mapy kódu](../modeling/media/codemapstoryboardpaint0.png)

 Pokud chcete začít prozkoumat, vyhledejte metodu `Undo`. Najdete ho ve třídě `PaintCanvas`.

 ![Vyhledání kódu &#45; v mapě kódu](../modeling/media/codemapstoryboardpaint1.png)

## <a name="start-mapping-the-code"></a>Spuštění mapování kódu
 Nyní spusťte mapování metody `undo` a jejích vztahů. V editoru kódu přidejte metodu `undo` a pole, na která odkazuje, na novou mapu kódu. Když vytvoříte nové mapování, může zaindexování kódu trvat nějakou dobu. To pomáhá rychlejšímu běhu pozdějších operací.

 ![Mapa &#45; kódu – zobrazit metodu a související pole](../modeling/media/codemapstoryboardpaint3.png)

> [!TIP]
> Zelené zvýraznění zobrazí poslední položky, které byly přidány do mapy. Zelená šipka ukazuje pozici kurzoru v kódu. Šipky mezi položkami představují různé vztahy. Můžete získat další informace o položkách v mapě přesunutím myši na ně a prozkoumáním jejich popisků.

 ![Mapa &#45; kódu – zobrazit popisy tlačítek](../modeling/media/codemapstoryboardpaint4.png)

## <a name="navigate-and-examine-code-from-the-map"></a>Procházení a zkoumání kódu z mapy
 Chcete-li zobrazit definici kódu pro každé pole, dvakrát klikněte na pole na mapě nebo vyberte pole a stiskněte klávesu **F12**. Zelená šipka se přesune mezi položkami na mapě. Kurzor v editoru kódu se také přesune automaticky.

 ![Definice pole &#45; prověření mapy kódu](../modeling/media/codemapstoryboardpaint5.png)

 ![Definice pole &#45; prověření mapy kódu](../modeling/media/codemapstoryboardpaint5a.png)

> [!TIP]
> Zelenou šipku na mapě můžete také přesunout přesunutím kurzoru v editoru kódu.

## <a name="understand-relationships-between-pieces-of-code"></a>Pochopení vztahů mezi částmi kódu
 Nyní chcete zjistit, který jiný kód komunikuje s poli `history` a `paintObjects`. Můžete do mapy přidat všechny metody, které odkazují na tato pole. To lze provést z mapy nebo z editoru kódu.

 ![Mapa &#45; kódu – najít všechny odkazy](../modeling/media/codemapstoryboardpaint6.png)

 ![Otevření mapy kódu z editoru kódu](../modeling/media/codemapstoryboardpaint6a.png)

> [!NOTE]
> Pokud přidáte položky z projektu, který je sdílen mezi více aplikacemi, například Windows Phone nebo Windows Store, pak se tyto položky vždy zobrazí s aktuálně aktivním projektem aplikace na mapě. Takže pokud změníte kontext na jiný projekt aplikace, pak kontext na mapě také změní všechny nově přidané položky ze sdíleného projektu. Operace, které provádíte s položkou na mapě, se vztahují pouze na ty položky, které sdílejí stejný kontext.

 Změňte rozložení a uspořádejte tak tok vztahů a usnadněte čtení z mapy. Položky kolem mapy lze také přesunout přetažením.

 ![Rozložení změny &#45; mapy kódu](../modeling/media/codemapstoryboardpaint7a.png)

> [!TIP]
> Ve výchozím nastavení je **přírůstkové rozložení** zapnuté. To při přidání nových položek mění uspořádání mapy co nejméně. Chcete-li změnit uspořádání celé mapy při každém přidání nových položek, vypněte **přírůstkové rozložení**.

 ![Rozložení změny &#45; mapy kódu](../modeling/media/codemapstoryboardpaint7.png)

 Podívejme se na tyto metody. Na mapě poklikejte na metodu **PaintCanvas** , nebo vyberte tuto metodu a stiskněte klávesu **F12**. Zjistíte, že tato metoda vytváří `history` a `paintObjects` jako prázdné seznamy.

 ![Kontrola mapy &#45; kódu – definice metody](../modeling/media/codemapstoryboardpaint8.png)

 Nyní opakujte stejný postup k prohlédnutí definice `clear` metody. Naučíte se, že `clear` provádí některé úkoly s `paintObjects` a `history`. Pak zavolá metodu `Repaint`.

 ![Kontrola mapy &#45; kódu – definice metody](../modeling/media/codemapstoryboardpaint9.png)

 Teď si Projděte definici metody `addPaintObject`. Provádí také některé úkoly s `history` a `paintObjects`. Také volá `Repaint`.

 ![Kontrola mapy &#45; kódu – definice metody](../modeling/media/codemapstoryboardpaint10.png)

## <a name="find-the-problem-by-examining-the-map"></a>Nalezení příčiny problému prozkoumáním mapy
 Zdá se, že všechny metody, které mění `history` a `paintObjects` volání `Repaint`. Přesto metoda `undo` nevolá `Repaint`, i když `undo` mění stejná pole. Proto si myslíte, že tento problém můžete vyřešit voláním `Repaint` z `undo`.

 ![Mapa &#45; kódu – najít chybějící volání metody](../modeling/media/codemapstoryboardpaint11.png)

 Pokud by nebyla nastavena mapa k zobrazení tohoto chybějícího volání, mohlo by být nalezení tohoto problému obtížnější, zejména u složitějšího kódu.

## <a name="share-your-discovery-and-next-steps"></a>Sdílení zjištění a další kroky
 Předtím, než vy nebo někdo jiný tuto chybu vyřeší, si můžete dělat na mapě poznámky o problému a způsobu jeho řešení.

 ![Komentáře a &#45; označení položek mapy kódu pro zpracování](../modeling/media/codemapstoryboardpaint12.png)

 Můžete například přidat komentáře do mapy a označit položky pomocí barev.

 ![Mapa &#45; kódu s komentářem a položky s příznakem](../modeling/media/codemapstoryboardpaint12a.png)

 Pokud máte nainstalovanou aplikaci Microsoft Outlook, můžete mapu e-mailem odeslat ostatním. Mapu taky můžete exportovat jako obrázek nebo jiný formát.

 ![Sdílená &#45; složka, export, pošta mapy kódu](../modeling/media/codemapstoryboardpaint13.png)

## <a name="fix-the-problem-and-show-what-you-did"></a>Vyřešení problému a zobrazení provedené činnosti
 Chcete-li tuto chybu vyřešit, přidejte volání `Repaint` pro `undo`.

 ![Mapa &#45; kódu – přidat chybějící volání metody](../modeling/media/codemapstoryboardpaint14.png)

 Chcete-li potvrdit svou opravu, restartujte relaci ladění a zkuste chybu reprodukovat. Nyní volba **vrátit zpět poslední tah** funguje podle očekávání a potvrdí, že jste provedli správnou opravu.

 ![Kontrola kódu &#45; potvrdit opravu kódu](../modeling/media/codemapstoryboardpaint15.png)

 Můžete aktualizovat mapu, aby zobrazovala provedené opravy.

 ![Mapa aktualizace &#45; mapy kódu s chybějícím voláním metody](../modeling/media/codemapstoryboardpaint16.png)

 Vaše mapa nyní zobrazuje propojení mezi **akcemi zpět** a **repaint**.

 ![Mapa kódu &#45; aktualizovala mapu pomocí volání metody](../modeling/media/codemapstoryboardpaint17.png)

> [!NOTE]
> Při aktualizaci mapy se může zobrazit zpráva, že byl aktualizován index kódu použitý k vytvoření mapy. To znamená, že někdo změnil kód, což způsobilo, že se vaše mapa neshoduje s aktuálním kódem. To vám nezabrání v aktualizaci mapy, ale chcete-li ověřit, že mapa odpovídá kódu, pravděpodobně ji budete muset znovu vytvořit.

 Nyní jste hotovi s vaším šetřením. Úspěšně jste našli a opravili problém pomocí mapování kódu. Máte k dispozici také mapu, která usnadňuje navigaci v rámci kódu, zapamatuje si, co jste se naučili, a zobrazí kroky, které jste provedli v zájmu vyřešení problému.

## <a name="see-also"></a>Viz také:

- [Mapování metod v zásobníku volání při ladění](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)
- [Vizualizace kódu](../modeling/visualize-code.md)
