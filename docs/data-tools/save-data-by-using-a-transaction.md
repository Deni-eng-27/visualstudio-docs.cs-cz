---
title: 'Postupy: ukládání dat pomocí transakce'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- saving data, using transactions
- System.Transactions namespace
- transactions, saving data
- data [Visual Studio], saving
ms.assetid: 8b835e8f-34a3-413d-9bb5-ebaeb87f1198
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: f4c865dcf55f8796748308822b8a6dde5f96ef8e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31920544"
---
# <a name="how-to-save-data-by-using-a-transaction"></a>Postupy: ukládání dat pomocí transakce
Ukládání dat v transakci pomocí <xref:System.Transactions> oboru názvů. Použití <xref:System.Transactions.TransactionScope> objektu účast v transakci, která je pro vás automaticky spravovány.

Projekty nejsou vytvořeny s odkazem na System.Transactions – sestavení, proto musíte ručně přidejte odkaz na projekty, které používají transakce.

Nejjednodušší způsob, jak implementovat transakce je k vytváření instancí <xref:System.Transactions.TransactionScope> objekt v `using` příkaz. (Další informace najdete v tématu [příkazu Using](/dotnet/visual-basic/language-reference/statements/using-statement), a [pomocí příkazu](/dotnet/csharp/language-reference/keywords/using-statement).) Kód, který běží v rámci `using` příkaz účastní transakce.

Potvrzení transakce, volání <xref:System.Transactions.TransactionScope.Complete%2A> metoda jako poslední příkaz v pomocí blokovat.

Vrácení transakce, způsobí výjimku před voláním <xref:System.Transactions.TransactionScope.Complete%2A> metoda.

## <a name="to-add-a-reference-to-the-systemtransactionsdll"></a>Chcete-li přidat odkaz na System.Transactions.dll

1.  Na **projektu** nabídce vyberte možnost **přidat odkaz na**.

2.  Na **.NET** karta (**systému SQL Server** kartu pro projekty na SQL serveru), vyberte **System.Transactions –** a potom vyberte **OK**.

     Odkaz na System.Transactions.dll se přidá do projektu.

## <a name="to-save-data-in-a-transaction"></a>K uložení dat v transakci

-   Přidejte kód pro uložení dat v rámci pomocí příkazu, který obsahuje transakce. Následující kód ukazuje, jak vytvořit a vytvoření instancí <xref:System.Transactions.TransactionScope> objektu v pomocí příkazu:

     [!code-vb[VbRaddataSaving#11](../data-tools/codesnippet/VisualBasic/save-data-by-using-a-transaction_1.vb)]
     [!code-csharp[VbRaddataSaving#11](../data-tools/codesnippet/CSharp/save-data-by-using-a-transaction_1.cs)]

## <a name="see-also"></a>Viz také

- [Ukládání dat zpět do databáze](../data-tools/save-data-back-to-the-database.md)
- [Návod: Uložení dat do transakce](../data-tools/save-data-in-a-transaction.md)