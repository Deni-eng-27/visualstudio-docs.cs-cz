---
title: Fragmenty XML | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 348dbf64-3f09-4fff-b47a-a7ecdf3221cc
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 5e2fbba9006c1621b8f98084d4ffd4c637be1127
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68147156"
---
# <a name="xml-snippets"></a>Fragmenty XML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

XML Editor nabízí funkci *fragmentů XML*, který umožňuje rychlejší vytváření souborů XML. Můžete znovu použít fragmentů XML tak, že vloží do vašich souborů. Můžete také vygenerovat data XML na základě schématu schématu XML definice jazyk (XSD).  
  
## <a name="reusable-xml-snippets"></a>Opakovaně použitelné XML fragmentů  
 XML Editor obsahuje mnoho fragmentů kódu, které se týkají několik běžných úloh. To umožňuje snadno vytvářet soubory XML. Pokud bylo vytváření schématu XML, například pomocí "Komplexních prvků typu sekvenci" a "Jednoduchý typ elementu" fragmenty kódu vloží následující text do souboru XML. Pak změníte `name` hodnotu tak, aby odpovídala vašim potřebám.  
  
```  
<xs:element name="name">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="name">  
        <xs:simpleType>  
          <xs:restriction base="xs:string"></xs:restriction>  
        </xs:simpleType>  
      </xs:element>  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Fragmenty kódu můžete vložit dvěma způsoby. **Vložit fragment** příkaz vloží fragment kódu XML na pozici kurzoru. **Obklopit fragmentem** příkaz zabalí fragment kódu XML okolo vybraného textu. Buď nejsou k dispozici i příkazy z **IntelliSense** podnabídky **upravit** nabídky, nebo v místní nabídce editoru.  
  
 Další informace najdete v tématu [jak: Použití fragmentů XML](../xml-tools/how-to-use-xml-snippets.md).  
  
## <a name="schema-generated-xml-snippets"></a>Generované schématu XML fragmentů  
 XML editor má také možnost generování fragmentu XML ze schématu XML. Tato funkce umožňuje naplnit k elementu pomocí elementů XML generované informace o schématu pro daný element.  
  
 Další informace najdete v tématu [jak: Generování fragmentu XML ze schématu XML](../xml-tools/how-to-generate-an-xml-snippet-from-an-xml-schema.md).  
  
## <a name="create-new-xml-snippets"></a>Vytvoření nových fragmentů kódu XML  
 Kromě fragmenty kódu, které jsou součástí [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual Studio ve výchozím nastavení můžete také vytvořit a použít vlastní fragmenty kódu XML.  
  
 Další informace najdete v tématu [jak: Vytváření fragmentů XML](../xml-tools/how-to-create-xml-snippets.md).  
  
## <a name="see-also"></a>Viz také  
 [Editor XML](../xml-tools/xml-editor.md)
