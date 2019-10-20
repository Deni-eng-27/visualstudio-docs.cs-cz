---
title: 'Návod: vytvoření datové služby WCF pomocí WPF a Entity Framework | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
helpviewer_keywords:
- data services in Visual Studio
- WCF Data Services, Visual Studio
- ADO.NET Data Services, Visual Studio
- WCF data services in Visual Studio
ms.assetid: da66ad1b-a25d-485c-af13-2d18f0422e3d
caps.latest.revision: 28
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: f26d81c3ac80b889f90e2a729545f0db0e52fa1a
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72660231"
---
# <a name="walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework"></a>Návod: vytvoření datové služby WCF pomocí WPF a Entity Framework
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tento návod ukazuje, jak vytvořit jednoduchý [!INCLUDE[ss_data_service](../includes/ss-data-service-md.md)] hostovaný ve [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] webové aplikaci, a pak k němu přistupovat z aplikace model Windows Forms.

 V tomto návodu se dozvíte, jak:

- Vytvořte webovou aplikaci, která bude hostovat [!INCLUDE[ss_data_service](../includes/ss-data-service-md.md)].

- Vytvoří [!INCLUDE[adonet_edm](../includes/adonet-edm-md.md)], který představuje tabulku Customers v databázi Northwind.

- Vytvořte [!INCLUDE[ss_data_service](../includes/ss-data-service-md.md)].

- Vytvořte klientskou aplikaci a přidejte odkaz na [!INCLUDE[ss_data_service](../includes/ss-data-service-md.md)].

- Vytvořit datovou vazbu na službu a vygenerovat uživatelské rozhraní

- Volitelně přidat do aplikace možnosti filtrování

## <a name="prerequisites"></a>Požadavky
 K dokončení tohoto návodu budete potřebovat následující komponenty:

- Ukázkovou databázi Northwind

     Pokud tuto databázi ve vývojovém počítači nemáte, můžete si ji stáhnout z webu [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088). Pokyny najdete v tématu [stažení ukázkových databází](https://msdn.microsoft.com/library/ef9d69a1-9461-43fe-94bb-7c836754bcb5).

## <a name="creating-the-service"></a>Vytvoření služby
 Chcete-li vytvořit [!INCLUDE[ss_data_service](../includes/ss-data-service-md.md)], přidejte webový projekt, vytvořte [!INCLUDE[adonet_edm](../includes/adonet-edm-md.md)] a pak vytvořte službu z modelu.

 V prvním kroku přidáte webový projekt pro hostování služby.

 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]

#### <a name="to-create-the-web-project"></a>Vytvoření webového projektu

1. Na panelu nabídek vyberte položku **soubor**, **Nový**, **projekt**.

2. V dialogovém okně **Nový projekt** rozbalte **Visual Basic** nebo **Visual C#**  a **webové** uzly a pak zvolte šablonu **webové aplikace ASP.NET** .

3. Do textového pole **název** zadejte **NorthwindWeb**a poté klikněte na tlačítko **OK** .

4. V dialogovém okně **Nový projekt ASP.NET** v seznamu **Vyberte šablonu** zvolte **prázdné**a pak klikněte na tlačítko **OK** .

   V tomto kroku vytvoříte [!INCLUDE[adonet_edm](../includes/adonet-edm-md.md)], který představuje tabulku Customers v databázi Northwind.

#### <a name="to-create-the-entity-data-model"></a>Vytvoření modelu Entity Data Model

1. Na panelu nabídek vyberte možnost **projekt**, **Přidat novou položku**.

2. V dialogovém okně **Přidat novou položku** zvolte uzel **dat** a pak zvolte položku **ADO.NET model EDM (Entity Data Model)** .

3. Do textového pole **název** zadejte `NorthwindModel` a pak klikněte na tlačítko **Přidat** .

    Zobrazí se Průvodce modelem Entity Data Model.

4. V průvodci model EDM (Entity Data Model) na stránce **Výběr obsahu modelu** zvolte položku **Návrhář EF z položky databáze** a poté klikněte na tlačítko **Další** .

5. Na stránce **Vyberte datové připojení** proveďte jeden z následujících kroků:

   - Pokud je datové připojení k ukázkové databázi Northwind k dispozici v rozevíracím seznamu, vyberte je.

        -nebo-

   - Klikněte na tlačítko **nové připojení** a nakonfigurujte nové datové připojení. Další informace najdete v tématu [Přidání nových připojení](../data-tools/add-new-connections.md).

6. Pokud databáze vyžaduje heslo, vyberte možnost **Ano, zahrnout citlivá data do připojovacího řetězce** a potom klikněte na tlačítko **Další** .

   > [!NOTE]
   > Pokud se zobrazí dialogové okno, klikněte na **tlačítko Ano** a uložte soubor do projektu.

7. Na stránce **Zvolte verzi** zvolte možnost **Entity Framework 5,0** a potom klikněte na tlačítko **Další** .

   > [!NOTE]
   > Aby bylo možné používat nejnovější verzi Entity Framework 6 se službami WCF, bude nutné nainstalovat balíček NuGet poskytovatele WCF Data Services Entity Framework. Viz [použití WCF Data Services 5.6.0 s Entity Framework 6 +](http://blogs.msdn.com/b/odatateam/archive/2013/10/02/using-wcf-data-services-5-6-0-with-entity-framework-6.aspx).

8. Na stránce **Zvolte vaše databázové objekty** rozbalte uzel **tabulky** , zaškrtněte políčko **zákazníci** a pak klikněte na tlačítko **Dokončit** .

    Zobrazí se diagram modelu entit a do projektu bude přidán soubor NorthwindModel.edmx.

   V tomto kroku vytvoříte a otestujete datovou službu.

#### <a name="to-create-the-data-service"></a>Vytvoření datové služby

1. Na panelu nabídek vyberte možnost **projekt**, **Přidat novou položku**.

2. V dialogovém okně **Přidat novou položku** zvolte uzel **Web** a pak zvolte položku **WCF Data Service 5,6** .

3. Do textového pole **název** zadejte `NorthwindCustomers` a pak klikněte na tlačítko **Přidat** .

    V **editoru kódu**se zobrazí soubor NorthwindCustomers. svc.

4. V **editoru kódu**vyhledejte první `TODO:` komentář a nahraďte kód následujícím kódem:

    [!code-csharp[WCFDataServiceWalkthrough#1](../snippets/csharp/VS_Snippets_VBCSharp/wcfdataservicewalkthrough/cs/northwindcustomers.svc.cs#1)]
    [!code-vb[WCFDataServiceWalkthrough#1](../snippets/visualbasic/VS_Snippets_VBCSharp/wcfdataservicewalkthrough/vb/northwindcustomers.svc.vb#1)]

5. Nahraďte komentáře v obslužné rutině události `InitializeService` následujícím kódem:

    [!code-csharp[WCFDataServiceWalkthrough#2](../snippets/csharp/VS_Snippets_VBCSharp/wcfdataservicewalkthrough/cs/northwindcustomers.svc.cs#2)]
    [!code-vb[WCFDataServiceWalkthrough#2](../snippets/visualbasic/VS_Snippets_VBCSharp/wcfdataservicewalkthrough/vb/northwindcustomers.svc.vb#2)]

6. Na panelu nabídek vyberte možnost **ladit**, **Spustit bez ladění** a spusťte službu. Otevře se okno prohlížeče a zobrazí se schéma XML pro službu.

7. Do **adresního** řádku zadejte `Customers` na konci adresy URL pro NorthwindCustomers. svc a pak zvolte klávesu **ENTER** .

    Zobrazí se reprezentace dat z tabulky Customers v jazyce XML.

   > [!NOTE]
   > V některých případech bude aplikace Internet Explorer chybně interpretovat data jako informační kanál RSS. Zkontrolujte, zda je zakázána možnost zobrazení informačních kanálů RSS. Další informace najdete v tématu [řešení potíží s odkazy na služby](../data-tools/troubleshooting-service-references.md).

8. Zavřete okno prohlížeče.

   V dalších krocích vytvoříte klientskou aplikaci založenou na modelu Windows Forms, která bude službu používat.

## <a name="creating-the-client-application"></a>Vytvoření klientské aplikace
 Vytvoříte klientskou aplikaci tak, že přidáte druhý projekt, do projektu přidáte odkaz na službu, nakonfigurujete zdroj dat a vytvoříte uživatelské rozhraní pro zobrazení dat ze služby.

 V prvním kroku přidáte do řešení projekt modelu Windows Forms a nastavíte ho jako spouštěný projekt.

#### <a name="to-create-the-client-application"></a>Vytvoření klientské aplikace

1. Na panelu nabídek vyberte možnosti soubor, **Přidat**, **Nový projekt**.

2. V dialogovém okně **Nový projekt** rozbalte uzel **Visual Basic** nebo **Visual C#**  a zvolte uzel **Windows** a pak zvolte **model Windows Forms aplikace**.

3. Do textového pole **název** zadejte `NorthwindClient` a pak klikněte na tlačítko **OK** .

4. V **Průzkumník řešení**vyberte uzel projektu **NorthwindClient** .

5. V panelu nabídek vyberte položku **projekt**, **nastavit jako spouštěný projekt**.

   V tomto kroku přidáte odkaz na službu do [!INCLUDE[ss_data_service](../includes/ss-data-service-md.md)] ve webovém projektu.

#### <a name="to-add-a-service-reference"></a>Přidání odkazu na službu

1. Na panelu nabídek vyberte položku **projekt**, **Přidat odkaz na službu**.

2. V dialogovém okně **Přidat odkaz na službu** klikněte na tlačítko **Vyhledat** .

    Adresa URL služby NorthwindCustomers se zobrazí v poli **adresa** .

3. Kliknutím na tlačítko **OK** přidejte odkaz na službu.

   V tomto kroku nakonfigurujete zdroj dat, abyste umožnili vytváření datových vazeb na službu.

#### <a name="to-enable-data-binding-to-the-service"></a>Vytvoření datové vazby na službu

1. Na panelu nabídek vyberte možnost **zobrazení**, **ostatní okna**, **zdroje dat**.

2. V okně **zdroje dat** klikněte na tlačítko **Přidat nový zdroj dat** .

3. Na stránce **Vybrat typ zdroje dat** v **Průvodci konfigurací zdroje dat**zvolte možnost **objekt**a poté klikněte na tlačítko **Další** .

4. Na stránce **Vyberte datové objekty** rozbalte uzel **NorthwindClient** a potom rozbalte uzel **NorthwindClient. ServiceReference1** .

5. Zaškrtněte políčko **Zákazník** a pak klikněte na tlačítko **Dokončit** .

   V tomto kroku vytvoříte uživatelské rozhraní, které zobrazí data ze služby.

#### <a name="to-create-the-user-interface"></a>Vytvoření uživatelského rozhraní

1. V okně **zdroje dat** otevřete místní nabídku uzlu **Customers** a vyberte možnost **Kopírovat**.

2. V návrháři formuláře **Form1. vb** nebo **Form1.cs** otevřete místní nabídku a vyberte možnost **Vložit**.

    Do formuláře se přidají <xref:System.Windows.Forms.DataGridView> ovládací prvek, součást <xref:System.Windows.Forms.BindingSource> a <xref:System.Windows.Forms.BindingNavigator> komponenta.

3. Zvolte ovládací prvek **customersDataGridView** a potom v okně **vlastnosti** nastavte vlastnost **Dock** na **Fill**.

4. V **Průzkumník řešení**otevřete místní nabídku pro uzel **Form1** a pomocí možnosti **Zobrazit kód** otevřete Editor kódu a do horní části souboru přidejte následující příkazy import nebo using:

   ```vb
   Imports NorthwindClient.ServiceReference1
   ```

   ```csharp
   using NorthwindClient.ServiceReference1;
   ```

5. Do obslužné rutiny události `Form1_Load` přidejte následující kód:

   ```vb
   Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
           Dim proxy As New NorthwindEntities _
   (New Uri("http://localhost:53161/NorthwindCustomers.svc/"))
           Me.CustomersBindingSource.DataSource = proxy.Customers
       End Sub
   ```

   ```csharp
   private void Form1_Load(object sender, EventArgs e)
   {
   NorthwindEntities proxy = new NorthwindEntities(new Uri("http://localhost:53161/NorthwindCustomers.svc/"));
   this.CustomersBindingSource.DataSource = proxy.Customers;
   }

   ```

6. V **Průzkumník řešení**otevřete místní nabídku pro soubor NorthwindCustomers. svc a v prohlížeči vyberte možnost **Zobrazit**. Spustí se aplikace Internet Explorer a zobrazí se schéma XML pro službu.

7. Zkopírujte adresu URL z panelu Adresa aplikace Internet Explorer.

8. V kódu, který jste přidali v kroku 4, vyberte `http://localhost:53161/NorthwindCustomers.svc/` a nahraďte ji adresou URL, kterou jste právě zkopírovali.

9. Na panelu nabídek vyberte možnost **ladit**, **Spustit ladění** a spusťte aplikaci. Zobrazí se informace o zákazníkovi.

   Nyní máte funkční aplikaci, která zobrazuje seznam zákazníků ze služby NorthwindCustomers. Pokud chcete prostřednictvím služby vystavit další data, můžete [!INCLUDE[adonet_edm](../includes/adonet-edm-md.md)] upravit tak, aby zahrnovala další tabulky z databáze Northwind.

   V dalším volitelném kroku se dozvíte, jak filtrovat data, která služba vrací.

## <a name="adding-filtering-capabilities"></a>Přidání možností filtrování
 V tomto kroku přizpůsobíte aplikaci tak, aby umožňovala filtrování dat podle města zákazníka.

#### <a name="to-add-filtering-by-city"></a>Přidání filtrování podle města

1. V **Průzkumník řešení**otevřete místní nabídku uzlu **Form1. vb** nebo **Form1.cs** a klikněte na tlačítko **otevřít**.

2. Přidejte ovládací prvek <xref:System.Windows.Forms.TextBox> a ovládací prvek <xref:System.Windows.Forms.Button> z **panelu nástrojů** do formuláře.

3. Otevřete místní nabídku ovládacího prvku <xref:System.Windows.Forms.Button> a zvolte možnost **Zobrazit kód**a přidejte následující kód do obslužné rutiny události `Button1_Click`:

    ```vb
    Private Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click
            Dim proxy As New northwindEntities _
    (New Uri("http://localhost:53161/NorthwindCustomers.svc"))
            Dim city As String = TextBox1.Text

            If city <> "" Then
                Me.CustomersBindingSource.DataSource = From c In _
             proxy.Customers Where c.City = city
            End If

        End Sub
    ```

    ```csharp
    private void Button1_Click(object sender, EventArgs e)
    {
    ServiceReference1.northwindModel.northwindEntities proxy = new northwindEntities(new Uri("http://localhost:53161/NorthwindCustomers.svc"));
    string city = TextBox1.Text;

    if (!string.IsNullOrEmpty(city)) {
    this.CustomersBindingSource.DataSource = from c in proxy.Customers where c.City == city;
    }

    }
    ```

4. V předchozím kódu nahraďte `http://localhost:53161/NorthwindCustomers.svc` adresou URL z obslužné rutiny události `Form1_Load`.

5. Na panelu nabídek vyberte možnost **ladit**, **Spustit ladění** a spusťte aplikaci.

6. Do textového pole zadejte **London**a pak klikněte na tlačítko. Zobrazí se pouze zákazníci z Londýna.

## <a name="see-also"></a>Viz také
 [Windows Communication Foundation služby a WCF Data Services v aplikaci Visual Studio](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md) [Postupy: Přidání, aktualizace nebo odebrání odkazu na službu WCF Data Service](../data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference.md)
