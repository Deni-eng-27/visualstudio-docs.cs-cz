---
title: Stránka možnosti, vlastnosti uzlu textový editor | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Tools Options settings, Text Editor node properties
- automation [Visual Studio], controlling Tools Options
ms.assetid: 19438302-0677-4f4d-9720-5667e6a22ab2
caps.latest.revision: 21
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 62dddacaea1846c8e5d5da404ad7a16fde90f209
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "72662420"
---
# <a name="options-page-text-editor-node-properties"></a>Stránka Možnosti, vlastnosti uzlu textového editoru
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Tento dokument popisuje některé stránky (nebo kolekce vlastností), které jsou přidruženy ke kategorii **textový editor** , v `DTE.Properties("TextEditor", <Property Page>)` dialogovém okně **Možnosti** . Název každého dílčího oddílu je volání, které se používá pro přístup ke `Properties` kolekci, a tabulka v jednotlivých pododdílech obsahuje seznam vlastností v kolekci.

 Makra Visual Basic v části [řízení nastavení možností](https://msdn.microsoft.com/library/a09ed242-7494-4cde-bbd1-7a8ec617965d) ukazují, jak zobrazit aktuální možnosti a jejich hodnoty pro každou stránku dialogového okna **Možnosti** .

## <a name="general"></a>Obecné
 `DTE.Properties("TextEditor", "General")`

|Název položky vlastnosti|Hodnota|Popis|
|------------------------|-----------|-----------------|
|GoToAnchorAfterEscape|Get/Set (Boolean)|Pokud `True` je stisknuta klávesa Escape a výběr způsobí, že se kurzor přesune na místo, kde byla spuštěna akce, která vytvořila výběr. `False` Přesune kurzor na druhý konec výběru.|
|DragNDropTextEditing|Get/Set (Boolean)|Určuje, zda lze při operacích kopírování nebo vyjmutí a vložení vybranou oblast textu přetáhnout v dokumentu z jednoho místa do jiného.|
|HorizontalScrollBar|Get/Set (Boolean)|Určuje, zda se v oknech editoru zobrazuje vodorovný posuvník.|
|VerticalScrollBar|Get/Set (Boolean)|Určuje, zda se v oknech editoru zobrazuje svislý posuvník.|
|SelectionMargin|Get/Set (Boolean)|Určuje, zda je na levé straně podokna textu místo pro speciální operace výběru, ikony pro kreslení zarážek atd.|
|MarginIndicatorBar|Get/Set (Boolean)|Určuje, zda se zobrazuje svislá čára, která odděluje levý okraj podokna textu od hlavní části tohoto podokna.|
|UndoCaretActions|Get/Set (Boolean)|Pokud `True` . operace vrácení zpět zahrnují pohyb v bodě vložení, příkazy výběru a tak dále, kromě úprav akcí, které upravují vyrovnávací paměť.|
|AutoDelimiterHighlighting|Get/Set (Boolean)|Určuje, zda při zadání koncového oddělovače zvýrazní editor počáteční oddělovač. Editor vždy zobrazí počáteční oddělovač tučně bez ohledu na hodnotu této vlastnosti.|
|EditorEmulation|Get/Set (Enum)||
|DetectUTF8WithoutSignature|Get/Set (Boolean)|Zjistí, zda soubor používá kódování UTF-8, pokud nemá signaturu kódování.|
|TrackChanges|Get/Set (Boolean)||

## <a name="plain-text"></a>Prostý text
 `DTE.Properties("TextEditor", "PlainText")`

 `PlainText`Možnosti editoru ovlivňují nastavení editoru při úpravách textových souborů. Každý programovací jazyk a [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] balíček má vlastní specifické nastavení **textového editoru** . Například chcete-li zobrazit nebo změnit [!INCLUDE[csprcs](../../includes/csprcs-md.md)] nastavení editoru, použijte `DTE.Properties("TextEditor", "CSharp") or DTE.Properties("TextEditor", "CSharp-Specific")` . Pro nastavení editoru **skriptu SQL** použijte `DTE.Properties("TextEditor", "SQL ")` .

|Název položky vlastnosti|Hodnota|Popis|
|------------------------|-----------|-----------------|
|AutoListMembers|Get/Set (Boolean)|Určuje, zda se automaticky zobrazí dostupný seznam členů, když uživatel zadá za odkaz na proměnnou tečku.|
|AutoListParams|Get/Set (Boolean)|Určuje, zda se automaticky zobrazí popis seznamu argumentů, když uživatel zadá za název funkce závorku (.|
|HideAdvancedMembers|Get/Set (Boolean)|Určuje, zda se mají v seznamech doplňování výrazů vypisovat všechny členy nebo pouze nejpoužívanější.|
|VirtualSpace|Get/Set (Boolean)|Určuje, zda se prázdné znaky zobrazují jako grafika. Toto nastavení `true` způsobí, že se `WordWrap` položka vlastnosti (v tomto seznamu) nastaví na `false` .|
|WordWrap|Get/Set (Boolean)|Určuje, zda se dlouhé řádky v tomto zobrazení zalamují na hranicích slov. Toto nastavení `true` způsobí, že se `VirtualSpace` položka vlastnosti (v tomto seznamu) nastaví na `false` .|
|WordWrapGlyphs|Get/Set (Boolean)|Zobrazí piktogram na konci řádku; označuje, že se tento řádek zalamuje na další řádek.|
|EnableLeftClickForURLs|Get/Set (Boolean)|Určuje, zda editor podtrhuje adresy URL a umožňuje v systémem zaregistrovaném webovém prohlížeči přejít na tuto adresu URL jedním kliknutím.|
|IndentStyle|Get/Set ( <xref:EnvDTE.vsIndentStyle> )|Určuje styl odsazení: výchozí, inteligentní nebo žádné.|
|TabSize|Get/Set (Long)|Představuje počet mezer, které se rovnají kartě. Nastavení celého čísla mimo rozsah 1 až 60 (včetně) se nezdařilo.|
|InsertTabs|Get/Set (Boolean)|Pokud `True` jsou při odsazení použity znaky tabulátoru.|
|IndentSize|Get/Set (Long)|Představuje počet mezer pro jednu úroveň odsazení. Nastavení celočíselné hodnoty mimo rozsah 1–60 (včetně) se nezdaří.|
|ShowLineNumbers|Get/Set (Boolean)|Určuje, zda se při zobrazení dokumentu v základním editoru zobrazují na levém okraji čísla řádků.|
|ShowNavigationBar|Get/Set (Boolean)|Určuje, zda se v horní části oken editoru zobrazují rozevírací seznamy a tlačítka.|
|CutCopyBlankLines|Get/Set (Boolean)|Vyjme nebo zkopíruje prázdné řádky, pokud jsou vybrány.|

## <a name="see-also"></a>Viz také
 [Řízení nastavení možností](https://msdn.microsoft.com/library/a09ed242-7494-4cde-bbd1-7a8ec617965d) [Určení názvů položek vlastností na](https://msdn.microsoft.com/library/d450422d-47c7-4eeb-9f9f-3286264bc5aa) stránce Možnosti stránky možnosti [, vlastnosti uzlu prostředí](../../ide/reference/options-page-environment-node-properties.md) [, vlastnosti uzlu písma a barvy](../../ide/reference/options-page-fonts-and-colors-node-properties.md)
