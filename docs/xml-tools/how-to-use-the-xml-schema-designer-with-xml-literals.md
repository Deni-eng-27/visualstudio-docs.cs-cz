---
title: 'Postupy: použití návrháře schémat XML s literály XML'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d11803e7-f81a-41a2-a145-ba494a45cc93
author: TerryGLee
ms.author: tglee
manager: jillfra
dev_langs:
- VB
ms.workload:
- multiple
ms.openlocfilehash: b4001e705cc69e07242abeeef5919573b264c5e8
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/01/2020
ms.locfileid: "75592656"
---
# <a name="how-to-use-the-xml-schema-designer-with-xml-literals"></a>Postupy: použití návrháře schémat XML s literály XML

Toto téma popisuje, jak zobrazit schéma přidružené k literálu XML v projektu Visual Basic.

## <a name="create-a-new-visual-basic-project"></a>Vytvoření nového projektu Visual Basic

1. Otevřít Visual Studio.

2. Vytvořte nový projekt **konzolové aplikace** Visual Basic s názvem **XMLLiterals**.

     Nový projekt obsahuje jeden Visual Basic zdrojový soubor *Module1. vb*.

## <a name="add-an-existing-xsd-file"></a>Přidat existující soubor XSD

1. Otevřete v programu Poznámkový blok nový textový soubor. Zkopírujte ukázkový kód schématu XML ze [schématu nákupních objednávek](../xml-tools/sample-xsd-file-simple-schema.md) a vložte ho do souboru.

2. Uložte soubor do nějakého umístění s názvem *PurchaseOrderSchema. xsd*.

3. V **Průzkumník řešení**klikněte pravým tlačítkem myši na název projektu, vyberte možnost **Přidat**a poté vyberte možnost **existující položka**. Zobrazí se dialogové okno **položka AddExisting** . Přejděte k souboru *PurchaseOrderSchema. xsd* , vyberte ho a pak klikněte na **Přidat**.

     Projekt XMLLiterals nyní obsahuje dva soubory: *Module1. vb* a *PurchaseOrderSchema. xsd*.

## <a name="add-code"></a>Přidat kód

Chcete-li přidat kód Visual Basic s literálem XML, na základě souboru XSD, který je součástí projektu:

1. Nahraďte kód v souboru *Module1. vb* následujícím kódem:

   ```vb
   Imports <xmlns:ns="http://tempuri.org/PurchaseOrderSchema.xsd">

   Module Module1
      Sub Main()

          Dim XMLLiteral = <ns:PurchaseOrder OrderDate="1900-01-01">
                               <ns:ShipTo country="US">
                                   <ns:name>name1</ns:name>
                                   <ns:street>street1</ns:street>
                                   <ns:city>city1</ns:city>
                                   <ns:state>state1</ns:state>
                                   <ns:zip>1</ns:zip>
                               </ns:ShipTo>
                               <ns:BillTo country="US">
                                   <ns:name>name1</ns:name>
                                   <ns:street>street1</ns:street>
                                   <ns:city>city1</ns:city>
                                   <ns:state>state1</ns:state>
                                   <ns:zip>1</ns:zip>
                               </ns:BillTo>
                           </ns:PurchaseOrder>

      End Sub
   End Module
   ```

2. Klikněte pravým tlačítkem na libovolný uzel XML v literálu XML nebo importujte obor názvů XML a **v Průzkumníku schémat vyberte Zobrazit**.

   **Průzkumník schémat XML** je zobrazen vedle sebe s Visual Basic souborem, který má literál XML přidružený ke sadě schémat XML.
