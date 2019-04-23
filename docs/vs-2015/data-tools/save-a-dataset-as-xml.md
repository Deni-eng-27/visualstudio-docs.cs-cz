---
title: Uložení datové sady ve formátu XML | Dokumentace Microsoftu
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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 2e4331b59c532e681c7e10ab8e43b953e9f72b18
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60059692"
---
# <a name="save-a-dataset-as-xml"></a>Uložení datové sady ve formátu XML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Data XML v datové sadě je možný voláním dostupné metody XML v datové sadě. K ukládání dat ve formátu XML, lze volat buď <xref:System.Data.DataSet.GetXml%2A> metoda nebo <xref:System.Data.DataSet.WriteXml%2A> metodu <xref:System.Data.DataSet>.  
  
 Volání <xref:System.Data.DataSet.GetXml%2A> metoda vrátí řetězec, který obsahuje data ze všech tabulek dat v datové sadě, který je formátován jako XML.  
  
 Volání <xref:System.Data.DataSet.WriteXml%2A> metoda odesílá data ve formátu XML do souboru, který zadáte.  
  
### <a name="to-save-the-data-in-a-dataset-as-xml-to-a-variable"></a>Chcete-li uložit data v datové sadě ve formátu XML do proměnné  
  
- <xref:System.Data.DataSet.GetXml%2A> Metoda vrátí hodnotu <xref:System.String>. To znamená, že deklarujete proměnnou typu <xref:System.String> a přiřaďte ho výsledky <xref:System.Data.DataSet.GetXml%2A> metody.  
  
     [!code-csharp[VbRaddataSaving#12](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#12)]
     [!code-vb[VbRaddataSaving#12](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#12)]  
  
### <a name="to-save-the-data-in-a-dataset-as-xml-to-a-file"></a>Chcete-li uložit data v datové sadě ve formátu XML do souboru  
  
- <xref:System.Data.DataSet.WriteXml%2A> Metoda má několik přetížení. Následující kód ukazuje, jak uložit data do souboru. Deklarujte proměnnou a přiřaďte ho platnou cestu k uložení souboru.  
  
     [!code-csharp[VbRaddataSaving#13](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#13)]
     [!code-vb[VbRaddataSaving#13](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#13)]  
  
## <a name="see-also"></a>Viz také  
 [Ukládání dat zpět do databáze](../data-tools/save-data-back-to-the-database.md)
