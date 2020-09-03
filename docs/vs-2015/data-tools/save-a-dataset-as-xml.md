---
title: Uložení datové sady jako XML | Microsoft Docs
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
- XML [Visual Basic], datasets
- data [Visual Studio], saving as XML
- datasets [Visual Basic], saving as XML
- saving data
ms.assetid: 68b8327c-ae05-49ff-b9ba-99183e70b52c
caps.latest.revision: 14
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e64c3c17934e5cdc5d6ca1f510c7164b86a77c1a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "72652853"
---
# <a name="save-a-dataset-as-xml"></a>Uložení datové sady ve formátu XML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Data XML v datové sadě jsou přístupná voláním dostupných metod jazyka XML na datové sadě. Chcete-li uložit data ve formátu XML, můžete zavolat buď <xref:System.Data.DataSet.GetXml%2A> metodu, nebo <xref:System.Data.DataSet.WriteXml%2A> metodu <xref:System.Data.DataSet> .

 Volání <xref:System.Data.DataSet.GetXml%2A> metody vrátí řetězec, který obsahuje data ze všech tabulek dat v datové sadě, která je formátována jako XML.

 Volání <xref:System.Data.DataSet.WriteXml%2A> metody odesílá data ve formátu XML do souboru, který zadáte.

### <a name="to-save-the-data-in-a-dataset-as-xml-to-a-variable"></a>Uložení dat v datové sadě jako XML do proměnné

- <xref:System.Data.DataSet.GetXml%2A>Metoda vrátí <xref:System.String> . To znamená, že deklarujete proměnnou typu <xref:System.String> a přiřadíte jí výsledky <xref:System.Data.DataSet.GetXml%2A> metody.

     [!code-csharp[VbRaddataSaving#12](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#12)]
     [!code-vb[VbRaddataSaving#12](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#12)]

### <a name="to-save-the-data-in-a-dataset-as-xml-to-a-file"></a>Uložení dat v datové sadě jako XML do souboru

- <xref:System.Data.DataSet.WriteXml%2A>Metoda má několik přetížení. Následující kód ukazuje, jak uložit data do souboru. Deklarujte proměnnou a přiřaďte jí platnou cestu k uložení souboru do.

     [!code-csharp[VbRaddataSaving#13](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#13)]
     [!code-vb[VbRaddataSaving#13](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#13)]

## <a name="see-also"></a>Viz také
 [Ukládání dat zpět do databáze](../data-tools/save-data-back-to-the-database.md)
