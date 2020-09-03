---
title: 'Postupy: Přidání uzlů výsledků hledání sad schémat do pracovního prostoru | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: ff33b3cc-4db9-4b4e-9378-b45ed5999b18
caps.latest.revision: 10
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: b34be331ad3ec67e2c3bd8d9ecc500cd256b1b09
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "72666542"
---
# <a name="how-to-add-schema-set-search-result-nodes-to-the-workspace"></a>Postupy: Přidání uzlů výsledků hledání v sadě schémat do pracovního prostoru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Toto téma vysvětluje, jak přidat uzly, které jsou zvýrazněny v Průzkumníku schémat XML jako výsledek hledání klíčového slova v pracovním prostoru.

> [!NOTE]
> Do [pracovního prostoru](../xml-tools/xml-schema-designer-workspace.md)lze přidat pouze globální uzly.

 V tomto příkladu se používá ukázka [schématu nákupní objednávky](../xml-tools/sample-xsd-file-purchase-order-schema.md).

### <a name="to-add-schema-set-result-nodes"></a>Postup přidání uzlů výsledků sady schémat

1. Postupujte podle kroků v tématu [Postupy: vytvoření a úprava souboru schématu XSD](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md).

2. Do textového pole Hledat na panelu nástrojů v [Průzkumníkovi XML](../xml-tools/xml-schema-explorer.md) zadejte "PurchaseOrder" a klikněte na tlačítko Hledat.

     ![Hledání klíčového slova Průzkumníka schémat XML](../xml-tools/media/schemaexplorersearch.gif "SchemaExplorerSearch")

     Výsledky hledání jsou zvýrazněny v Průzkumníku schémat XML a označené značkami na svislém posuvníku.

3. Do pracovního prostoru přidejte výsledky hledání kliknutím na tlačítko **Přidat zvýrazněné uzly do pracovního prostoru** v podokně souhrnné výsledky.

     ![Výsledek hledání v Průzkumníkovi schémat XML](../xml-tools/media/schemaexplorersearchresult.gif "SchemaExplorerSearchResult")

     `purchaseOrder`Uzel a `PurchaseOrderType` uzel se zobrazí vedle sebe na návrhové ploše [zobrazení grafu](../xml-tools/graph-view.md). Vzhledem k tomu, že oba uzly jsou související ( `purchaseOrder` element je `PurchaseOrderType` typu), je mezi nimi vykreslena šipka.
