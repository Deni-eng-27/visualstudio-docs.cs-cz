---
title: Možnosti, textový editor, XAML, formátování
ms.date: 01/17/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.XAML.Formatting.General
- VS.ToolsOptionsPages.Text_Editor.XAML.Miscellaneous
- VS.ToolsOptionsPages.Text_Editor.XAML.Formatting.Spacing
helpviewer_keywords:
- element spacing, XAML view settings
- attribute spacing, XAML view settings
- XAML view settings, auto-formatting events
- auto-formatting events, XAML view settings
- XAML view settings, tag wrapping
- XAML view settings, auto insert
- quotation mark style, XAML view settings
- XAML formatting, WPF Designer
- XAML view settings, Toolbox
- XAML view settings, element spacing
- default view, XAML view settings
- auto insert, XAML view settings
- XAML view settings, default view
- XAML view settings, quotation mark style
- tag wrapping, XAML view settings
- WPF Designer, XAML formatting
- XAML view settings, attribute spacing
ms.assetid: ad3820b1-0d94-4807-a74c-c3467ed973a2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 272fb5368b73e483bb7d2f44c475d5e4e7bfdfcc
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49933570"
---
# <a name="options-text-editor-xaml-formatting"></a>Možnosti, textový editor, XAML, formátování
Použití **formátování** stránky vlastností k určení, jak jsou formátovány elementů a atributů v dokumentech XAML. Chcete-li otevřít **možnosti** dialogovém okně klikněte na tlačítko **nástroje** nabídky a pak klikněte na tlačítko **možnosti**. Přístup **formátování** vlastnost stránce, rozbalte **textový Editor**, **XAML**, **formátování** uzlu.

> [!NOTE]
> Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení integrovaného vývojového prostředí sady Visual Studio](../../ide/personalizing-the-visual-studio-ide.md).


## <a name="auto-formatting-events"></a>Události automatického formátování
 Automatické formátování může dojít, když se zjistí některý z následujících událostí.

-   Dokončení koncové značky nebo jednoduché značky.

-   Dokončení počáteční značky.

-   Vložení ze schránky.

-   Formátování klávesových příkazů.

Můžete určit, které události způsobit automatického formátování.

|||
|-|-|
|**Dokončení koncové nebo jednoduché značky**|Automatické formátování vyvolá se po dokončení zápisu se koncová značka nebo jednoduché značky. Jednoduché značky nemá žádné atributy, například `<Button />`.|
|**Po dokončení počáteční značky**|Automatické formátování nastane, když dokončíte zadávání počáteční značku.|
|**Při vložení ze schránky**|Automatické formátování vyvolá se při vložení XAML ze schránky do zobrazení XAML.|

## <a name="quotation-mark-style"></a>Styl uvozovky
 Toto nastavení určuje, zda hodnoty atributů jsou uzavřeny v jednoduchých nebo dvojitých uvozovek. Toto nastavení použijte, automatického formátování a automatické dokončování IntelliSense.

 Jakmile jednou nastavíte tuto možnost, pouze atributy následně přidat pomocí návrháře vliv na jeden nebo ručně v XAML zobrazení jsou.

|||
|-|-|
|**Dvojité uvozovky (")**|Hodnoty atributů jsou uzavřeny v dvojitých uvozovkách.<br /><br /> `<Button Name="button1">Hello</Button>`|
|**Jednoduché uvozovky (')**|Hodnoty atributů jsou uzavřeny v jednoduchých uvozovkách.<br /><br /> `<Button Name='button1'>Hello</Button>`|

## <a name="tag-wrapping"></a>Obtékání značky
 Můžete určit délka řádku pro obtékání značky. Pokud je povoleno zalamování značky, budou všechny XAML následně přidat pomocí návrháře zabaleny odpovídajícím způsobem.

|||
|-|-|
|**Zalomit značky, které překročí určenou délku**|Určuje, zda řádky jsou zabaleny v určené délky řádku **délka**.|
|**Délka**|Počet znaků, které mohou obsahovat řádek. V případě potřeby některé řádky XAML může překročit Délka zadaného řádku.|

## <a name="attribute-spacing"></a>Vzdálenost atributů
 Pomocí tohoto nastavení můžete řídit, jak jsou uspořádány atributy v dokumentu XAML

|||
|-|-|
|**Zachovat vložení znaků newline a mezery mezi atributy**|Nové řádky a mezery mezi atributy nejsou ovlivněny automatického formátování.<br /><br /> `<Button Height="23"   Name="button1"`<br /><br /> `Width="75">Hello</Button>`|
|**Vložit mezi atributy jednu mezeru**|Atributy zabírat jeden řádek s dělicí sousední atributy jednu mezeru. Nastavení obtékání značky se použijí.<br /><br /> `<Button Height="23" Name="button1" Width="75">Hello</Button>`|
|**Umístit každý atribut na samostatný řádek**|Každý atribut zabírá samostatném řádku. To je užitečné, když jsou k dispozici mnoho atributů.<br /><br /> `<Button`<br /><br /> `Height="23"`<br /><br /> `Name="button1"`<br /><br /> `Width="75">Hello</Button>`|
|**Pozice první atribut na stejný řádek jako počáteční značku**|Pokud je zaškrtnuto, zobrazí se první atribut na stejný řádek jako počáteční značky elementu.<br /><br /> `<Button Height="23"`<br /><br /> `Name="button1"`<br /><br /> `Width="75">Hello</Button>`|

## <a name="element-spacing"></a>Vzdálenost elementů
 Pomocí tohoto nastavení můžete řídit, jak prvky jsou uspořádány do dokumentu XAML


| | |
| - | - |
| **Zachovat nové řádky v obsahu** | Prázdné řádky v obsahu elementu se neodeberou.<br /><br /> `<Grid>`<br /><br /> ``<br /><br /> ``<br /><br /> `<Button Name="button1">Hello</Button>`<br /><br /> ``<br /><br /> `</Grid>\` |
| **Sbalit několik prázdných řádků v obsahu do jednoho řádku** | Prázdné řádky v obsahu elementu, jsou sbaleny do jednoho řádku.<br /><br /> `<Grid>`<br /><br /> ``<br /><br /> `<Button Name="button1">Hello</Button>`<br /><br /> ``<br /><br /> `</Grid>` |
| **Odebrat prázdné řádky v obsahu** | Odeberou se všechny prázdné řádky v obsahu elementu.<br /><br /> `<Grid>`<br /><br /> `<Button Name="button1">Hello</Button>`<br /><br /> `</Grid>` |

## <a name="miscellaneous-section-auto-insert"></a>Různé části Automatické vložení
 Pomocí tohoto nastavení můžete řídit, kdy značky a nabídky jsou automaticky generovány.

|||
|-|-|
|**Uzavírací značky**|Určuje, zda elementu uzavírací značku není automaticky vygenerován při zavření úvodní značku, s větší než znak (>).|
|**Uvozovky atributu**|Určuje, zda nadřazené nabídky jsou generovány, pokud hodnota atributu se vybere z rozevíracího seznamu dokončení příkazu.|
|**Pravé složené závorky pro MarkupExtension**|Určuje, zda rozšíření značek uzavírací závorkou (}) není automaticky vygenerován při zadávání otevírací složená závorka znaků ({}).|
|**Čárky k oddělení parametrů MarkupExtension**|Určuje, zda čárky jsou generovány, pokud více než jeden parametr typu v rozšíření značek.|

## <a name="see-also"></a>Viz také:

- [XAML ve WPF](/dotnet/framework/wpf/advanced/xaml-in-wpf)
