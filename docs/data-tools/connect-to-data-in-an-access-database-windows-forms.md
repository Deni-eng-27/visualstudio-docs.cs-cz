---
title: "Připojte se k datům v databázi aplikace Access (Windows Forms) | Microsoft Docs"
ms.custom: 
ms.date: 09/15/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- databases, connecting to
- databases, Access
- data [Visual Studio], connecting
- connecting to data, from Access databases
- Access databases, connecting
ms.assetid: 4159e815-d430-4ad0-a234-e4125fcbef18
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 1f67a87f4a704d3f76ccddba62112983c058a9f3
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="connect-to-data-in-an-access-database-windows-forms"></a>Připojte se k datům v databázi aplikace Access (Windows Forms)
Pomocí sady Visual Studio se můžete připojit k databázi aplikace Access (soubor MDF nebo soubor ACCDB). Po definování připojení, data se zobrazí v **zdroje dat** okno. Odtud můžete přetáhnout tabulky nebo zobrazení do formulářů.   
  
## <a name="prerequisites"></a>Požadavky  
 Pokud chcete použít tyto postupy, musíte projekt aplikace Windows Forms a databázi (soubor ACCDB) nebo databázi Access 2000-2003 (soubor .mdb). Postupujte podle kroků odpovídajících vašemu typu souboru.  
  
## <a name="creating-the-dataset-for-an-accdb-file"></a>Vytvoření sady dat pro soubor ACCDB  
 Pro databáze vytvořené prostřednictvím přístupu 2013, Office 365, přístup 2010 nebo Access 2007 pomocí následujícího postupu můžete připojit.  
  
#### <a name="to-create-the-dataset"></a>Vytvoření datové sady  
  
1.  Otevřete aplikaci Windows Forms, ke kterému se chcete připojit data.  
  
2.  Na **zobrazení** nabídce vyberte možnost **ostatní okna** > **zdroje dat**.  
  
     ![Zobrazit další zdroje dat Windows](../data-tools/media/viewdatasources.png "ViewDataSources")  
  
3.  V **zdroje dat** okně klikněte na tlačítko **přidat nový zdroj dat**.  

     **Průvodce konfigurací zdroje dat** otevře.  
  
4.  Vyberte **databáze** na **zvolte typ zdroje dat** a pak vyberte **Další**.  
  
5.  Vyberte **datovou sadu** na **vyberte Model databáze** a pak vyberte **Další**.  
  
6.  Na **zvolit datové připojení** vyberte **nové připojení** konfigurace nové datové připojení.  

     **Přidat připojení** otevře se dialogové okno.  
  
7.  Vyberte **změnu** vedle položky **zdroj dat** textové pole.

     **Zdroj dat změny** otevře se dialogové okno.  
  
8.  V seznamu zdrojů dat, vyberte  **\<jiných\>**. V **zprostředkovatele dat** rozevíracího seznamu, vyberte **zprostředkovatel dat .NET Framework pro OLE DB**, zvolte **OK**.  

9. Zpět v **přidat připojení** dialogové okno, vyberte **Microsoft Office 12.0 zprostředkovatel Access Database Engine OLE DB** z **zprostředkovatele OLE DB** rozevíracího seznamu.  
  
     ![OLE DB zprostředkovatel Microsoft Office 12.0 Access](../data-tools/media/dataoledbprovideroffice12access.png "dataOLEDBProviderOffice12Access")  

     > [!NOTE]
     >  Pokud nevidíte **Microsoft Office 12.0 zprostředkovatel Access Database Engine OLE DB** ve zprostředkovateli OLE DB rozevíracího seznamu, budete muset nainstalovat [ovladač systému Office 2007: součásti pro připojení dat](https://www.microsoft.com/download/confirmation.aspx?id=23734).
  
9. V **serveru nebo název souboru** textového pole zadejte cestu a soubor název ACCDB soubor, který chcete připojit k a pak vyberte **OK**. (Pokud se soubor databáze má uživatelské jméno a heslo, zadejte, je před výběrem **OK**.)    
  
10. Vyberte **Další** na **zvolit datové připojení** stránky.  

     Může se zobrazit dialogové okno informující o datového souboru není v aktuálním projektu. Vyberte **Ano** nebo **ne**.
  
11. Vyberte **Další** na **uložit připojovací řetězec do konfiguračního souboru aplikace** stránky.  
  
12. Rozbalte **tabulky** uzlu **zvolte databázové objekty** stránky.  
  
13. Vyberte libovolnou tabulky a zobrazení v datovou sadu a pak vyberte **Dokončit**.  
  
     Datová sada se přidá do projektu a tabulky a zobrazení se zobrazí v **zdroje dat** okno.  
  
## <a name="creating-the-dataset-for-an-mdb-file"></a>Vytvoření sady dat pro soubor .mdb  
 Vytvořit datová sada spuštěním **Průvodce konfigurací zdroje dat**.  
  
#### <a name="to-create-the-dataset"></a>Vytvoření datové sady  
  
1.  Otevřete aplikaci Windows Forms, ke kterému se chcete připojit data.  
  
2.  Na **zobrazení** nabídce vyberte možnost **ostatní okna** > **zdroje dat**.  
  
     ![Zobrazit další zdroje dat Windows](../data-tools/media/viewdatasources.png "ViewDataSources")  
  
3.  V **zdroje dat** okně klikněte na tlačítko **přidat nový zdroj dat**.  

     **Průvodce konfigurací zdroje dat** otevře.
  
4.  Vyberte **databáze** na **zvolte typ zdroje dat** a pak vyberte **Další**.  
  
5.  Vyberte **datovou sadu** na **vyberte Model databáze** a pak vyberte **Další**.  
  
6.  Na **zvolit datové připojení** vyberte **nové připojení** konfigurace nové datové připojení.  
  
7.  Pokud zdroj dat není **soubor databáze aplikace Microsoft Access (OLE DB)**, vyberte **změnu** otevřete **zdroj dat změny** dialogové okno a vybrat **Microsoft Přístup k souboru databáze**a potom vyberte **OK**.  
  
8.  V **název souboru databáze**, zadejte cestu a název souboru .mdb, kterou chcete připojit k a pak vyberte **OK**.  
  
     ![Přidat připojení souboru databáze aplikace Access](../data-tools/media/dataaddconnectionaccessmdb.png "dataAddConnectionAccessMDB")  
  
9. Vyberte **Další** na **zvolit datové připojení** stránky.  
  
10. Vyberte **Další** na **uložit připojovací řetězec do konfiguračního souboru aplikace** stránky.  
  
11. Rozbalte **tabulky** uzlu **zvolte databázové objekty** stránky.  
  
12. Vyberte libovolnou tabulky a zobrazení v datovou sadu a pak vyberte **Dokončit**.  
  
     Datová sada se přidá do projektu a tabulky a zobrazení se zobrazí v **zdroje dat** okno.  
  
## <a name="security"></a>Zabezpečení  
 Ukládání citlivých informací (například hesla) může ovlivnit zabezpečení aplikace. Bezpečnější způsob, jak řídit přístup k databázi, je ověřování systému Windows (označované také jako integrované zabezpečení). Další informace najdete v tématu [chrání informace o připojení](/dotnet/framework/data/adonet/protecting-connection-information).  
  
## <a name="next-steps"></a>Další kroky  
 Datová sada, kterou jste právě vytvořili, je teď dostupná v **zdroje dat** okno. Teď můžete provádět některé z následujících úloh:  
  
-   Vyberte položky v **zdroje dat** okna a přetáhněte je do svého formuláře (najdete v části [vazby Windows Forms – ovládací prvky k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)).  
  
-   Otevřít zdroj dat v **návrháře Dataset** můžete přidat nebo upravit objekty, které tvoří datovou sadu.  
  
-   Přidejte logiku ověření pro <xref:System.Data.DataTable.ColumnChanging> nebo <xref:System.Data.DataTable.RowChanging> událostí tabulek dat v datové sadě (viz [ověření dat v datových sadách](../data-tools/validate-data-in-datasets.md)).  
  
## <a name="see-also"></a>Viz také
[Přidání připojení](../data-tools/add-new-connections.md)
