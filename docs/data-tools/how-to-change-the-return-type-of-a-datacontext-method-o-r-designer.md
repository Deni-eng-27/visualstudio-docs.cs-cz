---
title: 'Postupy: Změnu návratového typu metody DataContext (Návrhář O-R)'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c5b66bff-6dbb-43c0-bffa-317133ca5b9e
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: 77d7b98367e343f90827429ad50be91527f7f303
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53939434"
---
# <a name="how-to-change-the-return-type-of-a-datacontext-method-or-designer"></a>Postupy: Změnu návratového typu metody DataContext (O/R Designer)
Návratový typ <xref:System.Data.Linq.DataContext> – metoda (založeno na uložená procedura nebo funkce) se liší v závislosti na tom, kde vyřaďte uloženou proceduru nebo funkci v **O/R Designer**. Pokud přetáhnete položku přímo do existující entity třídy, <xref:System.Data.Linq.DataContext> metodu, která má návratový typ třídy entita se vytvoří (Pokud je schéma dat vrácené uloženou proceduru nebo funkci odpovídá obrazec třídy entity). Pokud přetáhnete položku na prázdnou oblast **O/R Designer**, <xref:System.Data.Linq.DataContext> vytvořené metodou, která vrací automaticky generovanému typu. Můžete změnit návratový typ <xref:System.Data.Linq.DataContext> metoda po přidání do podokna metody. Zkontrolovat nebo změnit návratový typ <xref:System.Data.Linq.DataContext> metoda, vyberte ho a klikněte **návratový typ** vlastnost v **vlastnosti** okna.

> [!NOTE]
>  Nejde vrátit zpět <xref:System.Data.Linq.DataContext> metody, které mají návratový typ nastavena na třídu entity k vrácení automaticky generovaný typ pomocí **vlastnosti** okna. Vrátit zpět <xref:System.Data.Linq.DataContext> metodu pro návrat na automaticky generovaný typ, je třeba přetáhnout na původní objekt do databáze **O/R Designer** znovu.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="to-change-the-return-type-of-a-datacontext-method-from-the-auto-generated-type-to-an-entity-class"></a>Změna návratového typu metody DataContext z automaticky generovaný typ pro třídu entity

1.  Vyberte <xref:System.Data.Linq.DataContext> metoda v podokně metody.

2.  Vyberte **návratový typ** v **vlastnosti** okna a pak vyberte dostupné entity třídy v **návratový typ** seznamu. Pokud třída požadované entity není v seznamu, přidejte ji tak nebo jej vytvořit v **O/R Designer** ho přidat do seznamu.

3.  Uložit *dbml* souboru.

## <a name="to-change-the-return-type-of-a-datacontext-method-from-an-entity-class-back-to-the-auto-generated-type"></a>Chcete-li změnit zpět na automaticky generovaný typ návratového typu metody DataContext z třídy entity

1.  Vyberte <xref:System.Data.Linq.DataContext> metodu **metody** podokně a odstraňte ho.

2.  Přetáhněte objekt databáze z **Průzkumníka serveru** nebo **Průzkumník databáze** na prázdnou oblast **O/R Designer**.

3.  Uložit *dbml* souboru.

## <a name="see-also"></a>Viz také:

- [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [Metody DataContext (O/R Designer)](../data-tools/datacontext-methods-o-r-designer.md)
- [Postupy: Vytvoření metod DataContext namapovaných na uložené procedury a funkce (O/R Designer)](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)