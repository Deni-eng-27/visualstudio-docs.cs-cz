---
title: Průzkumník schématu XML | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
ms.assetid: 2fc39e98-b194-456b-a452-cfafb0a52d66
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 84aead3cf496a28e67e6440fb77b8cbf4aca6462
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="xml-schema-explorer"></a>Průzkumník schématu XML
Průzkumník schématu XML je integrovaná do sady Microsoft Visual Studio a Editor souborů XML pro práci s schématu XML definition language (XSD) schématy. Při otevření souboru schématu XML **schématu nastavit** uzel se zobrazí v Průzkumníku schématu XML. Všechny zahrnuté, importované nebo Předefinovaná schémata pro cílový soubor a také všechny soubory, které se odkazuje prostřednictvím `include` nebo `import` prohlášení, také se zobrazí v Průzkumníku schématu XML.  
  
 Průzkumník schématu XML umožňuje provést následující:  
  
-   Vám zajistí rychlý přehled sady schématu.  
  
-   Procházet a přejděte ke stromu.  
  
-   Proveďte – klíčové slovo a hledání specifické pro schéma. Další informace najdete v tématu [hledání sady schématu](../xml-tools/searching-the-schema-set.md).  
  
-   Přidejte do zobrazení grafu nebo zobrazení obsahu Modle výsledky hledání  
  
-   Řazení stromu podle pořadí dokument, typ nebo název. Další informace najdete v tématu [řazení, filtrování a seskupování](../xml-tools/sorting-filtering-and-grouping-xml-schema-explorer.md).  
  
-   Otevřete Editor souborů XML a přejít do umístění kód v souboru XSD. Další informace najdete v tématu [integrace pomocí editoru XML](../xml-tools/integration-with-xml-editor.md).  
  
-   Generovat ukázka XML pro globální elementy.  
  
Průzkumník schématu XML obsahuje hierarchická zobrazení schématu nastavit pomocí zobrazení stromu. Průzkumník schématu XML také poskytuje vyhledávání, filtrování, navigace a řazení. Pro přístup k Explorer schématu XML, proveďte jednu z následujících akcí:  
  
-   Pokud jste na [spuštění zobrazení](../xml-tools/start-view.md), klikněte na tlačítko **Explorer schématu XML** odkaz.  
  
-   Pokud jste na [zobrazení grafu](../xml-tools/graph-view.md) nebo [zobrazení obsahu modelu](../xml-tools/content-model-view.md) a mít uzly v pracovním prostoru, použijte v místní nabídce vyberte Explorer schématu XML.  
  
-   Můžete také vybrat Explorerfrom schématu XML **zobrazení** nabídky.  
  
-   Můžete přistupovat Explorerfrom schématu XML VB soubor, který má literál XML Visual Basic přidružený soubor XSD. Tím zobrazíte schéma nastavit v Průzkumníku schématu XML, klikněte pravým tlačítkem uzel XML ve literál XML nebo importu obor názvů XML a vyberte **zobrazit v Průzkumníku schématu** příkaz. Další informace najdete v tématu [integrace XML literály pomocí Průzkumníka schématu XML](../xml-tools/integration-of-xml-literals-with-xml-schema-explorer.md).  
  
## <a name="tree-view"></a>Zobrazení stromu  
 Explorer schématu XML zobrazí informace o sadě předem kompilovaném schématu ve stromové struktuře. Stromovou strukturu jsou uspořádána následujícím způsobem:  
  
-   Na nejvyšší úrovni je schéma nastavte uzel.  
  
-   Na druhé úrovni obsahuje obory názvů.  
  
-   Na třetí úrovni obsahuje soubory.  
  
-   Úroveň čtvrtý obsahuje globální uzly. To může zahrnovat prvky, skupiny, komplexní typy, jednoduché typy, atributy, skupiny atributů, a `include`, `import`, a `redefine` příkazy.  
  
Následuje příklad stromové struktury:  
  
![Průzkumník schématu XML](../xml-tools/media/xmlschemaexplorer.gif "XMLSchemaExplorer")  
  
## <a name="selection-and-activation"></a>Výběr a aktivace  
 Zvýrazněte a vyberte uzel, klikněte na tlačítko jednou v Průzkumníku schématu.  
  
 Pokud chcete aktivovat uzel, klikněte dvakrát na jeho nebo stiskněte klávesu **Enter** při výběru uzlu.  
  
-   Aktivace uzlu otevře soubor, ve kterém je tento uzel definovaný (Pokud soubor již není otevřený) a vybírá uzel v souboru.  
  
-   Aktivace uzlem soubor otevře vybraný soubor (Pokud není otevřený) a klade důraz `<schema>` uzlu.  
  
-   Aktivace SchemaSet nebo obor názvů uzlu neprovede žádnou akci.  
  
## <a name="draging-and-dropping-nodes"></a>Draging a vyřazení uzlů  
 Můžete přetáhnout a vyřadit globální uzlů, soubor uzly a uzly oboru názvů do zobrazení o návrháři XSD. Pokud je aktuální zobrazení [spuštění zobrazení](../xml-tools/start-view.md), přetáhněte uzel k zobrazení se otevře [zobrazení grafu](../xml-tools/graph-view.md). Pokud je aktuální zobrazení [zobrazení obsahu modelu](../xml-tools/content-model-view.md) nebo zobrazení grafu, zobrazení se nezmění, pokud je uzlem na ho vyřadit.  
  
 Odstranit soubory v zobrazení přidá všechny globální uzly v souboru, který se [prostoru Návrhář XSD](../xml-tools/xml-schema-designer-workspace.md). Vyřazení obory názvů v zobrazení přidá všechny uzly globální v oboru názvů do pracovního prostoru. V pracovním prostoru jsou sdílena mezi všechna zobrazení.  
  
 Můžete nelze přetažení místní uzlů nebo import.  
  
## <a name="in-this-section"></a>V tomto oddílu  
  
-   [Hledání v sadě schémat](../xml-tools/searching-the-schema-set.md)  
  
-   [Řazení, filtrování a seskupení](../xml-tools/sorting-filtering-and-grouping-xml-schema-explorer.md)  
  
-   [Kontextové nabídky](../xml-tools/context-menus-xml-schema-explorer.md)  
  
-   [Integrace literálů XML s Průzkumníkem schémat XML](../xml-tools/integration-of-xml-literals-with-xml-schema-explorer.md)  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Přidání uzlů do pracovního prostoru z Průzkumníka schémat XML](../xml-tools/how-to-add-nodes-to-the-workspace-from-the-xml-schema-explorer.md)