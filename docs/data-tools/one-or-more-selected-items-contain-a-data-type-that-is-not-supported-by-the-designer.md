---
title: Minimálně jedna vybraná položka obsahuje datový typ, který návrhář nepodporuje.
ms.date: 11/04/2016
ms.topic: error-reference
ms.assetid: 71dcd4f9-2946-42c5-9ce4-99c819ea2785
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: d2f066bb7501085b66ba724f94840314063cd2ca
ms.sourcegitcommit: 1d4f6cc80ea343a667d16beec03220cfe1f43b8e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85281887"
---
# <a name="one-or-more-selected-items-contain-a-data-type-that-is-not-supported-by-the-designer"></a>Minimálně jedna vybraná položka obsahuje datový typ, který návrhář nepodporuje.

Jedna nebo více položek přetažených z **Průzkumník serveru** nebo **Průzkumníka databáze** do **návrháře o/r** obsahuje datový typ, který není podporován **návrhářem o/r**, například [uživatelsky definované typy CLR](/dotnet/framework/data/adonet/sql/clr-user-defined-types).

## <a name="to-correct-this-error"></a>Oprava této chyby

1. Vytvořte zobrazení založené na požadované tabulce a nezahrnuje datový typ, který není podporován.

2. Přetáhněte zobrazení z **Průzkumník serveru** nebo **Průzkumníka databáze** do návrháře.

## <a name="see-also"></a>Viz také

- [Nástroje LINQ to SQL v aplikaci Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
