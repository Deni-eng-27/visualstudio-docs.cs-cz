---
title: Možnosti, textový Editor, všechny jazyky, posuvníky
ms.date: 10/25/2018
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.All_Languages.Scroll_Bars
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 881f995dc8f4c675691f7eaa63d26acefd4b3d01
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53876783"
---
# <a name="options-text-editor-all-languages-scroll-bars"></a>Možnosti, textový Editor, všechny jazyky, posuvníky
Toto dialogové okno umožňuje změnit výchozí chování posuvníku editoru kódu. Chcete-li zobrazit tyto možnosti, vyberte **možnosti** z **nástroje** nabídky. V rámci **textový Editor** složky, rozbalte **všechny jazyky** podsložku a klikněte na tlačítko **posuvníky**.

> [!CAUTION]
> Tato stránka nastaví výchozí možnosti pro všechny vývojářské jazyky. Resetuje se možnost v tomto dialogovém okně obnovíte možnosti posuvníky ve všech jazycích do jakékoli volby jsou tady vyberete. Chcete-li změnit možnosti textového editoru pro právě jeden jazyk, rozbalte podsložku pro daný jazyk a vyberte jeho možnosti.

## <a name="show-horizontal-scroll-bar"></a>Zobrazí vodorovný posuvník

Pokud je vybráno, zobrazí vodorovný posuvník, který umožňuje ze strany na stranu přejděte do zobrazení elementy, které spadají mimo oblast zobrazení editoru. Pokud vodorovné posuvníky nedostupné, můžete přejít kurzor klíče.

## <a name="show-vertical-scroll-bar"></a>Zobrazit svislý posuvník.

Pokud je vybráno, zobrazí svislý posuvník, který umožňuje nahoru a dolů k zobrazení elementy, které spadají mimo oblast zobrazení editoru. Pokud svislé posuvníky nejsou k dispozici, můžete Page Up, Page Down a klíče kurzor posouvat.

## <a name="display"></a>Displej

### <a name="show-annotations-over-vertical-scroll-bar"></a>Zobrazit poznámky přes svislý posuvník

Vyberte, zda svislý posuvník zobrazuje následující poznámky:

- změny
- značky
- chyby
- pozici blikajícího kurzoru

> [!TIP]
> **Zobrazit značky** možnost obsahuje zarážky a záložky.

Vyzkoušejte si, že otevřete soubor kódu a nahrazení nějaký text, který se nachází na několika místech v souboru. Posuvník demonstruje účinek nahrazení, tak si změny můžete zálohovat, pokud něco, co by nemělo být nahrazen.

## <a name="behavior"></a>Chování

Posuvník má dva režimy: panelu režim a režim mapování.

### <a name="use-bar-mode-for-vertical-scroll-bar"></a>Použít panel režim pro svislý posuvník.

*Panel režimu* zobrazí poznámka ukazatelů posuvníku. Kliknutím na posuvník posune stránku nahoru nebo dolů, ale nepřejde do tohoto umístění v souboru.

### <a name="use-map-mode-for-vertical-scroll-bar"></a>Použít režim mapování pro svislý posuvník.

V *režim mapování*po kliknutí na umístění na posuvník, kurzor přejde do tohoto umístění v souboru namísto pouze posouvání navýšení nebo snížení kapacity na stránce. Řádky kódu jsou uvedeny v miniaturní posuvníku. Můžete zvolit, jak široké sloupce mapy je tak, že vyberete hodnotu v **hled zdrojů**. Pokud chcete povolit větší náhled kódu při přesunutí ukazatele myši na mapě, vyberte **zobrazení popisu tlačítka ve verzi Preview** možnost. Sbalených oblasti jinak jsou zobrazena šedě a rozbalte při dvojitém kliknutí na ně.

> [!TIP]
> Můžete vypnout zobrazení miniaturní kódu v režimu mapování tak, že nastavíte **hled zdrojů** k **vypnout**. Pokud **zobrazení popisu tlačítka ve verzi Preview** je vybrané, se stále zobrazuje náhled kódu na tomto místě při najetí na ukazatel na posuvníku a kurzor stále přejde do tohoto umístění v souboru po kliknutí na.

## <a name="see-also"></a>Viz také:

- [Postupy: Upravit posuvník](../how-to-track-your-code-by-customizing-the-scrollbar.md)