---
title: Přidání uzlů výsledků hledání v sadě schémat XML do pracovního prostoru
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: ff33b3cc-4db9-4b4e-9378-b45ed5999b18
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9e9f004943474f9b1c0fb449c1aec23f70034c3a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53875031"
---
# <a name="how-to-add-schema-set-search-result-nodes-to-the-workspace"></a>Postupy: Přidání uzlů výsledků hledání v sadě schémat do pracovního prostoru

Toto téma vysvětluje, jak přidat uzly, které jsou zvýrazněné **Průzkumníka schémat XML** jako výsledek hledání klíčového slova v pracovním prostoru.

> [!NOTE]
> Lze přidat pouze globální uzly [pracovní prostor](../xml-tools/xml-schema-designer-workspace.md).


 Tento příklad používá ukázku [nákupní pořadí schématu](../xml-tools/sample-xsd-file-purchase-order-schema.md).

## <a name="to-add-schema-set-result-nodes"></a>Přidání uzlů výsledků sadě schémat

1.  Postupujte podle kroků v [jak: Vytvoření a úprava souboru schématu XSD](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md).

2.  Do textového pole hledání zadejte "purchaseOrder" [Průzkumník XML](../xml-tools/xml-schema-explorer.md) nástrojů a klikněte na tlačítko Hledat.

     ![Hledání klíčových slov Průzkumníka schémat XML](../xml-tools/media/schemaexplorersearch.gif)

     Výsledky hledání jsou zvýrazněné **Průzkumníka schémat XML** a označeny dílků na svislý posuvník.

3.  Výsledky hledání do pracovního prostoru přidat kliknutím **přidá zvýrazněné uzly do pracovního prostoru** tlačítko na panelu souhrnu výsledků.

     ![Výsledek hledání Průzkumníka schémat XML](../xml-tools/media/schemaexplorersearchresult.gif)

     `purchaseOrder` Uzlu a `PurchaseOrderType` uzel se zobrazí vedle sebe na návrhové ploše [zobrazení grafu](../xml-tools/graph-view.md). Protože se týkají dva uzly ( `purchaseOrder` element má `PurchaseOrderType` typu), šipka vykreslením mezi nimi.