---
title: "Návod: Použití funkcí Editor XML | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea8dc357-2e66-455a-aec2-7ccaccfc9adf
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d87870ef00ceb0a3c66b91975b11038c00bd1dc2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-using-xml-editor-features"></a>Návod: Použití funkcí Editor XML
Kroky v tomto návodu ukazují, jak vytvořit nový dokument XML. Průvodce také používá některé z funkcí editoru XML, které umožňují cenné XML pro vytváření obsahu.  
  
> [!NOTE]
>  Před spuštěním průvodce, uložte soubor hireDate.xsd (uvedené níže v tomto tématu) do místního počítače.  
  
### <a name="to-create-a-new-xml-file-and-associate-it-with-an-xml-schema"></a>K vytvoření nového souboru XML a přidružte ji k schématu XML  
  
1.  Na **soubor** nabídky, přejděte na příkaz **nový**a klikněte na tlačítko **soubor**.  
  
2.  Vyberte **souboru XML** v **šablony** panelu a klikněte na tlačítko **otevřete**.  
  
     Nový soubor se otevře v editoru. Tento soubor obsahuje deklaraci XML výchozí `<?xml version="1.0" encoding="utf-8">`.  
  
3.  V okně vlastností dokumentu klikněte na tlačítko Procházet (**...** ) na **schémata** pole.  
  
     **XSD schémata** se zobrazí dialogové okno.  
  
4.  Klikněte na tlačítko **přidat**.  
  
     **Otevřete schématu XSD** se zobrazí dialogové okno.  
  
5.  Vyberte soubor hireDate.xsd a klikněte na tlačítko **otevřete**.  
  
6.  Click **OK**.  
  
     Schéma XML je nyní přidružené k dokumentu XML. Schéma XML slouží k ověření dokumentu. Také se používá technologii IntelliSense k naplnění seznamu členů platný elementů.  
  
### <a name="to-add-data"></a>Chcete-li přidat data  
  
1.  Typ `<` v podokně editor.  
  
     Zobrazí se seznam členů možné položky:  
  
    -   **!--** přidání komentáře.  
  
    -   **! DOCTYPE** přidejte typ dokumentu.  
  
    -   **?** Chcete-li přidat instrukce pro zpracování.  
  
    -   **Zaměstnanec** přidat kořenový element.  
  
2.  Vyberte **<!--** přidat uzel komentáře a stiskněte klávesu ENTER.  
  
     Editor vloží koncová značka komentáře a umístí kurzoru mezi počáteční a koncové značky pro komentáře.  
  
3.  Zadejte **souboru XML testovací**.  
  
4.  Na nový řádek, zadejte `<`a vyberte **zaměstnanec** ze seznamu členů.  
  
     Editor přidá začátku elementu XML, `<employee`. V tomto okamžiku můžete přidat atributy do elementu nebo můžete zavřít počáteční značce zadáním `>`.  
  
5.  Typ `>` zavřete značky.  
  
6.  Editor přidá koncová značka. Koncová značka se přidá s vlnovkou indikující chybu ověření. Popisek zobrazí zprávu: elementu 'zaměstnanec, má neúplné obsah. Byl očekáván "ID".  
  
7.  Typ `<` a vyberte **ID** ze seznamu členů. Pak zadejte `>`.  
  
     Přidá XML element editor `<ID></ID>`a umístí kurzor po ID počáteční značka.  
  
8.  Typ **abc**.  
  
     **Abc** text má vlnovkou. Popisek zobrazí zprávu: element "ID" má neplatnou hodnotu podle jeho datového typu.  
  
9. Klikněte pravým tlačítkem na ID elementu a vyberte **přejít k definici**.  
  
     Editor hireDate.xsd soubor se otevře v novém okně dokumentu a umístí kurzor na definici ID schématu elementu.  
  
10. Vraťte se do souboru XML a nahraďte **abc** textu s **123**.  
  
     Podtržení vlnovkou a popisu tlačítka jsou vymazány pod hodnota ID elementu. Popisek pro zaměstnance koncová značka nyní zobrazí zprávu: elementu 'zaměstnanec, má neúplné obsah. Očekávané, přijetím datum".  
  
11. Umístěte kurzor za koncovou značku ID, zadejte v `<`, vyberte datum přijetí ze seznamu členů a poté zadejte v `>`.  
  
     Přidá XML element editor `<hire-date></hire-date>`a umístí kurzor po datum přijetí počáteční značka.  
  
12. Zadejte **2003-01-10** pro hodnotu Datum přijetí.  
  
### <a name="to-format-the-xml-document"></a>K formátování v dokumentu XML  
  
- Vyberte **formátovat dokument** tlačítka panelu nástrojů editoru XML.
  
    V dokumentu XML je naformátována.  
  
### <a name="to-save-the-xml-document"></a>Uložení dokumentu XML  
  
1.  Z **soubor** nabídce vyberte možnost **uložit jako**.  
  
     **Uložit soubor jako** se zobrazí dialogové okno. Výchozí název souboru je 'XMLFile1'.  
  
2.  Zadejte název souboru a umístění v dokumentu XML a klikněte na tlačítko **Uložit**.  
  
## <a name="hiredatexsd-file"></a>hireDate.xsd souboru  
 Následující schéma soubor je používán návodu.  
  
```xml
<?xml version="1.0"?>  
<xs:schema attributeFormDefault="unqualified"  
     elementFormDefault="qualified" targetNamespace="urn:empl-hire"  
     xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="employee">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="ID" type="xs:unsignedShort" />  
        <xs:element name="hire-date" type="xs:date" />  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a>Viz také  
 [Editor XML](../xml-tools/xml-editor.md)