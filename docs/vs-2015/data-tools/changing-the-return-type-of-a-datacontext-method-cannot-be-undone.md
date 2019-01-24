---
title: Změnu návratového typu metody DataContext nejde vrátit zpět | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: 76b161fc-5075-4192-8d94-f15b02e199e9
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 9f986dae74991695c83b2e2c329493141c6518bb
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54775581"
---
# <a name="changing-the-return-type-of-a-datacontext-method-cannot-be-undone"></a>Změnu návratového typu metody DataContext nelze vrátit zpět.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Změnu návratového typu metody DataContext nelze vrátit zpět. Pokud chcete vrátit zpět k automaticky generovanému typu, musí přetáhnete položky z Průzkumník serveru/Průzkumník databáze do Návrháře relací objektů znovu. Opravdu že chcete změnit návratový typ?  
  
 Návratový typ <xref:System.Data.Linq.DataContext> metoda se liší v závislosti na tom, kde přetáhnete položku do [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]. Pokud přetáhnete položku přímo do existující entity třídy, <xref:System.Data.Linq.DataContext> metodu, která má návratový typ třídy entita se vytvoří. Pokud přetáhnete položku na prázdnou oblast [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)], <xref:System.Data.Linq.DataContext> vytvořené metodou, která vrací automaticky generovanému typu. Můžete změnit návratový typ <xref:System.Data.Linq.DataContext> metoda po přidání do podokna metody. Zkontrolovat nebo změnit návratový typ <xref:System.Data.Linq.DataContext> metoda, vyberte ho a klikněte **návratový typ** vlastnost v **vlastnosti** okna.  
  
### <a name="to-change-the-return-type-of-a-datacontext"></a>Chcete-li změnit návratový typ položkou DataContext  
  
-   Klikněte na **Ano**.  
  
### <a name="to-exit-the-message-box-and-leave-the-return-type-unchanged"></a>Chcete ukončit okně se zprávou a ponechat beze změny návratový typ  
  
-   Klikněte na tlačítko **ne**.  
  
### <a name="to-revert-to-the-original-return-type-after-changing-the-return-type"></a>Vrátit zpět na původní typ vrácené hodnoty po změnu návratového typu  
  
1.  Vyberte <xref:System.Data.Linq.DataContext> metodu [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] a odstraňte ho.  
  
2.  Vyhledejte položku v **Průzkumník serveru/Průzkumník databáze** a přetáhněte ji do [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].  
  
     A <xref:System.Data.Linq.DataContext> metodu je vytvořen s původní výchozí návratovým typem.  
  
## <a name="see-also"></a>Viz také  
 [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [Metody DataContext (O/R Designer)](../data-tools/datacontext-methods-o-r-designer.md)   
 [Postupy: Vytvoření metod DataContext namapovaných na uložené procedury a funkce (O/R Designer)](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)
