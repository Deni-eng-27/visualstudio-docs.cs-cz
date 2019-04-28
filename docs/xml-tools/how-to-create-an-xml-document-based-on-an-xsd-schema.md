---
title: 'Postupy: Vytvoření dokumentu XML na základě schématu XSD'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 193b195f-e918-4c79-a1a1-8096a1433bde
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d4ba0106a1494c7e7e8d56c3e902a3436f657712
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62783327"
---
# <a name="how-to-create-an-xml-document-based-on-an-xsd-schema"></a>Postupy: Vytvoření dokumentu XML na základě schématu XSD

**Generovat ukázkové XML** funkce generuje ukázkový soubor XML na základě souboru schématu XML (XSD).

 Tuto možnost můžete použít v následujících scénářích:

- Abyste pochopili použití různých konstrukcí ve schématu.

- Potvrďte, že schéma co dělá jeho účelem je provádět.

**Generovat ukázkové XML** funkce je dostupná pouze na globální prvky a vyžaduje platnou sadu schémat XML.

Tato funkce generuje obvykle platný dokumentů XML. Nicméně pokud schéma obsahuje jeden nebo více z následujících akcí, ukázka nemusí být platné:

- `xs:key`, `xs:keyref`, A `xs:unique` omezení identity.

- `xs:pattern` omezující vlastnosti.

- Výčty `xs:QName` typu.

- `xs:ENTITY`, `xs:ENTITIES`, a `xs:NOTATION` typy.

Všimněte si také, že `xs:base64Binary` obsah se bude generovat jenom v případě, že dojde k vyčíslení ve schématu pro daný typ.

## <a name="to-generate-an-xml-instance-document-based-on-the-xsd-file"></a>Generovat dokument XML instance na základě souboru XSD

1. Postupujte podle kroků v [jak: Vytvoření a úprava souboru schématu XSD](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md).

2. V [Průzkumníka schémat XML](../xml-tools/xml-schema-explorer.md), klikněte pravým tlačítkem myši `PurchaseOrder` globální element. Vyberte **generovat ukázkový soubor XML**.

     Když vyberete tuto možnost, PurchaseOrder. *xml* soubor s následujícím obsahem XML ukázky bude vygenerována a otevřené v editoru XML:

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <PurchaseOrder OrderDate="1900-01-01" xmlns="http://tempuri.org/PurchaseOrderSchema.xsd">
      <ShipTo country="US">
        <name>name1</name>
        <street>street1</street>
        <city>city1</city>
        <state>state1</state>
        <zip>1</zip>
      </ShipTo>
      <ShipTo country="US">
        <name>name2</name>
        <street>street2</street>
        <city>city2</city>
        <state>state2</state>
        <zip>-79228162514264337593543950335</zip>
      </ShipTo>
      <BillTo country="US">
        <name>name1</name>
        <street>street1</street>
        <city>city1</city>
        <state>state1</state>
        <zip>1</zip>
      </BillTo>
    </PurchaseOrder>
    ```