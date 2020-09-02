---
title: Kontrola uzlů pomocí zobrazení modelu obsahu v Návrháři schématu XML
ms.date: 11/04/2016
ms.topic: how-to
ms.assetid: c42ddac8-b0e3-48d6-9832-112a19d6c104
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 81bf6294aeac9a23168bf9cf9aaec26efbfc6c1f
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85815978"
---
# <a name="how-to-examine-the-content-model-of-nodes-using-the-content-model-view"></a>Postupy: prohlédnutí modelu obsahu uzlů pomocí zobrazení modelu obsahu

Toto téma popisuje, jak prozkoumat uzly pomocí [zobrazení modelu obsahu](../xml-tools/content-model-view.md).

## <a name="to-create-a-new-xsd-file-and-display-the-root-element-in-the-content-model-view"></a>Vytvoření nového souboru XSD a zobrazení kořenového prvku v zobrazení modelu obsahu

1. Vytvoří nový soubor schématu XML.

2. Klikněte na **použít editor XML k zobrazení a úpravě základního souboru schématu XML** v zobrazení Start.

3. Zkopírujte ukázkový kód schématu XML z [ukázkového schématu XML: schéma nákupu](../xml-tools/sample-xsd-file-purchase-order-schema.md) a vložte jej pro nahrazení kódu, který byl přidán do nového souboru XSD ve výchozím nastavení.

4. Vyberte `purchaseOrder` element v Průzkumníku schémat tak, že kliknete pravým tlačítkem na `purchaseOrder` prvek v editoru XML a vyberete **Zobrazit v Průzkumníkovi XML**.

5. Klikněte pravým tlačítkem myši `purchaseOrder` v PRŮZKUMNÍKU XML a vyberte **Zobrazit v zobrazení modelu obsahu**.

     Zobrazení modelu obsahu zobrazí `purchaseOrder` prvek na jeho návrhové ploše.

6. Rozbalte `shipTo` uzly, `billTo` a `items` buď dvojitým kliknutím na jednotlivé uzly, nebo kliknutím na dvojitou šipku napravo od každého uzlu.

     Uzly `purchaseOrder` elementu jsou nyní rozbaleny a můžete zobrazit model obsahu elementu.

7. V rámci prvku klikněte na libovolný uzel `purchaseOrder` a podívejte se na panel s popisem cesty, kde se zobrazí informace o tom, kde se v sadě schémat nachází vybraný uzel.

8. Kliknutím na tlačítko **zobrazit dokumentaci** na panelu nástrojů XSD přepnete dokumentaci. Můžete také kliknout pravým tlačítkem na návrhovou plochu a přepínat dokumentaci.

9. Klikněte pravým tlačítkem na `purchaseOrder` uzel a vyberte **vytvořit ukázkový kód XML** , abyste viděli dokument instance XML.
