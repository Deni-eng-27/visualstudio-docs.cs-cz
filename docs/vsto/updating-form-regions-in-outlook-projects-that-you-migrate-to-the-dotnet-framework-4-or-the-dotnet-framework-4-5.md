---
title: "Aktualizace oblastí formulářů v projektech Outlook při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords: Office projects [Office development in Visual Studio], migrating to .NET Framework 4
ms.assetid: 65991e2f-4875-49f0-b21b-6a3d0175d0f4
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 57bb9bf6ddf20574b06b336b5620adb86c3070c7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="updating-form-regions-in-outlook-projects-that-you-migrate-to-the-net-framework-4-or-the-net-framework-45"></a>Aktualizace oblastí formulářů v projektech Outlook při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5
  Pokud cílový framework projektu doplňku VSTO pro Outlook s oblasti formuláře se změní na [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, musíte provést některé změny kód oblasti generovaném formuláři a kód, který vytvoří instanci určité třídy oblasti formuláře za běhu.  
  
## <a name="updating-the-generated-form-region-code"></a>Aktualizace kód oblasti generovaném formuláři  
 Pokud cílový framework projektu se změní na [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, musíte změnit kód oblasti generovaném formuláři. Provedené změny se u oblasti formuláře navržené v sadě Visual Studio a formulář oblasti, které jste importovali z aplikace Outlook. Další informace o rozdílech mezi tyto typy oblasti formuláře najdete v tématu [vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md).  
  
#### <a name="to-update-the-generated-code-for-a-form-region-that-you-designed-in-visual-studio"></a>Chcete-li aktualizovat generovaný kód pro oblasti formuláře, který je navržený tak, že v sadě Visual Studio  
  
1.  Otevřete soubor modelu code-behind oblasti formuláře v editoru kódu. Název tohoto souboru je *YourFormRegion*. Designer.cs nebo *YourFormRegion*. Designer.vb. Pokud chcete zobrazit tento soubor v projektech Visual Basic, klikněte **zobrazit všechny soubory** tlačítko v **Průzkumníku řešení**.  
  
2.  Upravit deklaraci třídy oblasti formuláře tak, aby je odvozena z <xref:Microsoft.Office.Tools.Outlook.FormRegionBase> místo Microsoft.Office.Tools.Outlook.FormRegionControl.  
  
3.  Upravte konstruktoru třídy oblasti formuláře, jak je znázorněno v následující příklady kódu.  
  
     Následující příklad kódu ukazuje konstruktoru třídy oblasti formuláře v projektu s cílem rozhraní .NET Framework 3.5.  
  
    ```vb  
    Public Sub New(ByVal formRegion As Microsoft.Office.Interop.Outlook.FormRegion)  
        MyBase.New(formRegion)  
        Me.InitializeComponent()  
    End Sub  
    ```  
  
    ```csharp  
    public FormRegion1(Microsoft.Office.Interop.Outlook.FormRegion formRegion)  
        : base(formRegion)  
    {  
        this.InitializeComponent();  
    }  
    ```  
  
     Následující příklad kódu ukazuje konstruktoru třídy oblasti formuláře v projektu s cílem [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)].  
  
    ```vb  
    Public Sub New(ByVal formRegion As Microsoft.Office.Interop.Outlook.FormRegion)  
        MyBase.New(Globals.Factory, formRegion)  
        Me.InitializeComponent()  
    End Sub  
    ```  
  
    ```csharp  
    public FormRegion1(Microsoft.Office.Interop.Outlook.FormRegion formRegion)  
        : base(Globals.Factory, formRegion)  
    {  
        this.InitializeComponent();  
    }  
    ```  
  
4.  Upravte podpis metody `InitializeManifest` metoda, jak je uvedeno níže. Zajistěte, aby neupravujte kód v metodě; Tento kód představuje nastavení oblasti formuláře, které jste provedli v návrháři. V jazyce Visual C# projekty, je třeba rozbalit oblasti, který je pojmenován `Form Region Designer generated code` zobrazíte tuto metodu.  
  
     Následující příklad kódu ukazuje podpis `InitializeManifest` metoda v projektu, jehož cílem rozhraní .NET Framework 3.5.  
  
    ```vb  
    Private Shared Sub InitializeManifest(ByVal manifest As Microsoft.Office.Tools.Outlook.FormRegionManifest)  
  
        ' Do not change code in this method.  
    End Sub  
    ```  
  
    ```csharp  
    private static void InitializeManifest(Microsoft.Office.Tools.Outlook.FormRegionManifest manifest)  
    {  
        // Do not change code in this method.  
    }  
    ```  
  
     Následující příklad kódu ukazuje podpis `InitializeManifest` metoda v projektu, jehož cílem [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)].  
  
    ```vb  
    Private Shared Sub InitializeManifest(ByVal manifest As Microsoft.Office.Tools.Outlook.FormRegionManifest,   
        ByVal factory As Microsoft.Office.Tools.Outlook.Factory)  
  
        ' Do not change code in this method.  
    End Sub  
    ```  
  
    ```csharp  
    private static void InitializeManifest(Microsoft.Office.Tools.Outlook.FormRegionManifest manifest,   
        Microsoft.Office.Tools.Outlook.Factory factory)  
    {  
        // Do not change code in this method.  
    }  
    ```  
  
5.  Přidáte novou položku aplikace Outlook oblasti formuláře do projektu. Otevření souboru kódu na pozadí pro nové oblasti formuláře, vyhledejte *YourNewFormRegion* `Factory` a `WindowFormRegionCollection` třídy v souboru a tyto třídy zkopírujte do schránky.  
  
6.  Odstraňte nové oblasti formuláře, které jste přidali do projektu.  
  
7.  V souboru kódu na pozadí formuláře oblast, která jsou aktualizace pro práci v přesměrovanou projektu, vyhledejte *YourOriginalFormRegion* `Factory` a `WindowFormRegionCollection` třídy a nahraďte kód, který jste zkopírovali z nové oblasti formuláře.  
  
8.  V *YourNewFormRegion* `Factory` a `WindowFormRegionCollection` třídy, vyhledejte všechny odkazy na *YourNewFormRegion* třídy a změňte každý odkaz na  *YourOriginalFormRegion* třídy místo. Například je s názvem oblasti formuláře při aktualizaci `SalesDataFormRegion` a názvem nové oblasti formuláře jste vytvořili v kroku 5 `FormRegion1`, změňte všechny odkazy z `FormRegion1` k `SalesDataFormRegion`.  
  
#### <a name="to-update-the-generated-code-for-a-form-region-that-you-imported-from-outlook"></a>Chcete-li aktualizovat generovaný kód pro oblasti formuláře, který jste importovali z Outlooku  
  
1.  Otevřete soubor modelu code-behind oblasti formuláře v editoru kódu. Název tohoto souboru je *YourFormRegion*. Designer.cs nebo *YourFormRegion*. Designer.vb. Pokud chcete zobrazit tento soubor v projektech Visual Basic, klikněte **zobrazit všechny soubory** tlačítko v **Průzkumníku řešení**.  
  
2.  Upravit deklaraci třídy oblasti formuláře tak, aby je odvozena z <xref:Microsoft.Office.Tools.Outlook.ImportedFormRegionBase> místo Microsoft.Office.Tools.Outlook.ImportedFormRegion.  
  
3.  Upravte konstruktoru třídy oblasti formuláře, jak je znázorněno v následující příklady kódu.  
  
     Následující příklad kódu ukazuje konstruktoru třídy oblasti formuláře v projektu s cílem rozhraní .NET Framework 3.5.  
  
    ```vb  
    Public Sub New(ByVal formRegion As Microsoft.Office.Interop.Outlook.FormRegion)  
        MyBase.New(formRegion)  
    End Sub  
    ```  
  
    ```csharp  
    public ImportedFormRegion1(Microsoft.Office.Interop.Outlook.FormRegion formRegion)  
        : base(formRegion)  
    {  
        this.FormRegionShowing += new System.EventHandler(this.TaskFormRegion_FormRegionShowing);  
        this.FormRegionClosed += new System.EventHandler(this.TaskFormRegion_FormRegionClosed);  
    }  
    ```  
  
     Následující příklad kódu ukazuje podpis konstruktoru třídy oblasti formuláře v projektu s cílem [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)].  
  
    ```vb  
    Public Sub New(ByVal formRegion As Microsoft.Office.Interop.Outlook.FormRegion)  
        MyBase.New(Globals.Factory, formRegion)  
    End Sub  
    ```  
  
    ```csharp  
    public ImportedFormRegion1(Microsoft.Office.Interop.Outlook.FormRegion formRegion)  
        : base(Globals.Factory, formRegion)  
    {  
        this.FormRegionShowing += new System.EventHandler(this.TaskFormRegion_FormRegionShowing);  
        this.FormRegionClosed += new System.EventHandler(this.TaskFormRegion_FormRegionClosed);  
    }  
    ```  
  
4.  Pro každý řádek kódu `InitializeControls` metoda, která inicializuje ovládacího prvku ve třídě oblasti formuláře upravit kód, jak je uvedeno níže.  
  
     Následující příklad kódu ukazuje, jak se inicializovat ovládací prvek v projektu s cílem rozhraní .NET Framework 3.5. V tomto kódu má metodu GetFormRegionControl parametr typu, který určuje typ ovládacího prvku, který je vrácen.  
  
    ```vb  
    Me.olkTextBox1 = Me.GetFormRegionControl(Of Microsoft.Office.Interop.Outlook.OlkTextBox)("OlkTextBox1")  
    ```  
  
    ```csharp  
    this.olkTextBox1 = this.GetFormRegionControl<Microsoft.Office.Interop.Outlook.OlkTextBox>("OlkTextBox1");  
    ```  
  
     Následující příklad kódu ukazuje, jak se inicializovat ovládací prvek v projektu s cílem [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]. V tomto kódu <xref:Microsoft.Office.Tools.Outlook.ImportedFormRegionBase.GetFormRegionControl%2A> metoda nemá parametr typu. Musíte vysílat návratovou hodnotu pro typ ovládacího prvku, který se inicializace.  
  
    ```vb  
    Me.olkTextBox1 = CType(GetFormRegionControl("OlkTextBox1"), Microsoft.Office.Interop.Outlook.OlkTextBox)  
    ```  
  
    ```csharp  
    this.olkTextBox1 = (Microsoft.Office.Interop.Outlook.OlkTextBox)GetFormRegionControl("OlkTextBox1");  
    ```  
  
5.  Přidáte novou položku aplikace Outlook oblasti formuláře do projektu. Otevření souboru kódu na pozadí pro nové oblasti formuláře, vyhledejte *YourNewFormRegion* `Factory` a `WindowFormRegionCollection` třídy v souboru a tyto třídy zkopírujte do schránky.  
  
6.  Odstraňte nové oblasti formuláře, které jste přidali do projektu.  
  
7.  V souboru kódu na pozadí formuláře oblast, která jsou aktualizace pro práci v přesměrovanou projektu, vyhledejte *YourOriginalFormRegion* `Factory` a `WindowFormRegionCollection` třídy a nahraďte kód, který jste zkopírovali z nové oblasti formuláře.  
  
8.  V *YourNewFormRegion* `Factory` a `WindowFormRegionCollection` třídy, vyhledejte všechny odkazy na *YourNewFormRegion* třídy a změňte každý odkaz na  *YourOriginalFormRegion* třídy místo. Například je s názvem oblasti formuláře při aktualizaci `SalesDataFormRegion` a názvem nové oblasti formuláře jste vytvořili v kroku 5 `FormRegion1`, změňte všechny odkazy z `FormRegion1` k `SalesDataFormRegion`.  
  
## <a name="instantiating-form-region-classes"></a>Vytváření instancí třídy oblasti formuláře  
 Je třeba upravit kód, který dynamicky vytvoří instanci určité třídy oblasti formuláře. V projektech cílených pro rozhraní .NET Framework 3.5 můžete vytvořit instanci třídy oblasti formuláře, jako je Microsoft.Office.Tools.Outlook.FormRegionManifest přímo. V projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, jsou tyto třídy rozhraní, které nelze vytvořit instanci přímo.  
  
 Pokud je na změnit cílový framework projektu [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, musíte vytvořit instanci rozhraní pomocí metod, které jsou k dispozici Globals.Factory vlastností. Další informace o vlastnosti Globals.Factory najdete v tématu [globální přístup k objektům v projektech Office](../vsto/global-access-to-objects-in-office-projects.md).  
  
 Následující tabulka uvádí typy oblasti formuláře a metoda sloužící k vytvoření instance typy v projektů cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější.  
  
|Typ|Metoda Factory, která použít|  
|----------|---------------------------|  
|<xref:Microsoft.Office.Tools.Outlook.FormRegionCustomAction>|<xref:Microsoft.Office.Tools.Outlook.Factory.CreateFormRegionCustomAction%2A>|  
|<xref:Microsoft.Office.Tools.Outlook.FormRegionInitializingEventArgs>|<xref:Microsoft.Office.Tools.Outlook.Factory.CreateFormRegionInitializingEventArgs%2A>|  
|<xref:Microsoft.Office.Tools.Outlook.FormRegionManifest>|<xref:Microsoft.Office.Tools.Outlook.Factory.CreateFormRegionManifest%2A>|  
  
## <a name="see-also"></a>Viz také  
 [Migrace řešení Office na rozhraní .NET Framework 4 nebo novější](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md)   
 [Vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md)  
  