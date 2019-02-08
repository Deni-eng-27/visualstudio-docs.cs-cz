---
title: Aktualizace dat pomocí objektu TableAdapter
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], saving
- data [Visual Studio], TableAdapters
- updating data, TableAdapters
- TableAdapters, updating data
- data [Visual Studio], updating
- saving data
ms.assetid: 5e32e10e-9bac-4969-9bdd-b8f6919d3516
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 546ca45ed48f9fc247bd5706005153f41cf206e5
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55926759"
---
# <a name="update-data-by-using-a-tableadapter"></a>Aktualizace dat pomocí objektu TableAdapter

Poté, co byl upravit a ověřit data v datové sadě, můžete odeslat aktualizovaná data zpět do databáze pomocí volání `Update` metodu [TableAdapter](../data-tools/create-and-configure-tableadapters.md). `Update` Metodu aktualizace jedné tabulky datového a spustí správný příkaz (vložení, aktualizace nebo odstranění) na základě <xref:System.Data.DataRow.RowState%2A> každého řádku dat v tabulce. Když datové sady má související tabulky, Visual Studio vygeneruje třídy TableAdapterManager, které umožňují provádět aktualizace. Třída TableAdapterManager zajistí, že jsou ve správném pořadí podle omezení cizího klíče, které jsou definovány v databázi provedeny aktualizace. Při použití ovládacích prvků vázaných na data, architektura vázání dat vytvoří členské proměnné třídy TableAdapterManager volá tableAdapterManager.

> [!NOTE]
> Při pokusu aktualizovat zdroj dat s obsahem datové sady, může docházet k chybám. Aby nedocházelo k chybám, doporučujeme umístit kód, který volá adaptéru `Update` metodu `try` / `catch` bloku.

 Přesný postup pro aktualizaci zdroje dat se může lišit v závislosti na obchodní potřeby, ale zahrnuje následující kroky:

1.  Volání `Update` metoda `try` / `catch` bloku.

2.  Pokud je výjimka zachycena, vyhledejte řádek dat, která způsobila chybu.

3.  Sjednotit problém v datech řádku (prostřednictvím kódu programu, pokud je to možné, nebo tím, že předloží neplatný řádek pro uživatele pro úpravy) a akci opakujte aktualizaci (<xref:System.Data.DataRow.HasErrors%2A>, <xref:System.Data.DataTable.GetErrors%2A>).

## <a name="save-data-to-a-database"></a>Uložení dat do databáze

Volání `Update` metody třídy TableAdapter. Předejte název tabulky dat, který obsahuje hodnoty, které mají být zapsána do databáze.

### <a name="to-update-a-database-by-using-a-tableadapter"></a>Chcete-li aktualizovat databázi pomocí TableAdapter

-   Uzavřete objektu TableAdapter`Update` metoda `try` / `catch` bloku. Následující příklad ukazuje, jak aktualizovat obsah `Customers` tabulku v `NorthwindDataSet` zevnitř `try` / `catch` bloku.

     [!code-csharp[VbRaddataSaving#9](../data-tools/codesnippet/CSharp/update-data-by-using-a-tableadapter_1.cs)]
     [!code-vb[VbRaddataSaving#9](../data-tools/codesnippet/VisualBasic/update-data-by-using-a-tableadapter_1.vb)]

## <a name="see-also"></a>Viz také:

- [Ukládání dat zpět do databáze](../data-tools/save-data-back-to-the-database.md)