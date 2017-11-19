---
title: "Postupy: Konfigurace dědičnosti pomocí návrháře O-R | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e594af12-e777-434a-bc08-7dd2dac84cdc
caps.latest.revision: "4"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 8b4c2ac7790bd2c5114b04a6119702013d54825b
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="how-to-configure-inheritance-by-using-the-or-designer"></a>Postupy: Konfigurace dědičnosti pomocí Návrhář relací objektů
[!INCLUDE[vs_ordesigner_long](../data-tools/includes/vs_ordesigner_long_md.md)] ([!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]) Podporuje koncept dědění jedné tabulky, jak často jsou implementované v relačním systémech. V jedné tabulce dědičnosti je jedné databáze tabulku, která obsahuje pole pro informace nadřazené a podřízené informace. Pomocí relačních dat sloupce diskriminátoru obsahuje hodnotu, která určuje, které třídy žádné záznam patří.  
  
Představte si třeba osob tabulku, která obsahuje všechny zaměstnaní společnosti. Někteří uživatelé mají zaměstnanci a někteří uživatelé mají správci. Tabulka lidí, který obsahuje sloupec s názvem `EmployeeType` s hodnotou 1 pro správce a hodnota 2 pro zaměstnance; Toto je sloupce diskriminátoru. V tomto scénáři můžete vytvořit podtřídou třídy zaměstnanci a naplnit třída se pouze záznamy, které mají `EmployeeType` hodnota 2. Rovněž můžete odebrat sloupce, které se nevztahují z každé ze třídy.  
  
Vytváření objektový model, který používá dědičnosti (a odpovídá na relační data) může být poněkud matoucí. Následující postup popisuje kroky potřebné pro konfiguraci dědičnosti se Návrhář relací objektů. Následující obecné kroky bez odkazující na existující tabulky a sloupce může být obtížné, takže poskytuje návod, který používá data. Pro podrobné podrobné pokyny pro konfiguraci dědičnosti, pomocí [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], najdete v části [návod: vytváření třídy LINQ to SQL podle pomocí jedné tabulky dědičnosti (Návrhář relací objektů)](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md).  
  
## <a name="to-create-inherited-data-classes"></a>K vytvoření zděděné datových tříd
  
1.  Otevřete [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] přidáním **třídy LINQ to SQL** položky do existujícího projektu Visual Basic a C#.  
  
2.  Přetáhněte tabulku, kterou chcete použít jako základní třída na [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].  
  
3.  Přetáhněte druhé kopie v tabulce na [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] a přejmenujte ji. Je to odvozené třídy nebo podtřídy.  
  
4.  Klikněte na tlačítko **dědičnosti** v **Návrhář relací objektů** kartě **sada nástrojů**a pak klikněte na tlačítko podtřídy (tabulky, můžete přejmenovat) a připojte ho k základní třídy.  
  
    > [!NOTE]
    >  Klikněte **dědičnosti** položky v **sada nástrojů** a uvolnění tlačítka myši, klikněte na druhé kopie třídy, které jste vytvořili v kroku 3 a pak klikněte na první třídy, které jste vytvořili v kroku 2. První třídy bude odkazovat na šipku v řádku dědičnosti.  
  
5.  V každé třídě odstraňte všechny vlastnosti objektu, které nechcete zobrazit a které nejsou používány k přidružení. Pokoušíte se odstranit objekt vlastnosti používané pro přidružení dojde k chybě: [vlastnost \<název vlastnosti > nelze odstranit, protože se účastní přidružení \<název přidružení >](../data-tools/the-property-property-name-cannot-be-deleted-because-it-is-participating-in-the-association-association-name.md).  
  
    > [!NOTE]
    >  Protože odvozené třídy dědí vlastnosti definované ve své základní třídy, nemůže být stejné sloupce definovaný ve každá třída. (Sloupce jsou implementované jako vlastnosti). Vytváření sloupců v odvozené třídě můžete povolit tak modifikátor dědičnosti na vlastnost v základní třídě. Další informace najdete v tématu [základní informace o dědičnosti (Visual Basic)](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics).  
  
6.  Vyberte řádek dědičnosti ve [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].  
  
7.  V **vlastnosti** nastavte **diskriminátoru vlastnost** na název sloupce, který se používá k rozlišení záznamy v tříd.  
  
8.  Nastavte **odvozené třídy diskriminátoru hodnota** vlastnost na hodnotu v databázi, která označí jako zděděné typu záznamu. (Toto je hodnota, který je uložený ve sloupci diskriminátoru a který se používá k určení zděděné třídy.)  
  
9. Nastavte **hodnota diskriminátoru základní třídy** vlastnost na hodnotu, která označí jako základní typ záznamu. (Toto je hodnota, který je uložený ve sloupci diskriminátoru a který se používá k určení základní třídy.)  
  
10. Volitelně můžete také nastavit **dědičnosti výchozí** vlastnosti k určení typu v hierarchii dědičnosti, která se používá při načítání řádků, které neodpovídají žádné definované dědičnosti kódu. Jinými slovy, pokud má záznam hodnotu v jeho sloupce diskriminátoru který neodpovídá hodnotě buď **odvozené třídy diskriminátoru hodnotu** nebo **hodnota diskriminátoru základní třídy** vlastnosti, záznamu načte do typ určený jako **dědičnosti výchozí**.  
  
## <a name="see-also"></a>Viz také
[Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
[Návod: Vytváření třídy LINQ to SQL (Návrhář O-R)](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)   
[PAVE, co je nového pro vývoj aplikací dat v sadě Visual Studio 2012](http://msdn.microsoft.com/en-us/3d50d68f-5f44-4915-842f-6d42fce793f1)   
[Přístup k datům v sadě Visual Studio](../data-tools/accessing-data-in-visual-studio.md)   
[Technologie LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)   
[Návod: Vytvoření třídy LINQ to SQL s použitím dědičnosti jedné tabulky (Návrhář relací objektů)](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)   
[Základní informace o dědičnosti (Visual Basic)](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)  
[Dědičnost](/dotnet/csharp/programming-guide/classes-and-structs/inheritance)