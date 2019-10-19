---
title: Aktualizace dat pomocí TableAdapter | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- data [Visual Studio], saving
- data [Visual Studio], TableAdapters
- updating data, TableAdapters
- TableAdapters, updating data
- data [Visual Studio], updating
- saving data
ms.assetid: 5e32e10e-9bac-4969-9bdd-b8f6919d3516
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 312bf75100d2b9b270b45776c5f7ded21ab6ac52
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72602337"
---
# <a name="update-data-by-using-a-tableadapter"></a>Aktualizace dat pomocí objektu TableAdapter
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Po úpravě a ověření dat ve vaší datové sadě můžete aktualizovaná data odeslat zpět do databaseby volání metody `Update` třídy TableAdapter. Metoda `Update` aktualizuje jedinou datovou tabulku a spustí správný příkaz (INSERT, UPDATE nebo DELETE) na základě <xref:System.Data.DataRow.RowState%2A> každého řádku dat v tabulce. Pokud má datová sada související tabulky, aplikace Visual Studio vygeneruje třídu TableAdapterManager, kterou použijete k provedení aktualizací. Třída TableAdapterManager zajišťuje, že aktualizace budou provedeny ve správném pořadí na základě omezení cizího klíče, které jsou definovány v databázi. Při použití ovládacích prvků vázaných na data vytvoří architektura datové vazby členskou proměnnou třídy TableAdapterManager s názvem tableAdapterManager. Další informace najdete v tématu [hierarchický přehled aktualizací](https://msdn.microsoft.com/library/c4f8e8b9-e4a5-4a02-8462-d03d1e8222d6).

> [!NOTE]
> Když se pokusíte aktualizovat zdroj dat obsahem datové sady, můžete získat chyby. Aby se předešlo chybám, doporučujeme, abyste thatyou kód, který volá metodu `Update` adaptéru do `try` / bloku `catch`.

 Přesný postup pro aktualizaci zdroje dat se může lišit v závislosti na obchodních potřebách, ale obsahuje následující kroky:

1. Zavolejte `Update`ovou metodu adaptéru ve `try` / bloku `catch`.

2. Pokud je zachycena výjimka, vyhledejte řádek dat, který způsobil chybu. Další informace naleznete v tématu [How to: Vyhledání řádků s chybami](https://msdn.microsoft.com/library/1fa907c5-fe66-4f29-a253-2b97b900050c).

3. Odsouhlasení problému na řádku dat (pokud můžete, nebo zadáním neplatného řádku pro úpravu), a potom zkuste aktualizaci zopakovat (<xref:System.Data.DataRow.HasErrors%2A> <xref:System.Data.DataTable.GetErrors%2A>).

## <a name="savedata-to-a-database"></a>SaveData k databázi
 Zavolejte metodu `Update` TableAdapter. Předejte název tabulky dat obsahující hodnoty, které mají být zapsány do databáze.

#### <a name="to-update-a-database-by-using-a-tableadapter"></a>Aktualizace databáze pomocí TableAdapter

- Uzavřete `Update` metodu TableAdapter do `try` / bloku `catch`. Následující příklad ukazuje, jak aktualizovat obsah `Customers` tabulky v `NorthwindDataSet` v rámci `try` / `catch` bloku.

     [!code-csharp[VbRaddataSaving#9](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form3.cs#9)]
     [!code-vb[VbRaddataSaving#9](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form3.vb#9)]

## <a name="see-also"></a>Viz také
 [Ukládání dat zpět do databáze](../data-tools/save-data-back-to-the-database.md)
