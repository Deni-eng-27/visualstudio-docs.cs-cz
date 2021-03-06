---
title: 'Návrhář schématu XML: získání přehledu o sadě schémat pomocí zobrazení grafu'
description: Naučte se používat zobrazení grafu v Průzkumníkovi schémat XML k zobrazení vysokého zobrazení uzlů v sadě schémat a vztahů mezi uzly.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: how-to
ms.assetid: c0df4b0d-52ef-4a6c-9676-1d8311aad7c7
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 553b9f2d84f70c75ebcee40cdffe044237c23a5f
ms.sourcegitcommit: f4b49f1fc50ffcb39c6b87e2716b4dc7085c7fb5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/05/2020
ms.locfileid: "93398485"
---
# <a name="how-to-get-an-overview-of-a-schema-set-using-the-graph-view"></a>Postupy: získání přehledu o sadě schémat pomocí zobrazení grafu

Toto téma popisuje, jak použít [zobrazení grafu](../xml-tools/graph-view.md) k zobrazení vysokého zobrazení uzlů v sadě schémat a vztahů mezi uzly.

## <a name="to-create-a-new-xsd-file-and-display-the-root-element-in-the-content-model-view"></a>Vytvoření nového souboru XSD a zobrazení kořenového prvku v zobrazení modelu obsahu

1. Vytvořte nový soubor schématu XML a uložte soubor jako *Relationships. xsd*.

2. Kliknutím na **použít editor XML zobrazíte a upravíte odkaz základní soubor XML schématu** v zobrazení Start.

3. Zkopírujte ukázkový kód schématu XML z [ukázkového schématu XML: relace](../xml-tools/sample-xsd-file-relationships.md) a vložte jej pro nahrazení kódu, který byl přidán do nového souboru XSD ve výchozím nastavení.

4. Klikněte pravým tlačítkem na libovolné místo v editoru XML a vyberte **zobrazení Návrhář**.

5. Vyberte zobrazení grafu z **panelu nástrojů XSD**.

6. V **Průzkumníku schémat XML** vyberte uzel **sada schémat** a přetáhněte uzel na návrhovou plochu zobrazení grafu. Měli byste vidět všechny globální uzly a šipky připojující uzly, které mají relace.

     ![Zobrazení grafu](../xml-tools/media/relationshipingraphview.gif)

7. Klikněte na libovolný uzel na návrhové ploše a podívejte se na panel s popisem cesty a zjistěte, kde se vybraný uzel nachází v sadě schémat.

8. Rick – klikněte na libovolný uzel prvku na návrhové ploše a vyberte **vytvořit ukázkový kód XML** pro zobrazení dokumentu instance XML.
