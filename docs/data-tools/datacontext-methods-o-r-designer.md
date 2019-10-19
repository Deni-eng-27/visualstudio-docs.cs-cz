---
title: Metody DataContext (O-R Designer)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c149f4e5-3b61-4c33-892e-3e26d47f3eeb
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 0e81f2337931f565e0068a852bf9b8284350690c
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72648544"
---
# <a name="datacontext-methods-or-designer"></a>Metody DataContext (Návrhář relací objektů)

metody <xref:System.Data.Linq.DataContext> (v kontextu [LINQ to SQL nástrojů v aplikaci Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)) jsou metody třídy <xref:System.Data.Linq.DataContext>, které spouštějí uložené procedury a funkce v databázi.

Třída <xref:System.Data.Linq.DataContext> je [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] třída, která funguje jako trubka mezi SQL Server databází a třídami [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] entit mapovanými na tuto databázi. Třída <xref:System.Data.Linq.DataContext> obsahuje informace o připojovacím řetězci a metody pro připojení k databázi a manipulaci s daty v databázi. Ve výchozím nastavení třída <xref:System.Data.Linq.DataContext> obsahuje několik metod, které lze volat, například metodu <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, která odesílá aktualizovaná data z třídy [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] do databáze. Můžete také vytvořit další <xref:System.Data.Linq.DataContext> metody, které jsou mapovány na uložené procedury a funkce. Jinými slovy, volání těchto vlastních metod spustí uloženou proceduru nebo funkci v databázi, ke které je namapována metoda <xref:System.Data.Linq.DataContext>. Můžete přidat nové metody do <xref:System.Data.Linq.DataContext> třídy stejně, jako byste přidali metody pro rozšiřování libovolné třídy. V diskusích o metodách <xref:System.Data.Linq.DataContext> v kontextu **návrháře o/R**je však <xref:System.Data.Linq.DataContext> metod, které jsou mapovány na uložené procedury a funkce, které jsou popsány.

## <a name="methods-pane"></a>Podokno metody

<xref:System.Data.Linq.DataContext> metody, které se mapují k uloženým procedurám a funkcím, se zobrazí v podokně **metody** **návrháře pro/R**. Podokno **metody** je podokno podél strany podokna **entity** (hlavní návrhová plocha). Podokno **metody** obsahuje seznam všech <xref:System.Data.Linq.DataContext> metod, které jste vytvořili pomocí **návrháře o/R**. Ve výchozím nastavení je podokno **metody** prázdné. Přetažením uložených procedur nebo funkcí z **Průzkumník serveru** nebo z **Průzkumníka databáze** do **návrháře o/R** vytvoříte <xref:System.Data.Linq.DataContext> metody a naplníte podokno **metody** . Další informace naleznete v tématu [How to: Create DataContext Methods namapované na uložené procedury a funkce (O/R Designer)](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md).

> [!NOTE]
> Otevřete a zavřete podokno metody kliknutím pravým tlačítkem myši na **Návrhář pro/R** a následným kliknutím na **Skrýt podokno metody** nebo **Zobrazit podokno metody**nebo pomocí klávesové zkratky **CTRL** +**1**.

## <a name="two-types-of-datacontext-methods"></a>Dva typy metod DataContext

Metody DataContext jsou metody, které jsou mapovány na uložené procedury a funkce v databázi. Metody DataContext můžete vytvořit a přidat v podokně **metody** **návrháře pro/R**. Existují dva různé typy <xref:System.Data.Linq.DataContext> metod; ty, které vracejí jednu nebo více sad výsledků, a ty, které nezahrnují:

- <xref:System.Data.Linq.DataContext> metody, které vracejí jednu nebo více sad výsledků dotazu:

   Vytvořte tento druh metody <xref:System.Data.Linq.DataContext>, když vaše aplikace stačí spustit uložené procedury a funkce v databázi a vracet výsledky. Další informace naleznete v tématu [How to: Create DataContext Methods namapované na uložené procedury a funkce (O/R Designer)](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md), System. data. Linq. ISingleResult \<T > a <xref:System.Data.Linq.IMultipleResults>.

- <xref:System.Data.Linq.DataContext> metody, které nevracejí sady výsledků dotazu: například vložení, aktualizace a odstranění pro konkrétní třídu entity.

   Vytvořte tento druh metody <xref:System.Data.Linq.DataContext>, pokud má aplikace spouštět uložené procedury místo použití výchozího [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] chování pro ukládání upravených dat mezi třídou entity a databází. Další informace naleznete v tématu [Postupy: přiřazení uložených procedur pro provádění aktualizací, vkládání a odstraňování (O/R Designer)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md).

## <a name="return-types-of-datacontext-methods"></a>Návratové typy metod DataContext

Když přetáhnete uložené procedury a funkce z **Průzkumník serveru** nebo **Průzkumníka databáze** do **návrháře o/R**, návratový typ generované <xref:System.Data.Linq.DataContext> metody se liší v závislosti na tom, kde položku vyřadíte. Vyřazení položek přímo na existující třídu entity vytvoří metodu <xref:System.Data.Linq.DataContext> s návratovým typem třídy entity; vyřazení položek do prázdné oblasti **návrháře o/R** (v obou podoknech) vytvoří metodu <xref:System.Data.Linq.DataContext>, která vrátí automaticky generovaný typ. Automaticky generovaný typ má název, který se shoduje s uloženou procedurou nebo názvem funkce a vlastnostmi, které jsou mapovány na pole vracené uloženou procedurou nebo funkcí.

> [!NOTE]
> Můžete změnit návratový typ metody <xref:System.Data.Linq.DataContext> poté, co ji přidáte do podokna metody. Chcete-li zkontrolovat nebo změnit návratový typ metody <xref:System.Data.Linq.DataContext>, vyberte ji a v okně **vlastnosti** Zkontrolujte vlastnost **návratový typ** . Další informace naleznete v tématu [Postupy: Změna návratového typu metody DataContext (O/R Designer)](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md).

Objekty, které přetáhnete z databáze na plochu návrháře O/R, se pojmenují automaticky na základě názvu objektů v databázi. Pokud přetáhnete stejný objekt více než jednou, přidá se číslo na konec nového názvu, který rozlišuje názvy. Pokud názvy objektů databáze obsahují mezery nebo znaky nejsou podporovány v Visual Basic nebo C#, je místo nebo neplatný znak nahrazen podtržítkem.

## <a name="see-also"></a>Viz také:

- [Nástroje LINQ to SQL v aplikaci Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [Uložené procedury](/dotnet/framework/data/adonet/sql/linq/stored-procedures)
- [Postupy: Vytvoření metod DataContext namapovaných na uložené procedury a funkce (Návrhář relací objektů)](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)
- [Postupy: Přiřazení uložených procedur za účelem aktualizací, vkládání a odstraňování (Návrhář relací objektů)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)
- [Návod: Přizpůsobení chování tříd entit při vložení, aktualizaci a odstranění](../data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes.md)
- [Návod: vytváření tříd LINQ to SQL (Návrhář O-R)](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)