---
title: 'Postupy: Výběr schémat XML pro použití | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: d6fda3ef-d465-4788-8514-2f2d528d658c
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d897fe074c0215d462ff81ccd33e7d71487b1282
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63433106"
---
# <a name="how-to-select-the-xml-schemas-to-use"></a>Postupy: Výběr schémat XML pro použití
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

XML Editor obsahuje schéma mezipaměti umístěné v adresáři %InstallDir%\Xml\Schemas. Mezipaměti schématu obsahuje dobře známými schématy XML, které slouží k ověření dokumentu technologie IntelliSense a XML.  
  
 **Schémata** vlastnost dokumentu slouží k výběru jedné nebo více schématu definice jazyk (XSD) schématu XML používat. Umožní vám vybrat schémata z mezipaměti schémat nebo změnu schématu, který se nenachází v mezipaměti.  
  
 Schémata, které jste zadali se ukládají do skrytého souboru s možností uživatele řešení (.suo), spolu s všechny ostatní vlastnosti dokumentu XML. V důsledku toho není nutné znovu zadat tyto hodnoty při příštím otevření řešení.  
  
> [!NOTE]
> V editoru můžete ověřit pomocí vložené schéma nebo schéma. odkazuje `xsd:schemaLocation` atribut. Další informace najdete v tématu [ověření dokumentu XML](../xml-tools/xml-document-validation.md).  
  
### <a name="to-select-an-xml-schema-from-the-schema-cache"></a>Chcete-li vybrat schématu XML z mezipaměti schémat  
  
1. Otevření souboru v editoru XML.  
  
2. V okně Vlastnosti dokumentu, klepněte na tlačítko **schémata** pole.  
  
    **Schémat XML** se zobrazí dialogové okno. Dialogové okno obsahuje všechna schémata s příponou XSD v mezipaměti schématu (včetně schémata odkazovaná v souboru catalog.xml) a také jakékoli schéma, které je v aktuálním řešení, otevřete v sadě Visual Studio, odkazuje `xsd:schemaLocation` atribut, nebo je odkazované v **schémata** vlastnost.  
  
3. Výběr schémat pro účely ověření pomocí jedné z následujících akcí:  
  
   - Vyberte schéma uvedené v **schémat XML** dialogového okna, klikněte na tlačítko **použití** sloupec a pak vyberte **použít tohle schéma**.  
  
     -nebo-  
  
   - Výběr více schémat, které jsou uvedeny v **schémat XML** dialogového okna, klikněte pravým tlačítkem a vyberte **použít tohle schéma**.  
  
4. Klikněte na **OK**.  
  
    Seznam vybraná schémata zkopírována zpět **schémata** vlastnost dokumentu.  
  
### <a name="to-add-an-xml-schema-to-the-schema-cache"></a>Přidat do mezipaměti schématu schématu XML  
  
1. V okně Vlastnosti dokumentu, klepněte na tlačítko **schémata** pole.  
  
2. Klikněte na **Přidat**.  
  
     Tím se otevře **otevřít schéma XSD** dialogového okna.  
  
3. Vyhledejte a vyberte schémata pro přidání do mezipaměti schématu.  
  
4. Klikněte na tlačítko **otevřít**.  
  
     Schémata přidané do schématu do mezipaměti a je **použití** nastavena na hodnotu sloupce **použít tohle schéma**.  
  
### <a name="to-delete-an-xml-schema-from-the-schema-cache"></a>Chcete-li odstranit schématu XML z mezipaměti schémat  
  
1. V okně Vlastnosti dokumentu, klepněte na tlačítko **schémata** pole.  
  
2. Vyberte schéma odebrat a potom klikněte na **odebrat**.  
  
     Schéma se odebere z mezipaměti schémat v paměti, ale neodebere se ze systému souborů.  
  
    > [!NOTE]
    > Pokud stále máte odkaz na schéma prostřednictvím `schemaLocation` atribut nebo odpovídající `targetNamespace` pak **odebrat** nebude fungovat v této situaci kvůli automatické přidružení. V tomto případě se doporučuje, abyste označili schématu jako **nepoužívat vybraná schémata** v **použít** sloupce.  
  
## <a name="see-also"></a>Viz také  
 [Mezipaměti schémat](../xml-tools/schema-cache.md)   
 [Dialogové okno schémata XML](../xml-tools/xml-schemas-dialog-box.md)   
 [Editor XML](../xml-tools/xml-editor.md)
