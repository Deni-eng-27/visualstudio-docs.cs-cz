---
title: Přehled modelu objektů aplikace Word
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Word object model
- Word [Office development in Visual Studio], object model
- object models [Office development in Visual Studio], Office
- object models [Office development in Visual Studio], Word
- objects [Office development in Visual Studio], Office object models
- Office object models
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0005dd52c9c70edf41c9fc32c51e555748c78bfc
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35258451"
---
# <a name="word-object-model-overview"></a>Přehled modelu objektů aplikace Word
  Při vývoji řešení aplikace Word v sadě Visual Studio komunikovat s model objektů aplikace Word. Tento objektový model se skládá z třídy a rozhraní, které jsou uvedeny v primární spolupracující sestavení pro aplikaci Word a jsou definovány v <xref:Microsoft.Office.Interop.Word> oboru názvů.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Toto téma obsahuje stručný přehled model objektů aplikace Word. Zdroje, kde můžete další informace o celý model objektů aplikace Word najdete v tématu [pomocí dokumentace modelu objektů aplikace Word](#WordOMDocumentation).  
  
 Informace o používání model objektů aplikace Word k provádění specifických úloh najdete v následujících tématech:  
  
-   [Práce s dokumenty](../vsto/working-with-documents.md)  
  
-   [Práce s textem v dokumentech](../vsto/working-with-text-in-documents.md)  
  
-   [Práce s tabulkami](../vsto/working-with-tables.md)  
  
##  <a name="understanding"></a> Pochopení model objektů aplikace Word  
 Word poskytuje stovky objekty, se kterými můžete pracovat. Tyto objekty jsou uspořádány do hierarchie, která přesně dodržuje uživatelské rozhraní. V horní části hierarchie <xref:Microsoft.Office.Interop.Word.Application> objektu. Tento objekt představuje aktuální instanci aplikace Word. <xref:Microsoft.Office.Interop.Word.Application> Objekt obsahuje <xref:Microsoft.Office.Interop.Word.Document>, <xref:Microsoft.Office.Interop.Word.Selection>, <xref:Microsoft.Office.Interop.Word.Bookmark>, a <xref:Microsoft.Office.Interop.Word.Range> objekty. Každý z těchto objektů má mnoho metody a vlastnosti, které dostanete pracovat a manipulovat s daným objektem.  
  
 Následující obrázek znázorňuje jedno zobrazení těchto objektů v hierarchii model objektů aplikace Word.  
  
 ![Model objektů aplikace Word obrázek](../vsto/media/wrwordobjectmodel.gif "obrázek Model objektů aplikace Word")  
  
 Na první pohled objekty jsou překrytí. Například <xref:Microsoft.Office.Interop.Word.Document> a <xref:Microsoft.Office.Interop.Word.Selection> objekty jsou obě členy <xref:Microsoft.Office.Interop.Word.Application> objektu, ale <xref:Microsoft.Office.Interop.Word.Document> objektu je také členem <xref:Microsoft.Office.Interop.Word.Selection> objektu. Jak <xref:Microsoft.Office.Interop.Word.Document> a <xref:Microsoft.Office.Interop.Word.Selection> objekty obsahují <xref:Microsoft.Office.Interop.Word.Bookmark> a <xref:Microsoft.Office.Interop.Word.Range> objekty. Překrytí existuje, protože přistupujete stejný typ objektu několika způsoby. Například použijete formátování <xref:Microsoft.Office.Interop.Word.Range> objekt; ale můžete chtít přístup k rozsahu aktuálního výběru, konkrétní odstavce, oddílu nebo celý dokument.  
  
 Následující části popisují stručně nejvyšší úrovně objekty a jejich vzájemné interakce mezi sebou. Tyto objekty zahrnují následujících pět:  
  
-   objekt aplikace  
  
-   Objekt dokumentu  
  
-   Výběr objektu  
  
-   rozsah – objekt  
  
-   BOOKMARK – objekt  
  
 Kromě model objektů aplikace Word projektech pro systém Office v sadě Visual Studio poskytují *hostitele položky* a *hostování ovládacích prvků* , rozšířit některé objekty ve model objektů aplikace Word. Hostitelských položek a hostitelských ovládacích prvků chovají jako Word objekty, které budou rozšíření, ale mají také další funkce, jako je například funkce datové vazby a další události. Další informace najdete v tématu [automatizace aplikace Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md) a [hostitele položky a hostitelem Přehled ovládacích prvků](../vsto/host-items-and-host-controls-overview.md).  
  
### <a name="application-object"></a>objekt aplikace  
 <xref:Microsoft.Office.Interop.Word.Application> Objekt představuje aplikaci Word a je nadřazeného všechny ostatní objekty. Její členy obvykle platí pro aplikaci Word jako celek. Jeho vlastnosti a metody můžete použít k řízení prostředí aplikace Word.  
  
 V doplňku VSTO projekty, získáte přístup <xref:Microsoft.Office.Interop.Word.Application> objekt pomocí `Application` pole z `ThisAddIn` – třída. Další informace najdete v tématu [doplňků Program VSTO](../vsto/programming-vsto-add-ins.md).  
  
 V projekty na úrovni dokumentu, získáte přístup <xref:Microsoft.Office.Interop.Word.Application> objekt pomocí <xref:Microsoft.Office.Tools.Word.Document.Application%2A> vlastnost `ThisDocument` – třída.  
  
### <a name="document-object"></a>Objekt dokumentu  
 <xref:Microsoft.Office.Interop.Word.Document> Objekt je důležitá pro programování aplikace Word. Reprezentuje dokument a veškerý jeho obsah. Při otevření dokumentu nebo vytvořit nový dokument, vytvořte novou <xref:Microsoft.Office.Interop.Word.Document> objekt, který je přidán do <xref:Microsoft.Office.Interop.Word.Documents> kolekce <xref:Microsoft.Office.Interop.Word.Application> objektu. Dokument, který je vybrán se nazývá aktivní dokument. Je zobrazena <xref:Microsoft.Office.Interop.Word._Application.ActiveDocument%2A> vlastnost <xref:Microsoft.Office.Interop.Word.Application> objektu.  
  
 Nástroje pro vývoj pro Office v sadě Visual Studio rozšiřují <xref:Microsoft.Office.Interop.Word.Document> objekt tím, že poskytuje <xref:Microsoft.Office.Tools.Word.Document> typu. Tento typ je *hostitelská položka* který umožňuje přístup ke všem funkcím <xref:Microsoft.Office.Interop.Word.Document> objektu a přidá další události a možnost přidávat spravované ovládací prvky.  
  
 Když vytvoříte projekt na úrovni dokumentu a, dostanete <xref:Microsoft.Office.Tools.Word.Document> členy pomocí vygenerovaného `ThisDocument` třídy ve vašem projektu. Můžete přístup ke členům v <xref:Microsoft.Office.Tools.Word.Document> hostitelská položka pomocí **mi** nebo **to** klíčová slova z kódu v `ThisDocument` třídy, nebo pomocí `Globals.ThisDocument` z kódu mimo `ThisDocument` Třída. Další informace najdete v tématu [programu úpravy na úrovni dokumentů](../vsto/programming-document-level-customizations.md). Například pokud chcete vybrat prvním odstavci v dokumentu, použijte následující kód.  
  
 [!code-vb[Trin_VstcoreWordAutomation#120](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#120)]
 [!code-csharp[Trin_VstcoreWordAutomation#120](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#120)]  
  
 V doplňku VSTO projekty, můžete vygenerovat <xref:Microsoft.Office.Tools.Word.Document> hostitele položky v době běhu. Vygenerovaný hostitelská položka můžete použít k přidávání ovládacích prvků v přidružené dokumentu. Další informace najdete v tématu [dokumentů rozšířit aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
### <a name="selection-object"></a>Výběr objektu  
 <xref:Microsoft.Office.Interop.Word.Selection> Představuje oblasti, který je aktuálně vybraný objekt. Při provádění operace v uživatelském rozhraní aplikace Word, jako je například tučné text, vyberte, nebo zvýrazněte text a použijte formátování. <xref:Microsoft.Office.Interop.Word.Selection> Objektu je vždy k dispozici v dokumentu. Pokud není nic vybráno, pak reprezentuje bod vložení. Kromě toho můžete výběr zahrnuje několik bloků textu, které nejsou souvislé.  
  
### <a name="range-object"></a>rozsah – objekt  
 <xref:Microsoft.Office.Interop.Word.Range> Objekt představuje souvislý oblasti v dokumentu a je definován počáteční pozice znaku a koncová pozice znaku. Nejste omezeni na jednu <xref:Microsoft.Office.Interop.Word.Range> objektu. Můžete definovat více <xref:Microsoft.Office.Interop.Word.Range> objekty ve stejném dokumentu. A <xref:Microsoft.Office.Interop.Word.Range> objekt má následující vlastnosti:  
  
-   Může sestávat ze samotné kurzor, rozsah textu nebo celý dokument.  
  
-   Obsahuje netisknutelné znaky, jako jsou mezery, tabulátory a značky odstavce.  
  
-   Může být oblast určeném aktuálním výběrem, nebo může představovat oblast liší od aktuální výběr.  
  
-   Není zobrazená v dokumentu, na rozdíl od výběr, který je vždy zobrazen.  
  
-   Se neukládají s dokumentem a existuje pouze tehdy, když je kód spuštěn.  
  
 Při vložení textu na konci tohoto rozsahu aplikace Word automaticky rozšíří oblasti zahrnout vložený text.  
  
### <a name="content-control-objects"></a>Objekty obsahu ovládacího prvku  
 A <xref:Microsoft.Office.Interop.Word.ContentControl> poskytuje způsob, jak vám umožňují řídit vstup a prezentace textu a jiné typy obsahu v dokumentech aplikace Word. A <xref:Microsoft.Office.Interop.Word.ContentControl> můžete zobrazit několika různých typů uživatelského rozhraní, které jsou optimalizované pro použití v dokumentech aplikace Word, například ovládacího prvku formátovaným textem, výběr data nebo pole se seznamem. Můžete použít také <xref:Microsoft.Office.Interop.Word.ContentControl> uživatelům zabránit v úpravy části dokumentu nebo šablony.  
  
 Visual Studio rozšiřuje <xref:Microsoft.Office.Interop.Word.ContentControl> objektu do několika různých hostitelské ovládací prvky. Zatímco <xref:Microsoft.Office.Interop.Word.ContentControl> objekt můžete zobrazit všechny různých typů uživatelského rozhraní, které jsou k dispozici pro ovládací prvky obsahu, Visual Studio poskytuje jiný typ pro každý ovládací prvek. Například můžete použít <xref:Microsoft.Office.Tools.Word.RichTextContentControl> můžete použít k vytvoření ovládacího prvku formátovaným textem, nebo <xref:Microsoft.Office.Tools.Word.DatePickerContentControl> vytvořit výběr data. Tyto hostitelské ovládací prvky chovají jako nativního <xref:Microsoft.Office.Interop.Word.ContentControl>, avšak mají další události a možnosti pro datové vazby. Další informace najdete v tématu [ovládací prvky obsahu](../vsto/content-controls.md).  
  
### <a name="bookmark-object"></a>BOOKMARK – objekt  
 <xref:Microsoft.Office.Interop.Word.Bookmark> Objekt představuje souvislý oblasti v dokumentu, s počáteční pozice a koncovou pozici. Záložky můžete označit na místo v dokumentu, nebo jako kontejner pro text v dokumentu. A <xref:Microsoft.Office.Interop.Word.Bookmark> objekt může obsahovat kurzor nebo mít stejnou velikost jako celý dokument. A <xref:Microsoft.Office.Interop.Word.Bookmark> má následující vlastnosti, které se kromě nastavit <xref:Microsoft.Office.Interop.Word.Range> objektu:  
  
-   Záložka můžete pojmenovat v době návrhu.  
  
-   <xref:Microsoft.Office.Interop.Word.Bookmark> objekty se ukládají s dokumentu a proto nebudou odstraněny, pokud kód zastaví nebo dokumentu je uzavřený.  
  
-   Záložky můžete skrytý nebo viditelný provedené nastavení <xref:Microsoft.Office.Interop.Word.View.ShowBookmarks%2A> vlastnost <xref:Microsoft.Office.Interop.Word.View> do objektu **false** nebo **true**.  
  
 Visual Studio rozšiřuje <xref:Microsoft.Office.Interop.Word.Bookmark> objekt tím, že poskytuje <xref:Microsoft.Office.Tools.Word.Bookmark> hostování ovládacího prvku. <xref:Microsoft.Office.Tools.Word.Bookmark> Hostitelského ovládacího prvku se chová jako nativní <xref:Microsoft.Office.Interop.Word.Bookmark>, ale má další události a možnosti pro datové vazby. Data lze vázat k ovládacímu prvku záložek na dokument stejným způsobem, že vázat data na textové pole ve formuláři Windows. Další informace najdete v tématu [Bookmark – ovládací prvek](../vsto/bookmark-control.md).  
  
##  <a name="WordOMDocumentation"></a> Pomocí dokumentace modelu objektů aplikace Word  
 Úplné informace o model objektů aplikace Word najdete odkaz na aplikaci Word primární spolupracující sestavení (PIA) a Visual Basic for Applications (VBA) odkaz na objekt modelu.  
  
### <a name="primary-interop-assembly-reference"></a>Odkaz sestavení primární spolupráce  
 Word PIA referenční dokumentaci k nástroji popisuje typy v sestavení primární spolupráce pro aplikaci Word. Tato dokumentace je k dispozici z následujícího umístění: [referenční primární spolupracující sestavení Wordu 2010](http://go.microsoft.com/fwlink/?LinkId=189588).  
  
 Další informace o návrhu PIA slova, jako jsou rozdíly mezi třídy a rozhraní v primární a jak jsou implementované události v primární, najdete v části [přehled třídy a rozhraní v primární spolupracující sestavení Office](http://go.microsoft.com/fwlink/?LinkId=189592).  
  
### <a name="vba-object-model-reference"></a>Odkaz na objekt modelu VBA  
 Reference objektu modelu VBA dokumenty model objektů aplikace Word, jako je vystaven VBA kód. Další informace najdete v tématu [Wordu 2010 odkaz na objekt modelu](http://go.microsoft.com/fwlink/?LinkId=199772).  
  
 Všechny objekty a členy ve model odkaz na VBA odpovídají typy a členy v PIA aplikace Word. Například odpovídá objektu dokumentu ve model odkaz na VBA <xref:Microsoft.Office.Interop.Word.Document> objekt v PIA aplikace Word. I když reference VBA objektu modelu poskytuje příklady kódu pro většinu vlastností, metod a událostí, musí překládat VBA kód v této referenci do jazyka Visual Basic nebo Visual C# Pokud chcete používat aplikace Word projektu, abyste vytvořili pomocí sady Visual Studio.  
  
## <a name="see-also"></a>Viz také:  
 [Primární spolupracující sestavení sady Office](../vsto/office-primary-interop-assemblies.md)   
 [Automatizace aplikace Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md)   
 [Práce s dokumenty](../vsto/working-with-documents.md)   
 [Práce s textem v dokumentech](../vsto/working-with-text-in-documents.md)   
 [Práce s tabulkami](../vsto/working-with-tables.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  