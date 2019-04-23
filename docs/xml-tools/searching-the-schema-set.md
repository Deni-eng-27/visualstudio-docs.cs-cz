---
title: Průzkumník schémat XML - hledání sadě schémat
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: ec1395e0-d03c-4130-810d-f2db656937bd
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b73d5c8acac211db09926acf0ba8009aa04ac0a8
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60070894"
---
# <a name="search-the-schema-set"></a>Hledání v sadě schémat

**Průzkumníka schémat XML** umožňuje hledat schéma nastavit následujícími způsoby:

- Hledání klíčových slov.

- Hledání podle schématu.

## <a name="keyword-search"></a>Hledání klíčových slov

 Provádět vyhledávání – klíčové slovo tak, že zadáte podřetězce v **hledání SchemaSet** textového pole **Průzkumníka schémat XML** nástrojů.

 ![Hledání klíčových slov Průzkumníka schémat XML](../xml-tools/media/schemaexplorersearch.gif)

 **Průzkumníka schémat XML** vyhledá schéma, nastavte pro následující atributy:

- Žádné `name` nebo `ref` atributy, které odpovídají zadané klíčové slovo. Elementy, atributy, typy a tak dále, můžete najít podle názvu.

- `schemaLocation` Atributy #include.

- `namespace` Atributy příkazy pro import.

## <a name="schema-specific-search"></a>Konkrétní schéma vyhledávání

 **Průzkumníka schémat XML** také zahrnuje integrované hledání, kterým můžete přistupovat pomocí (klikněte pravým tlačítkem) kontextovou nabídku **Průzkumníka schémat XML**. Další informace o dostupných kontextové nabídky, naleznete v tématu [kontextové nabídky](../xml-tools/context-menus-xml-schema-explorer.md). Můžete také provádět konkrétní schéma vyhledávání ze zobrazení spuštění; Další informace najdete v části "Nastavit informace o schématu" v [zobrazení Start](../xml-tools/start-view.md) tématu.

## <a name="display-and-navigate-search-results"></a>Zobrazení a navigace ve výsledcích hledání

 Po dokončení hledání v podokně souhrnných výsledků se přidá na panel nástrojů s výsledky hledání. Výsledky hledání jsou také zvýrazněna v **Průzkumníka schémat XML** a označeny dílků na svislý posuvník. Výsledky hledání můžete Navigovat pomocí **přejít k další výsledek hledání** a **přejít na předchozí výsledky hledání** tlačítka v podokně souhrnných výsledků **Průzkumníka schémat XML**nástrojů; pomocí klávesových zkratek **F3** a **Shift**+**F3**; nebo na značek na posuvníku.

 Výsledky hledání do pracovního prostoru můžete přidat kliknutím **přidá zvýrazněné uzly do pracovního prostoru** tlačítko na panelu souhrnu výsledků.

 ![Výsledek hledání Průzkumníka schémat XML](../xml-tools/media/schemaexplorersearchresult.gif)

## <a name="clear-search-results"></a>Vymazat výsledky hledání

 Vymazat výsledky hledání, klikněte na tlačítko **x** tlačítko na panelu souhrnu výsledků z **Průzkumníka schémat XML** panel nástrojů vyhledávání.

## <a name="see-also"></a>Viz také:

- [Průzkumník schémat XML](../xml-tools/xml-schema-explorer.md)