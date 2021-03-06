---
title: Přidat uzly výsledků hledání sady schémat XML do pracovního prostoru
description: Naučte se, jak přidat uzly zvýrazněné v Průzkumníku schémat XML jako výsledek hledání klíčového slova v pracovním prostoru.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: how-to
ms.assetid: ff33b3cc-4db9-4b4e-9378-b45ed5999b18
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e306ec76b6089d822dfdcd154ff1947aef1c9cac
ms.sourcegitcommit: 1a36533f385e50c05f661f440380fda6386ed3c1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/30/2020
ms.locfileid: "93049180"
---
# <a name="how-to-add-schema-set-search-result-nodes-to-the-workspace"></a>Postupy: Přidání uzlů výsledků hledání sad schémat do pracovního prostoru

Toto téma vysvětluje, jak přidat uzly, které jsou zvýrazněny v **Průzkumníku schémat XML** jako výsledek hledání klíčového slova v pracovním prostoru.

> [!NOTE]
> Do [pracovního prostoru](../xml-tools/xml-schema-designer-workspace.md)lze přidat pouze globální uzly.

V tomto příkladu se používá ukázka [schématu nákupní objednávky](../xml-tools/sample-xsd-file-purchase-order-schema.md).

## <a name="to-add-schema-set-result-nodes"></a>Postup přidání uzlů výsledků sady schémat

1. Postupujte podle kroků v tématu [Postupy: vytvoření a úprava souboru schématu XSD](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md).

2. Do textového pole Hledat na panelu nástrojů v [Průzkumníkovi XML](../xml-tools/xml-schema-explorer.md) zadejte "PurchaseOrder" a klikněte na tlačítko Hledat.

     ![Hledání klíčového slova Průzkumníka schémat XML](../xml-tools/media/schemaexplorersearch.gif)

     Výsledky hledání jsou zvýrazněny v **Průzkumníku schémat XML** a označené značkami na svislém posuvníku.

3. Do pracovního prostoru přidejte výsledky hledání kliknutím na tlačítko **Přidat zvýrazněné uzly do pracovního prostoru** v podokně souhrnné výsledky.

     ![Výsledek hledání v Průzkumníkovi schémat XML](../xml-tools/media/schemaexplorersearchresult.gif)

     `purchaseOrder`Uzel a `PurchaseOrderType` uzel se zobrazí vedle sebe na návrhové ploše [zobrazení grafu](../xml-tools/graph-view.md). Vzhledem k tomu, že oba uzly jsou související ( `purchaseOrder` element je `PurchaseOrderType` typu), je mezi nimi vykreslena šipka.
