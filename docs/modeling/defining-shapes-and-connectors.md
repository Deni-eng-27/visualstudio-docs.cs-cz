---
title: Definování obrazců a konektorů
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: db80cada3f49c8ba6488af31f399373457017c18
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="defining-shapes-and-connectors"></a>Definování obrazců a konektorů
Existuje několik typů základní tvary, které můžete použít k zobrazení informací v diagramu v jazyce specifické pro doménu (DSL).

##  <a name="shapeTypes"></a> Základní typy tvarů a konektory
 DSL diagram zobrazuje kolekce *tvarů* vzájemně propojena linkami nebo *konektory*.  Obvykle, ale ne vždy:

-   Obrazce jsou viditelné reprezentace prvků modelu.

-   Spojnice představují referenčních relací.

-   Diagram představuje instanci kořenové modelu.

-   Vnoření vztahy mezi elementy modelu jsou uvedeny ve členství ve skupině. Například elementy představující součásti porty jsou vloženy do komponentu.

 Tyto vzory nejsou vynucená, ale podporovány jsou více důrazně. Při návrhu DSL berte v úvahu, který by měl být návrh vnoření vztahy vliv jak má být k dispozici modelu na obrazovce. Naopak referenční relace by měla odpovídat koncepty vaší firemní domény.

 K dispozici jsou následující typy tvarů:

|Obrazce typu|Popis|
|----------------|-----------------|
|Geometrické obrazce|Obecné účely obdélníková nebo eliptické tvaru. Text a ikona dekoratéry můžete zobrazit v konkrétní umístění vůči hranice tvaru.<br /><br /> Vnořit tvarů uvnitř geometrické obrazce, najdete v tématu [vnoření tvarů](../modeling/nesting-shapes.md).|
|Tvar prostředí|Rámeček obsahující hlavičku a oddílů, jako například třída UML. Každé prostředí může obsahovat seznam řádků textu.<br /><br /> Řádky obvykle představují elementy vložených pod elementem reprezentována tvaru. Příklad vytvořte DSL ze šablony řešení diagramů tříd.|
|Tvar bitové kopie|Obrazec, který zobrazí obrázek.|
|Port obrazce|Malé obdélníku navržený tak, aby připojení k obrys jiného obrazce. Obvykle se používá v modelech součásti.<br /><br /> Element modelu reprezentována port je obvykle vložených pod reprezentována tvaru nadřazeného elementu. Příklad vytvořte DSL pomocí šablony řešení součásti.<br /><br /> Ve výchozím nastavení můžete po stranách nadřazené Vysuňte obrazce portu. Můžete definovat rozsah pravidla omezit na konkrétní pozici.<br /><br /> Tím, že port obrazce velmi malé a transparentní, můžete ji zadat pevné spojovací bod na povrch jeho nadřazeného obrazce.|
|Plaveckých drah|Plaveckých drah oddílu diagram na vodorovné nebo svislé segmenty. Dráha stále pod ostatním tvarům v diagramu.<br /><br /> Obvykle jsou elementy modelu dráha nadřazena v kořenovém adresáři modelu a další elementy jsou nadřazena na ně. Příklad vytvořte DSL ze šablony řešení tok úkolů.|
|Konektory|Řádky vykreslovat mezi tvary obvykle představují referenčních relací. Můžete nastavit možnosti aby konektor přímá nebo lomené a mít různé typy šipku.|

##  <a name="shapeInheritance"></a> Tvar dědičnosti
 Obrazce může dědit vlastnosti z jiného tvaru. Obrazce však musí být stejného druhu. Například pouze geometrické obrazce dědit z geometrické obrazce. Zděděné obrazce mají přihrádky a dekorátory jejich základní tvaru. Konektory lze dědit z konektorů.