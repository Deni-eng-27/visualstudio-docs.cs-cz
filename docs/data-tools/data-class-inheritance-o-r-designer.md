---
title: Dědičnost datových tříd (O-R Designer)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: af32653c-f4e6-4217-8c5a-e32b322b4918
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 7cb47913f2b14867be4dcc8f98688ab2d2a858d9
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72648559"
---
# <a name="data-class-inheritance-or-designer"></a>Dědičnost datových tříd (Návrhář relací objektů)

Stejně jako jiné objekty mohou LINQ to SQL třídy používat dědičnost a být odvozeny od jiných tříd. V kódu můžete určit vztahy dědičnosti mezi objekty tím, že deklarujete, že jedna třída dědí z jiné třídy. V databázi jsou vztahy dědičnosti vytvářeny několika způsoby. **Návrhář relací objektů** (**O/R Designer**) podporuje koncept dědičnosti s jednou tabulkou, protože je často implementován v relačních systémech.

V případě dědičnosti s jednou tabulkou existuje jedna databázová tabulka, která obsahuje sloupce pro základní i odvozené třídy. U relačních dat obsahuje sloupec diskriminátor hodnotu, která určuje, do které třídy daný záznam patří. Vezměte například `Persons` tabulku, která obsahuje všechny zaměstnané společností. Někteří lidé jsou zaměstnanci a někteří lidé jsou manažeři. Tabulka `Persons` obsahuje sloupec s názvem `Type` s hodnotou 1 pro manažery a hodnotou 2 pro zaměstnance. Sloupec `Type` je sloupec diskriminátor. V tomto scénáři můžete vytvořit podtřídu zaměstnanců a naplnit třídu pouze záznamy, které mají hodnotu `Type` 2.

Při konfiguraci dědičnosti v třídách entit pomocí [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] přetáhněte jedinou tabulku, která obsahuje data dědičnosti, do návrháře dvakrát: jednou pro každou třídu v hierarchii dědičnosti. Po přidání tabulek do návrháře je připojte pomocí položky dědičnosti z panelu nástrojů **Návrhář relací objektů** a pak nastavte čtyři vlastnosti dědičnosti v okně **vlastnosti** .

## <a name="inheritance-properties"></a>Vlastnosti dědičnosti

V následující tabulce jsou uvedeny vlastnosti dědičnosti a jejich popis:

|Vlastnost|Popis|
|--------------|-----------------|
|**Vlastnost diskriminátoru**|Vlastnost (namapovaná na sloupec), která určuje, do které třídy aktuální záznam patří.|
|**Hodnota diskriminátoru základní třídy**|Hodnota (ve sloupci určeném jako **vlastnost diskriminátoru**), která určuje, že záznam je základní třídou.|
|**Hodnota diskriminátoru odvozené třídy**|Hodnota (ve vlastnosti určené jako **vlastnost diskriminátor**), která určuje, že záznam je odvozenou třídou.|
|**Výchozí dědičnost**|Třída, která je naplněna v případě, že hodnota ve vlastnosti určené jako **vlastnost diskriminátoru** neodpovídá **hodnotě diskriminátoru základní třídy** ani **hodnoty diskriminátoru odvozené třídy**.|

Vytvoření objektového modelu, který používá dědičnost a odpovídá relačním datům, může být poněkud matoucí. V tomto tématu najdete informace o základních konceptech a jednotlivých vlastnostech, které jsou potřeba ke konfiguraci dědičnosti. V následujících tématech najdete srozumitelnější vysvětlení způsobu konfigurace dědičnosti s **návrhářem pro/R**.

|Téma|Popis|
|-----------|-----------------|
|[Postupy: Konfigurace dědičnosti pomocí Návrháře relací objektů](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md)|Popisuje, jak nakonfigurovat třídy entit, které používají dědičnost s jednou tabulkou, pomocí **návrháře o/R**.|
|[Návod: vytváření tříd LINQ to SQL pomocí dědičnosti s jednou tabulkou (O/R Designer)](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)|Poskytuje podrobné pokyny ke konfiguraci tříd entit, které používají dědičnost s jednou tabulkou, pomocí **návrháře o/R**.|

## <a name="see-also"></a>Viz také:

- [Nástroje LINQ to SQL v aplikaci Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [Návod: vytváření tříd LINQ to SQL (Návrhář O-R)](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)
- [Návod: vytváření tříd LINQ to SQL pomocí dědičnosti s jednou tabulkou (O/R Designer)](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)
- [Začínáme](/dotnet/framework/data/adonet/sql/linq/getting-started)