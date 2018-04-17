---
title: 'Návod: Můj první grafický subsystém WPF Desktopová aplikace | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- csharp
- vb
ms.workload:
- multiple
ms.openlocfilehash: 26ab7672095c518c0204491472695e1e04a2dcdb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a>Návod: Můj první grafický subsystém WPF aplikace pracovní plochy

Tento názorný postup obsahuje úvod k vývoji Windows Presentation Foundation (WPF). Vytvoříte základní aplikaci, která obsahuje prvky, které jsou společné pro většinu aplikací klasické pracovní plochy WPF: XAML značek, kódu, definice aplikace, ovládací prvky, rozložení, datové vazby a styly.

## <a name="creating-the-application-project"></a>Vytvoření projektu aplikace

V této části vytvoříte infrastrukturu aplikace, která zahrnuje projektu a hlavní okno nebo formuláře.

### <a name="to-create-the-project"></a>Vytvoření projektu

1. Na řádku nabídek zvolte **soubor** > **nový** > **projektu**.

1. V **nový projekt** dialogové okno, rozbalte **Visual C#** nebo **jazyka Visual Basic** uzlu a zvolte **Windows** uzel a potom rozbalte **Windows** uzel a zvolte **klasický desktopový** uzlu.

1. V seznamu šablony, vyberte **aplikaci WPF** šablony.

1. V **název** textového pole zadejte `ExpenseIt`a potom zvolte **OK** tlačítko.

    Vytvoření projektu a soubory projektu budou přidány do **Průzkumníku řešení**a návrháři intervalu pro správu a výchozí aplikace s názvem **MainWindow.xaml** se zobrazí.

### <a name="to-modify-the-main-window"></a>Chcete-li změnit hlavní okno

1. V návrháři, vyberte **MainWindow.xaml** kartě, pokud již není aktivní návrháře karty.

1. Pokud používáte C#, vyhledejte řádek `<Window x:Class="ExpenseIt.MainWindow"` a nahraďte ho `<NavigationWindow x:Class="ExpenseIt.MainWindow"`.

     Pokud používáte Visual Basic, vyhledejte řádek `<Window x:Class=" MainWindow"` a nahraďte ho `<NavigationWindow x:Class="MainWindow"`.

     Všimněte si, že při změně `<Window` značky k `<NavigationWindow`, IntelliSense automaticky změní na uzavírací značku a tím `</NavigationWindow>` také.

    > [!NOTE]
    >  Po změně značky, pokud **seznam chyb** je otevřené okno může dojít k několika chybám. Nemusíte si dělat starosti, budou změny provedené v příštích několika krocích tyto přejděte rychle.

1. Vyberte `<Grid>` a `</Grid>` značky a odstraňte je.

     A **okně navigace** nemůže obsahovat další prvky uživatelského rozhraní, jako **mřížky**.

1. V **vlastnosti** okno, rozbalte **běžné** uzel kategorie a zvolte **název** vlastnost a potom zadejte `ExpenseIt` a stiskněte klávesu **Enter**  klíč.

     Všimněte si, že **název** v okně XAML, změní se atribut tak, aby odpovídala nové hodnotě. Můžete upravit vlastnosti XAML v okně XAML nebo **vlastnosti** okno a změny jsou synchronizovány.

1. V okně XAML, nastavte hodnotu **výška** element `375`a nastavte hodnotu **šířka** vlastnost, která má `500`.

     Tyto prvky odpovídají **výška** a **šířka** vlastnosti, nalezené v **rozložení** kategorie v **vlastnosti** okno.

     Vaše **MainWindow.xaml** soubor by měl nyní vypadat jako v C#:

    ```xaml
    <NavigationWindow x:Class="ExpenseIt.MainWindow"
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
            xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
            xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
            xmlns:local="clr-namespace:ExpenseIt"
            mc:Ignorable="d"
            Title="ExpenseIt" Height="375" Width="500">
    </NavigationWindow>
    ```

    Nebo v jazyce Visual Basic takto:

    ```xaml
    <NavigationWindow x:Class="MainWindow"
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
            xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
            xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
            xmlns:local="clr-namespace:ExpenseIt"
            mc:Ignorable="d"
            Title="ExpenseIt" Height="375" Width="500">
    </NavigationWindow>
    ```

### <a name="to-modify-the-code-behind-file-c"></a>K úpravě souboru kódu na pozadí (C#)

1. V **Průzkumníku řešení**, rozbalte **MainWindow.xaml** uzlu a otevřete **MainWindow.xaml.cs** souboru.

1. Vyhledejte řádek `public partial class MainWindow : Window` a nahraďte ho `public partial class MainWindow : NavigationWindow`.

    Tato operace změní `MainWindow` odvozena od třídy `NavigationWindow`. V jazyce Visual Basic tomu automaticky dojde při změně okna v jazyce XAML, takže je nutné provést žádné změny kódu.

## <a name="adding-files-to-the-application"></a>Přidávání souborů do aplikace

V této části přidáte dvě stránky a bitovou kopii do aplikace.

### <a name="to-add-a-home-screen"></a>Chcete-li přidat domovskou obrazovku

1. V **Průzkumníku řešení**, otevřete místní nabídku pro **ExpenseIt –** uzel a zvolte **přidat** > **stránky**.

1. V **přidat novou položku** dialogovém okně, vyberte **název** text a zadejte `ExpenseItHome`a potom zvolte **přidat** tlačítko.

     Tato stránka je první okno, které se zobrazí, když je aplikace spuštěna.

1. V návrháři, vyberte **ExpenseItHome.xaml** kartě, pokud již není aktivní návrháře karty.

1. Vyberte `Title` atribut a změňte jeho hodnotu na **ExpenseIt – - Domů**.

     Vaše **ExpenseItHome.xaml** soubor by měl nyní vypadat jako v C#:

    ```xaml
    <Page x:Class="ExpenseIt.ExpenseItHome"
          xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
          xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
          xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
          xmlns:local="clr-namespace:ExpenseIt"
          mc:Ignorable="d"
          d:DesignHeight="300" d:DesignWidth="300"
          Title="ExpenseIt - Home">
        <Grid>

        </Grid>
    </Page>
    ```

    V jazyce Visual Basic se jemně liší první řádek:

    ```xaml
    <Page x:Class="ExpenseItHome"
    ```

1. V návrháři, vyberte **MainWindow.xaml** kartě.

1. Vyhledejte řádek `Title="ExpenseIt" Height="375" Width="500">` elementu a přidejte `Source="ExpenseItHome.xaml"` vlastnost.

     Nastaví tato **ExpenseItHome.xaml** na první stránce otevřelo při spuštění aplikace. Vaše **MainWindow.xaml** soubor by měl nyní vypadat jako v C#:

    ```xaml
    <NavigationWindow x:Class="ExpenseIt.MainWindow"
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
            xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
            xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
            xmlns:local="clr-namespace:ExpenseIt"
            mc:Ignorable="d"
            Title="ExpenseIt" Height="375" Width="500" Source="ExpenseItHome.xaml">
    </NavigationWindow>
    ```

    V jazyce Visual Basic se jemně liší první řádek:

    ```xaml
    <NavigationWindow x:Class="MainWindow"
    ```

     Jak se vlastností, které jste nastavili dříve, můžete mít nastavit `Source` vlastnost **různé** kategorii **vlastnosti** okno.

### <a name="to-add-a-details-window"></a>Chcete-li přidat okno podrobností

1. V **Průzkumníku řešení**, otevřete místní nabídku pro **ExpenseIt –** uzel a zvolte **přidat** > **stránky**.

1. V **přidat novou položku** dialogovém okně, vyberte **název** text a zadejte `ExpenseReportPage`a potom zvolte **přidat** tlačítko.

     Toto okno se zobrazí sestavu jednotlivých výdajů.

1. V návrháři, vyberte **ExpenseReportPage.xaml** kartě, pokud již není aktivní návrháře karty.

1. Vyberte `Title` atribut a změňte jeho hodnotu na **ExpenseIt – - zobrazení výdajů**.

     Váš soubor ExpenseReportPage.xaml by měl nyní vypadat například takto v jazyce C#:

    ```xaml
    <Page x:Class="ExpenseIt.ExpenseReportPage"
          xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
          xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
          xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
          xmlns:local="clr-namespace:ExpenseIt"
          mc:Ignorable="d"
          d:DesignHeight="300" d:DesignWidth="300"
          Title="ExpenseIt - View Expense">
        <Grid>

        </Grid>
    </Page>
    ```

    V jazyce Visual Basic se jemně liší první řádek:

    ```xaml
    <Page x:Class="ExpenseReportPage"
    ```

1. Na řádku nabídek zvolte **ladění** > **spustit ladění** (nebo stiskněte klávesu **F5**) ke spuštění aplikace.

     Následující obrázek znázorňuje aplikace s okno navigačních tlačítek.

     ![Snímek obrazovky ExpenseIt –](../designers/media/gettingstartedfigure1.png "GettingStartedFigure1")

1. Zavřete aplikaci se vraťte do režimu návrhu.

## <a name="creating-the-user-interface"></a>Vytvoření uživatelského rozhraní

Rozložení poskytuje seřazené způsob, jak umístit elementy a také spravuje velikost a umístění těchto elementů při změně velikosti formuláře. V této části vytvoříte jednoho sloupce mřížky s tři řádky. Budete přidání ovládacích prvků do dvě stránky, přidat kód a nakonec definovat opakovaně použitelné styly pro ovládací prvky.

### <a name="to-create-the-layout"></a>Chcete-li vytvořit rozložení

1. Otevřete **ExpenseItHome.xaml** a zvolte `<Grid>` elementu.

1. V **vlastnosti** okno, rozbalte **rozložení** uzel kategorie a sadu **okraj** hodnoty k `10`, `10`, `0`a `10`, která odpovídá levé, pravé, horní a dolní okraj.

     Element `Margin="10,0,10,10"` je přidán do `<Grid>` element v XAML. Ještě jednou, může zadání těchto hodnot přímo v kódu XAML místo v **vlastnosti** okno s stejného výsledku.

1. Přidejte následující kód XAML, který `Grid` elementu, který chcete vytvořit definice řádků a sloupců:

    ```xaml
    <Grid.ColumnDefinitions>
        <ColumnDefinition />
    </Grid.ColumnDefinitions>
    <Grid.RowDefinitions>
        <RowDefinition Height="Auto"/>
        <RowDefinition />
        <RowDefinition Height="Auto"/>
    </Grid.RowDefinitions>
    ```

### <a name="to-add-controls"></a>K přidávání ovládacích prvků

1. Otevřete **ExpenseItHome.xaml**.

1. Přidejte následující kód XAML právě vyšší `</Grid>` značky k vytvoření `Border`, `ListBox` a `Button` ovládacích prvků:

    ```xaml
    <!-- People list -->
      <Border Grid.Column="0" Grid.Row="0" Height="35" Padding="5" Background="#4E87D4">
          <Label VerticalAlignment="Center" Foreground="White">Names</Label>
      </Border>
      <ListBox Name="peopleListBox" Grid.Column="0" Grid.Row="1">
          <ListBoxItem>Mike</ListBoxItem>
          <ListBoxItem>Lisa</ListBoxItem>
          <ListBoxItem>John</ListBoxItem>
          <ListBoxItem>Mary</ListBoxItem>
      </ListBox>

      <!-- View report button -->
      <Button Grid.Column="0" Grid.Row="2" Margin="0,10,0,0" Width="125"
    Height="25" HorizontalAlignment="Right">View</Button>
    ```

     Všimněte si, že ovládací prvky se zobrazí v okně návrhu. Může také vytvoříte ovládací prvky přetažením z **sada nástrojů** okna do okna návrhu a nastavování jejich vlastností **vlastnosti** okno.

1. Sestavte a spusťte aplikaci. Následující obrázek znázorňuje běhu vzhled ovládacích prvků, které jsou vytvořené pomocí XAML v tomto postupu.

     ![Snímek obrazovky ExpenseIt –](../designers/media/gettingstartedfigure2.png "GettingStartedFigure2")

1. Zavřete aplikaci se vraťte do režimu návrhu.

### <a name="to-add-a-background-image"></a>Chcete-li přidat obrázek na pozadí

1. Vyberte následující obrázek a uložte ho jako `watermark.png`.

     ![Vodoznak návod](../designers/media/wpf_watermark.png "vodoznak")

    > [!NOTE]
    >  Případně můžete vytvořit vlastní image a uložte ho jako `watermark.png`.

1. V **Průzkumníku řešení**, otevřete místní nabídku pro **ExpenseIt –** uzel a zvolte **přidat** > **existující položka**.

1. V **přidat existující položku** dialogové okno, Najít **watermark.png** bitovou kopii, kterou jste právě přidali, zvolte jej a potom zvolte **přidat** tlačítko.

    > [!NOTE]
    >  Budete muset Rozbalit **typy souborů** seznam a vyberte **soubory obrázků**.

1. Otevřete **ExpenseItHome.xaml** souboru a přidejte následující kód XAML právě vyšší `</Grid>` značka vytvořit obrázek na pozadí:

    ```xaml
    <Grid.Background>
        <ImageBrush ImageSource="watermark.png"/>
    </Grid.Background>
    ```

### <a name="to-add-a-title"></a>Přidání názvu

1. Otevřete **ExpenseItHome.xaml**.

1. Vyhledejte řádek `<Grid.ColumnDefinitions>` a přidejte následující právě pod ním:

    ```xaml
    <ColumnDefinition Width="230" />
    ```

    Tím se vytvoří sloupec nalevo od ostatních sloupců s pevnou šířkou 230 pixelů.

1. Vyhledejte řádek `<Grid.RowDefinitions>` a přidejte následující právě pod ním:

    ```xaml
    <RowDefinition />
    ```

    Tento postup přidá řádek do horní části mřížky.

1. Přesunout ovládacích prvků na druhý sloupec nastavením `Grid.Column` hodnotu 1. Každý ovládací prvek dolů řádek, zvýšením každý `Grid.Row` hodnoty 1.

    1. Vyhledejte řádek `<Border Grid.Column="0" Grid.Row="0" Height="35" Padding="5" Background="#4E87D4">`. Změnit `Grid.Column="0"` k `Grid.Column="1"` a změňte `Grid.Row="0"` k `Grid.Row="1"`.

    1. Vyhledejte řádek `<ListBox Name="peopleListBox" Grid.Column="0" Grid.Row="1"`. Změnit `Grid.Column="0"` k `Grid.Column="1"` a změňte `Grid.Row="1"` k `Grid.Row="2"`.

    1. Vyhledejte řádek `<Button Grid.Column="0" Grid.Row="2" Margin="0,10,0,0" Width="125"`. Změnit `Grid.Column="0"` k `Grid.Column="1"` a změňte `Grid.Row="2"` k `Grid.Row="3"`.

1. Těsně před `<Border` elementu, přidejte následující kód XAML zobrazit název:

    ```xaml
    <Label Grid.Column="1" VerticalAlignment="Center" FontFamily="Trebuchet MS"
            FontWeight="Bold" FontSize="18" Foreground="#0066cc">
        View Expense Report
    </Label>
    ```

     Obsah **ExpenseItHome.xaml** by teď měl vypadat takto v jazyce C#:

    ```xaml
    <Page x:Class="ExpenseIt.ExpenseItHome"
          xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
          xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
          xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
          xmlns:local="clr-namespace:ExpenseIt"
          mc:Ignorable="d"
          d:DesignHeight="300" d:DesignWidth="300"
          Title="ExpenseIt - Home">
        <Grid Margin="10,0,10,10">
            <Grid.ColumnDefinitions>
                <ColumnDefinition Width="230" />
                <ColumnDefinition />
            </Grid.ColumnDefinitions>
            <Grid.RowDefinitions>
                <RowDefinition />
                <RowDefinition Height="Auto"/>
                <RowDefinition />
                <RowDefinition Height="Auto"/>
            </Grid.RowDefinitions>
            <Border Grid.Column="1" Grid.Row="1" Height="35" Padding="5" Background="#4E87D4">
                <Label VerticalAlignment="Center" Foreground="White">Names</Label>
            </Border>
            <!-- People list -->
            <Label Grid.Column="1" VerticalAlignment="Center" FontFamily="Trebuchet MS"
            FontWeight="Bold" FontSize="18" Foreground="#0066cc">
                View Expense Report
            </Label>
            <ListBox Name="peopleListBox" Grid.Column="1" Grid.Row="2">
                <ListBoxItem>Mike</ListBoxItem>
                <ListBoxItem>Lisa</ListBoxItem>
                <ListBoxItem>John</ListBoxItem>
                <ListBoxItem>Mary</ListBoxItem>
            </ListBox>

            <!-- View report button -->
            <Button Grid.Column="1" Grid.Row="3" Margin="0,10,0,0" Width="125"
    Height="25" HorizontalAlignment="Right">View</Button>
            <Grid.Background>
                <ImageBrush ImageSource="watermark.png"/>
            </Grid.Background>
        </Grid>
    </Page>
    ```

    V jazyce Visual Basic se jemně liší první řádek:

    ```xaml
    <Page x:Class="ExpenseItHome"
    ```

1. Pokud sestavení a spuštění aplikace v tomto okamžiku by měl vypadat jako na následujícím obrázku:

     ![Snímek obrazovky ExpenseIt –](../designers/media/gettingstartedfigure3.png "GettingStartedFigure3")

### <a name="to-add-code-to-the-button"></a>Chcete-li přidat kód pro tlačítko

1. Otevřete **ExpenseItHome.xaml**.

1. Vyberte `Button` elementu a přidejte následující kód XAML ihned po `HorizontalAlignment="Right"` element: `Click="Button_Click"`.

     Tento postup přidá obslužné rutiny události pro tlačítka `Click` událostí. **Tlačítko** element kódu by teď měl vypadat takto:

    ```xaml
    <!-- View report button -->
      <Button Grid.Column="1" Grid.Row="3" Margin="0,10,0,0" Width="125"
    Height="25" HorizontalAlignment="Right" Click="Button_Click">View</Button>
    ```

1. Otevřete **ExpenseItHome.xaml.cs** nebo **ExpenseItHome.xaml.vb** souboru.

1. Přidejte následující kód, který `ExpenseItHome` třídy:

   ```csharp
   private void Button_Click(object sender, RoutedEventArgs e)
   {
       // View Expense Report
       ExpenseReportPage expenseReportPage = new ExpenseReportPage();
       this.NavigationService.Navigate(expenseReportPage);
   }
   ```

   ```vb
   Private Sub Button_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)
       ' View Expense Report
       Dim expenseReportPage As New ExpenseReportPage()
   Me.NavigationService.Navigate(expenseReportPage)
   End Sub
   ```

    Tuto obslužnou rutinu události při kliknutí na tlačítko otevře se stránka sestavy náklady.

### <a name="to-create-the-ui-for-the-report-page"></a>Chcete-li vytvořit uživatelské rozhraní pro stránky sestavy

1. Otevřete **ExpenseReportPage.xaml**.

    Tato stránka zobrazuje vyúčtování pro osobě, která je vybrána na domovské stránce.

1. Přidejte následující kód XAML mezi `<Grid>` a `</Grid>` značky:

    ```xaml
    <Grid.Background>
        <ImageBrush ImageSource="watermark.png" />
    </Grid.Background>
    <Grid.ColumnDefinitions>
        <ColumnDefinition Width="230" />
        <ColumnDefinition />
    </Grid.ColumnDefinitions>
    <Grid.RowDefinitions>
        <RowDefinition Height="Auto" />
        <RowDefinition />
    </Grid.RowDefinitions>

    <Label Grid.Column="1" VerticalAlignment="Center" FontFamily="Trebuchet MS"
    FontWeight="Bold" FontSize="18" Foreground="#0066cc">
        Expense Report For:
    </Label>
    <Grid Margin="10" Grid.Column="1" Grid.Row="1">

        <Grid.ColumnDefinitions>
            <ColumnDefinition />
            <ColumnDefinition />
        </Grid.ColumnDefinitions>
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto" />
            <RowDefinition Height="Auto" />
            <RowDefinition />
        </Grid.RowDefinitions>

        <!-- Name -->
        <StackPanel Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="0" Orientation="Horizontal">
            <Label Margin="0,0,0,5" FontWeight="Bold">Name:</Label>
            <Label Margin="0,0,0,5" FontWeight="Bold"></Label>
        </StackPanel>

        <!-- Department -->
        <StackPanel Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="1" Orientation="Horizontal">
            <Label Margin="0,0,0,5" FontWeight="Bold">Department:</Label>
            <Label Margin="0,0,0,5" FontWeight="Bold"></Label>
        </StackPanel>

        <Grid Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="2" VerticalAlignment="Top"
              HorizontalAlignment="Left">
            <!-- Expense type and Amount table -->
            <DataGrid  AutoGenerateColumns="False" RowHeaderWidth="0" >
                <DataGrid.ColumnHeaderStyle>
                    <Style TargetType="{x:Type DataGridColumnHeader}">
                        <Setter Property="Height" Value="35" />
                        <Setter Property="Padding" Value="5" />
                        <Setter Property="Background" Value="#4E87D4" />
                        <Setter Property="Foreground" Value="White" />
                    </Style>
                </DataGrid.ColumnHeaderStyle>
                <DataGrid.Columns>
                    <DataGridTextColumn Header="ExpenseType" />
                    <DataGridTextColumn Header="Amount"  />
                </DataGrid.Columns>
            </DataGrid>
        </Grid>
    </Grid>
    ```

     Toto uživatelské rozhraní je podobná uživatelského rozhraní pro domovskou stránku vytvořit, ale v se zobrazí data sestavy **DataGrid** ovládacího prvku.

1. Sestavte a spusťte aplikaci.

1. Vyberte **zobrazení** tlačítko.

     Zobrazí se stránka sestavy výdajů.

     Následující obrázek znázorňuje stránka sestavy výdajů. Všimněte si, že je povolena back navigační tlačítko.

     ![Snímek obrazovky ExpenseIt –](../designers/media/gettingstartedfigure4.png "GettingStartedFigure4")

### <a name="to-style-controls"></a>Pro ovládací prvky stylu

1. Otevřete **App.xaml** souboru (C#) nebo **Application.xaml** souboru (Visual Basic).

1. Přidejte následující XAML mezi `<Application.Resources>` a `</Application.Resources>` značky:

    ```xaml
    <!-- Header text style -->
    <Style x:Key="headerTextStyle">
        <Setter Property="Label.VerticalAlignment" Value="Center"></Setter>
        <Setter Property="Label.FontFamily" Value="Trebuchet MS"></Setter>
        <Setter Property="Label.FontWeight" Value="Bold"></Setter>
        <Setter Property="Label.FontSize" Value="18"></Setter>
        <Setter Property="Label.Foreground" Value="#0066cc"></Setter>
    </Style>

    <!-- Label style -->
    <Style x:Key="labelStyle" TargetType="{x:Type Label}">
        <Setter Property="VerticalAlignment" Value="Top" />
        <Setter Property="HorizontalAlignment" Value="Left" />
        <Setter Property="FontWeight" Value="Bold" />
        <Setter Property="Margin" Value="0,0,0,5" />
    </Style>

    <!-- DataGrid header style -->
    <Style x:Key="columnHeaderStyle" TargetType="{x:Type DataGridColumnHeader}">
        <Setter Property="Height" Value="35" />
        <Setter Property="Padding" Value="5" />
        <Setter Property="Background" Value="#4E87D4" />
        <Setter Property="Foreground" Value="White" />
    </Style>

    <!-- List header style -->
    <Style x:Key="listHeaderStyle" TargetType="{x:Type Border}">
        <Setter Property="Height" Value="35" />
        <Setter Property="Padding" Value="5" />
        <Setter Property="Background" Value="#4E87D4" />
    </Style>

    <!-- List header text style -->
    <Style x:Key="listHeaderTextStyle" TargetType="{x:Type Label}">
        <Setter Property="Foreground" Value="White" />
        <Setter Property="VerticalAlignment" Value="Center" />
        <Setter Property="HorizontalAlignment" Value="Left" />
    </Style>

    <!-- Button style -->
    <Style x:Key="buttonStyle" TargetType="{x:Type Button}">
        <Setter Property="Width" Value="125" />
        <Setter Property="Height" Value="25" />
        <Setter Property="Margin" Value="0,10,0,0" />
        <Setter Property="HorizontalAlignment" Value="Right" />
    </Style>
    ```

     Tato XAML přidá následující styly:

    -   `headerTextStyle`: Chcete-li formát názvu stránky `Label`.

    -   `labelStyle`: K formátování `Label` ovládací prvky.

    -   `columnHeaderStyle`: K formátování `DataGridColumnHeader`.

    -   `listHeaderStyle`: K formátování záhlaví seznamu `Border` ovládací prvky.

    -   `listHeaderTextStyle`: K formátování záhlaví seznamu **popisek**.

    -   `buttonStyle`: K formátování `Button` na **ExpenseItHome.xaml** stránky.

1. Otevřete **ExpenseItHome.xaml** a nahraďte všechno mezi `<Grid>` a `</Grid>` prvky s následující XAML:

    ```xaml
    <Grid.ColumnDefinitions>
                <ColumnDefinition Width="230" />
                <ColumnDefinition />
            </Grid.ColumnDefinitions>

            <Grid.RowDefinitions>
                <RowDefinition/>
                <RowDefinition Height="Auto"/>
                <RowDefinition />
                <RowDefinition Height="Auto"/>
            </Grid.RowDefinitions>
            <Label Grid.Column="1" Style="{StaticResource headerTextStyle}" >
                View Expense Report
            </Label>
            <!-- People list -->
                  <Border Grid.Column="1" Grid.Row="1" Style="{StaticResource listHeaderStyle}">
                <Label Style="{StaticResource listHeaderTextStyle}">Names</Label>
            </Border>
            <ListBox Name="peopleListBox" Grid.Column="1" Grid.Row="2">
                <ListBoxItem>Mike</ListBoxItem>
                <ListBoxItem>Lisa</ListBoxItem>
                <ListBoxItem>John</ListBoxItem>
                <ListBoxItem>Mary</ListBoxItem>
            </ListBox>

            <!-- View report button -->
            <Button Grid.Column="1" Grid.Row="3" Click="Button_Click" Style="{StaticResource buttonStyle}">View</Button>
            <Grid.Background>
                <ImageBrush ImageSource="watermark.png"  />
            </Grid.Background>
    ```

     Vlastnosti, jako `VerticalAlignment` a `FontFamily` které definují, jak vypadá každý ovládací prvek se odeberou a nahrazuje použití stylů.

1. Otevřete **ExpenseReportPage.xaml** a nahraďte všechno mezi `<Grid>` a finální `</Grid>` prvky s následující XAML:

    ```xaml
    <Grid.Background>
        <ImageBrush ImageSource="watermark.png" />
    </Grid.Background>
    <Grid.ColumnDefinitions>
        <ColumnDefinition Width="230" />
        <ColumnDefinition />
    </Grid.ColumnDefinitions>
    <Grid.RowDefinitions>
        <RowDefinition Height="Auto" />
        <RowDefinition />
    </Grid.RowDefinitions>
    <Label Grid.Column="1" Style="{StaticResource headerTextStyle}">
        Expense Report For:
    </Label>
    <Grid Margin="10" Grid.Column="1" Grid.Row="1">
        <Grid.ColumnDefinitions>
            <ColumnDefinition />
            <ColumnDefinition />
        </Grid.ColumnDefinitions>
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto" />
            <RowDefinition Height="Auto" />
            <RowDefinition />
        </Grid.RowDefinitions>

        <!-- Name -->
        <StackPanel Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="0" Orientation="Horizontal">
            <Label Style="{StaticResource labelStyle}">Name:</Label>
            <Label Style="{StaticResource labelStyle}"></Label>
        </StackPanel>

        <!-- Department -->
        <StackPanel Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="1"
    Orientation="Horizontal">
            <Label Style="{StaticResource labelStyle}">Department:</Label>
            <Label Style="{StaticResource labelStyle}"></Label>
        </StackPanel>

        <Grid Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="2" VerticalAlignment="Top"
              HorizontalAlignment="Left">
            <!-- Expense type and Amount table -->
            <DataGrid ColumnHeaderStyle="{StaticResource columnHeaderStyle}"
                      AutoGenerateColumns="False" RowHeaderWidth="0" >
                <DataGrid.Columns>
                    <DataGridTextColumn Header="ExpenseType" />
                    <DataGridTextColumn Header="Amount"  />
                </DataGrid.Columns>
            </DataGrid>
        </Grid>
    </Grid>
    ```

     Tento postup přidá stylů pro `<Label>` a `<Border>` elementy.

## <a name="connecting-to-data"></a>Připojení k datům
 V této části vytvoříte zprostředkovatele dat a dat šablonu a potom se připojte ovládacích prvků pro zobrazení dat.

### <a name="to-bind-data-to-a-control"></a>K vytvoření vazby dat k ovládacímu prvku

1. Otevřete **ExpenseItHome.xaml** a zvolte `<Grid>` elementu.

1. Přidejte následující kód XAML:

    ```xaml
    <Grid.Resources>
    <!-- Expense Report Data -->
    <XmlDataProvider x:Key="ExpenseDataSource" XPath="Expenses">
        <x:XData>
            <Expenses xmlns="">
                <Person Name="Mike" Department="Legal">
                    <Expense ExpenseType="Lunch" ExpenseAmount="50" />
                    <Expense ExpenseType="Transportation" ExpenseAmount="50" />
                </Person>
                <Person Name="Lisa" Department="Marketing">
                    <Expense ExpenseType="Document printing"
          ExpenseAmount="50"/>
                    <Expense ExpenseType="Gift" ExpenseAmount="125" />
                </Person>
                <Person Name="John" Department="Engineering">
                    <Expense ExpenseType="Magazine subscription"
         ExpenseAmount="50"/>
                    <Expense ExpenseType="New machine" ExpenseAmount="600" />
                    <Expense ExpenseType="Software" ExpenseAmount="500" />
                </Person>
                <Person Name="Mary" Department="Finance">
                    <Expense ExpenseType="Dinner" ExpenseAmount="100" />
                </Person>
            </Expenses>
        </x:XData>
    </XmlDataProvider>
    </Grid.Resources>
    ```

     Tento kód vytvoří `XmlDataProvider` třídu, která obsahuje data pro každou osobu. Obvykle to by načíst jako soubor, ale pro zjednodušení je přidat data vložené.

1. Uvnitř `<Grid.Resources>` elementu, přidejte následující kód XAML:

    ```xaml
    <!-- Name item template -->
    <DataTemplate x:Key="nameItemTemplate">
        <Label Content="{Binding XPath=@Name}"/>
    </DataTemplate>
    ```

     Tím se přidá `Data Template` určující způsob zobrazení dat v **ListBox**.

1. Nahradit existující `<ListBox>` element s následující XAML:

    ```xaml
    <ListBox Name="peopleListBox" Grid.Column="1" Grid.Row="2"
             ItemsSource="{Binding Source={StaticResource ExpenseDataSource}, XPath=Person}"
             ItemTemplate="{StaticResource nameItemTemplate}">
    </ListBox>
    ```

     Tento kód váže `ItemsSource` vlastnost `ListBox` ke zdroji dat a použije šablona dat jako `ItemTemplate`.

### <a name="to-connect-data-to-controls"></a>Pro připojení dat k ovládacím prvkům

1. Otevřete **ExpenseReportPage.xaml.vb** nebo **ExpenseReportPage.xaml.cs**.

1. V jazyce C#, přidejte následující konstruktor **ExpenseReportPage** třídy, nebo v jazyce Visual Basic nahraďte existující třídy následujícím kódem:

   ```csharp
   // Custom constructor to pass expense report data
   public ExpenseReportPage(object data):this()
   {
       // Bind to expense report data.
       this.DataContext = data;
   }
   ```

   ```vb
   Partial Public Class ExpenseReportPage
   Inherits Page
       Public Sub New()
       InitializeComponent()
       End Sub

       ' Custom constructor to pass expense report data
       Public Sub New(ByVal data As Object)
           Me.New()
           ' Bind to expense report data.
           Me.DataContext = data
       End Sub
   End Class
   ```

   Tento konstruktor přijímá objekt dat jako parametr. Datový objekt v tomto případě bude obsahovat název vybraného uživatele.

1. Otevřete **ExpenseItHome.xaml.vb** nebo **ExpenseItHome.xaml.cs**.

1. Nahraďte `Click` kód obslužné rutiny událostí s následující:

   ```csharp
   private void Button_Click(object sender, RoutedEventArgs e)
   {
       // View Expense Report
       ExpenseReportPage expenseReportPage = new ExpenseReportPage(this.peopleListBox.SelectedItem);
       this.NavigationService.Navigate(expenseReportPage);
   }
   ```

   ```vb
   Private Sub Button_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)
       ' View Expense Report
       Dim expenseReportPage As New ExpenseReportPage(Me.peopleListBox.SelectedItem)
       Me.NavigationService.Navigate(expenseReportPage)
   End Sub
   ```

   Tento kód zavolá nové konstruktoru.

### <a name="to-update-the-ui-with-data-templates"></a>Aktualizace uživatelského rozhraní pomocí šablony dat

1. Otevřete **ExpenseReportPage.xaml**.

1. Nahraďte kód XAML pro **název** a **oddělení** `<StackPanel` prvky s následující:

    ```xaml
    <!-- Name -->
    <StackPanel Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="0" Orientation="Horizontal">
        <Label Style="{StaticResource labelStyle}">Name:</Label>
        <Label Style="{StaticResource labelStyle}" Content="{Binding XPath=@Name}"></Label>
    </StackPanel>

    <!-- Department -->
    <StackPanel Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="1" Orientation="Horizontal">
        <Label Style="{StaticResource labelStyle}">Department:</Label>
        <Label Style="{StaticResource labelStyle}" Content="{Binding XPath=@Department}"></Label>
    </StackPanel>
    ```

     Tím je vytvořena vazba **popisek** ovládací prvky pro vlastnosti zdroje příslušná data.

1. Přidejte následující kód XAML uvnitř `<Grid>` element:

    ```xaml
    <!--Templates to display expense report data-->
    <Grid.Resources>
        <!-- Reason item template -->
        <DataTemplate x:Key="typeItemTemplate">
            <Label Content="{Binding XPath=@ExpenseType}"/>
        </DataTemplate>
        <!-- Amount item template -->
        <DataTemplate x:Key="amountItemTemplate">
            <Label Content="{Binding XPath=@ExpenseAmount}"/>
        </DataTemplate>
    </Grid.Resources>
    ```

     Definuje způsob, jak zobrazit data sestavy výdajů.

1. Nahraďte `<DataGrid>` element s následující:

    ```xaml
    <!-- Expense type and Amount table -->
    <DataGrid ItemsSource="{Binding XPath=Expense}" ColumnHeaderStyle="{StaticResource columnHeaderStyle}" AutoGenerateColumns="False" RowHeaderWidth="0" >

        <DataGrid.Columns>
            <DataGridTextColumn Header="ExpenseType" Binding="{Binding XPath=@ExpenseType}"  />
            <DataGridTextColumn Header="Amount" Binding="{Binding XPath=@ExpenseAmount}" />
        </DataGrid.Columns>

    </DataGrid>
    ```

     Tím se přidá **ItemSource** a definuje vazby u položek výdajů.

1. Sestavte a spusťte aplikaci.

1. Zvolte osoby a pak **zobrazení** tlačítko.

     Následující obrázek znázorňuje obě stránky aplikace ExpenseIt – ovládací prvky, rozložení, styly, datové vazby a šablony dat použít.

     ![Snímky obrazovky ukázkové ExpenseIt –](../designers/media/gettingstartedfigure5.png "GettingStartedFigure5")

## <a name="best-practices"></a>Doporučené postupy

Tento příklad ukazuje základy grafického subsystému WPF a v důsledku toho nedodrží osvědčené postupy pro vývoj aplikací. Podle potřeby komplexní přehled WPF a rozhraní .NET Framework aplikace vývoj osvědčené postupy, najdete v následujících tématech:

-   Usnadnění – [usnadnění – doporučené postupy](/dotnet/framework/ui-automation/accessibility-best-practices)

-   Zabezpečení – [zabezpečení systému Windows Presentation Foundation](/dotnet/framework/wpf/security-wpf)

-   Lokalizace - [WPF globalizace a lokalizace – přehled](/dotnet/framework/wpf/advanced/wpf-globalization-and-localization-overview)

-   Výkon – [optimalizace výkonu aplikace WPF](/dotnet/framework/wpf/advanced/optimizing-wpf-application-performance)

## <a name="whats-next"></a>Co je další

Nyní máte několik technik k dispozici pro vytvoření aplikace pomocí grafického subsystému WPF. Teď byste měli mít základní znalosti o stavební bloky aplikace WPF vázané na data. Toto téma je rozhodně není vyčerpávající, ale zpravidla nyní také mít smysl pro některé možnosti, které můžete zjistit, na vlastní nad rámec techniky v tomto tématu.

Další informace o modelech WPF architektura a programování najdete v následujících tématech:

-   [Architektura WPF](/dotnet/framework/wpf/advanced/wpf-architecture)

-   [XAML – přehled](/dotnet/framework/wpf/advanced/xaml-overview-wpf)

-   [Přehled vlastností závislosti](/dotnet/framework/wpf/advanced/dependency-properties-overview)

-   [Rozložení systému](/dotnet/framework/wpf/advanced/layout)

-   [Styly a šablony](/dotnet/framework/wpf/controls/styles-and-templates)

Další informace o vytváření aplikací najdete v následujících tématech:

-   [Přehled vývoje aplikace](/dotnet/framework/wpf/app-development/index)

-   [Přehled ovládacích prvků](/dotnet/framework/wpf/controls/index)

-   [Přehled datových vazeb](/dotnet/framework/wpf/data/data-binding-overview)

-   [WPF grafiky, animace a přehled média](/dotnet/framework/wpf/graphics-multimedia/index)

-   [Dokumenty v platformě WPF](/dotnet/framework/wpf/advanced/documents-in-wpf)

## <a name="see-also"></a>Viz také

[Vytvoření moderních desktopových aplikací pomocí Windows Presentation Foundation](../designers/create-modern-desktop-applications-with-windows-presentation-foundation.md)
