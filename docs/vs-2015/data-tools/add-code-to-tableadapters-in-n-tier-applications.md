---
title: Přidejte kód do prvků TableAdapters ve víceúrovňových aplikacích | Dokumentace Microsoftu
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
- TableAdapters, n-tier applications
- n-tier applications, extending TableAdapters
ms.assetid: dafac00e-df9d-4d4a-95a6-e34b4d099425
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 3c3ddcb99163fe3548f020094647566c1779f5d9
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63444503"
---
# <a name="add-code-to-tableadapters-in-n-tier-applications"></a>Přidávání kódu do objektů TableAdapter ve vícevrstvých aplikacích
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete rozšířit funkce `TableAdapter` tak, že vytvoříte soubor částečné třídy pro `TableAdapter` a přidávání kódu do ní (místo přidání kódu *DatasetName*. Soubor DataSet.Designer). Částečné třídy povolit kód pro konkrétní třídu rozdělit mezi několik fyzických souborů. Další informace najdete v tématu [částečné](http://msdn.microsoft.com/library/7adaef80-f435-46e1-970a-269fff63b448) nebo [partial (typ)](http://msdn.microsoft.com/library/27320743-a22e-4c7b-b0b3-53afe3607334).  
  
 Kód, který definuje `TableAdapter` je generována pokaždé, když jsou změny provedené `TableAdapter`. Tento kód se také vygeneruje, když dojde ke změně za běhu všechny průvodce, který změní konfiguraci `TableAdapter`. Aby se zabránilo odstranit během opětovné vygenerování kódu `TableAdapter`, přidejte kód do souboru částečné třídy `TableAdapter`.  
  
 Ve výchozím nastavení po oddělíte datové sady a `TableAdapter` kód, výsledek je soubor samostatné třídy v každém projektu. Původní projekt obsahuje soubor s názvem *DatasetName*. Designer.vb (nebo *DatasetName*. Designer.cs), který obsahuje `TableAdapter` kódu. Projekt, který je zadaný ve **projektu Dataset** vlastnost má soubor s názvem *DatasetName*. DataSet.Designer.vb (nebo *DatasetName*. DataSet.Designer.cs), která obsahuje kód datové sady.  
  
> [!NOTE]
> Když oddělíte datové sady a `TableAdapter`s (nastavením **projektu DataSet** vlastnost), existující částečné třídy v projektu nebudou automaticky přesunuty. Existující částečné třídy datové sady je nutné ručně přesunout do projektu datové sady.  
  
> [!NOTE]
> Návrhář DataSet poskytuje funkce pro generování <xref:System.Data.DataTable.ColumnChanging> a <xref:System.Data.DataTable.RowChanging> obslužných rutin událostí v případě potřeby ověřování. Další informace najdete v tématu [přidání ověřování do vícevrstvé datové sady](../data-tools/add-validation-to-an-n-tier-dataset.md).  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
### <a name="to-add-user-code-to-a-tableadapter-in-an-n-tier-application"></a>Chcete-li přidat uživatelský kód do objektu TableAdapter v n vrstvou aplikaci  
  
1. Najděte projekt, který obsahuje soubor XSD (datová sada).  
  
2. Dvakrát klikněte **XSD** soubor otevřete datovou sadu.  
  
3. Klikněte pravým tlačítkem myši `TableAdapter` , který chcete přidat kód a pak vyberte**zobrazit kód**.  
  
     Částečné třídy se vytvoří a otevře v editoru kódu.  
  
4. Přidejte kód do částečné deklarace třídy.  
  
5. Následující příklad ukazuje, kde přidat kód pro `CustomersTableAdapter` v `NorthwindDataSet`:  
  
    ```vb  
    Partial Public Class CustomersTableAdapter  
        ' Add code here to add functionality   
        ' to the CustomersTableAdapter.  
    End Class  
    ```  
  
    ```csharp  
    public partial class CustomersTableAdapter  
    {  
        // Add code here to add functionality  
        // to the CustomersTableAdapter.  
    }  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Přehled vícevrstvých datových aplikací](../data-tools/n-tier-data-applications-overview.md)   
 [Přidání kódu do datových sad v n vrstvé aplikace](../data-tools/add-code-to-datasets-in-n-tier-applications.md)   
 [Objekty TableAdapter](http://msdn.microsoft.com/library/09416de9-134c-4dc7-8262-6c8d81e3f364)   
 [TableAdapterManager – přehled](http://msdn.microsoft.com/library/33076d42-6b41-491a-ac11-6c6339aea650)   
 [Přehled hierarchické aktualizace](http://msdn.microsoft.com/library/c4f8e8b9-e4a5-4a02-8462-d03d1e8222d6)