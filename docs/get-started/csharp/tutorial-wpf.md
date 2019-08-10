---
title: Hello World aplikace pomocí WPF vC#
description: Vytvořte jednoduchou aplikaci Windows Desktop .NET v C# systému Visual Studio pomocí architektury rozhraní Windows Presentation Foundation (WPF).
ms.custom: seodec18, get-started
ms.date: 08/09/2019
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
ms.topic: conceptual
dev_langs:
- CSharp
ms.assetid: f84339c7-d617-4f56-bfcd-af2215c347ba
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 8803bf6992608a496d560b68b71545d764803760
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68924393"
---
# <a name="tutorial-create-a-simple-application-with-c"></a>Kurz: Vytvoření jednoduché aplikace pomocí jazyka C\#

Po dokončení tohoto kurzu se seznámíte s mnoha nástroji, dialogovými okny a návrháři, které můžete použít při vývoji aplikací pomocí sady Visual Studio. Vytvoříte aplikaci "Hello, World", navrhnete uživatelské rozhraní, přidáte kód a budete ladit chyby, zatímco se naučíte pracovat v integrovaném vývojovém prostředí ([IDE](visual-studio-ide.md)).

::: moniker range="vs-2017"
Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) stránku a nainstalovat zdarma.
::: moniker-end
::: moniker range=">=vs-2019"
Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) stránku a nainstalovat zdarma.
::: moniker-end

## <a name="configure-the-ide"></a>Nastavení integrovaného vývojového prostředí (IDE)

::: moniker range="vs-2017"

Při prvním otevření aplikace Visual Studio budete vyzváni k přihlášení. Tento krok je pro tento kurz volitelný. V dalším kroku se zobrazí dialogové okno s výzvou, abyste si zvolili vývojové nastavení a barevný motiv. Ponechte výchozí nastavení a klikněte na **Spustit Visual Studio**.

![Dialogové okno zvolit nastavení](../media/exploreide-settings.png)

Po spuštění sady Visual Studio se zobrazí okna nástrojů, nabídky a panely nástrojů a prostor hlavního okna. Okna nástrojů jsou ukotvena na levé a pravé straně okna aplikace, s možností snadného **spuštění**, řádku nabídek a standardní panel nástrojů v horní části. Ve středu okna aplikace je **Úvodní stránka**. Při načítání řešení nebo projektu se zobrazí editory a návrháři v prostoru, kde je **Úvodní stránka** . Při vývoji aplikace strávíte nejvíce času v této centrální oblasti.

![Integrované vývojové prostředí (IDE) sady Visual Studio 2017 s obecným nastavením](../media/exploreide-idewithgeneralsettings.png "Snímek obrazovky s prostředím IDE sady Visual Studio 2017 s použitým obecným nastavením")

::: moniker-end

::: moniker range=">=vs-2019"

Při spuštění sady Visual Studio se nejprve otevře okno Start. Pokud chcete otevřít vývojové prostředí, vyberte **pokračovat bez kódu** . Zobrazí se okna nástrojů, nabídky a panely nástrojů a prostor hlavního okna. Okna nástrojů jsou ukotvena na levé a pravé straně okna aplikace, pomocí vyhledávacího pole, řádku nabídek a standardního panelu nástrojů v horní části. Při načítání řešení nebo projektu se editory a návrháře zobrazí v centrálním prostoru okna aplikace. Při vývoji aplikace strávíte nejvíce času v této centrální oblasti.

::: moniker-end

## <a name="create-the-project"></a>Vytvoření projektu

Při vytváření aplikace v systému Visual Studio je třeba nejprve vytvořit projekt a řešení. V tomto příkladu vytvoříte projekt Windows Presentation Foundation (WPF).

::: moniker range="vs-2017"

1. Vytvořte nový projekt. Na panelu nabídek vyberte **soubor** > **Nový** > **projekt**.

     ![Na panelu nabídek vyberte možnosti soubor, nový, projekt] . (../media/exploreide-filenewproject.png "Snímek obrazovky s panelem nabídek, kde si zvolíte soubor, nový, projekt")

1. V dialogovém **okně Nový projekt** vyberte kategorii nainstalovaná > aplikace  > **Visual C#**  **Windows Desktop** a pak vyberte šablonu **aplikace WPF (.NET Framework)** . Pojmenujte projekt **HelloWPFApp**a vyberte **OK**.

     ![Šablona aplikace WPF v dialogovém okně Nový projekt sady Visual Studio](media/exploreide-newprojectcsharp.png "Snímek obrazovky šablony aplikace WPF v dialogovém okně Nový projekt")

::: moniker-end

::: moniker range="vs-2019"

1. Otevřete Visual Studio 2019.

1. V okně Start vyberte možnost **vytvořit nový projekt**.

   ![Zobrazit okno vytvořit nový projekt](../../get-started/media/vs-2019/start-window-create-new-project.png "Snímek obrazovky okna vytvořit nový projekt")

1. Na obrazovce **vytvořit nový projekt** vyhledejte "WPF", zvolte **aplikace WPF (.NET Framework)** a pak klikněte na tlačítko **Další**.

   ![Šablona aplikace WPF v dialogovém okně vytvořit nový projekt](media/vs-2019/exploreide-newprojectcsharp-vs2019.png "Snímek obrazovky šablony aplikace WPF v dialogovém okně vytvořit nový projekt")

1. Na další obrazovce zadejte název projektu, **HelloWPFApp**a klikněte na **vytvořit**.

   ![Pojmenujte projekt HelloWPFApp.](./media/vs-2019/exploreide-nameproject.png "Snímek obrazovky okna, kde pojmenovat projekt")

::: moniker-end

Visual Studio vytvoří projekt a řešení HelloWPFApp a **Průzkumník řešení** zobrazí různé soubory. **Návrhář WPF** zobrazuje návrhové zobrazení a zobrazení XAML souboru *MainWindow. XAML* v rozděleném zobrazení. Posunutí příčky můžete zobrazit více nebo méně z obou zobrazení. Můžete zvolit, zda chcete zobrazit pouze vizuální zobrazení nebo pouze zobrazení XAML.

![Projekt a řešení WPF v integrovaném vývojovém prostředí](media/exploreide-wpfproject-cs.png "Snímek obrazovky s projektem a řešením WPF v integrovaném vývojovém prostředí")

> [!NOTE]
> Další informace o jazyce XAML (eXtensible Application Markup Language) naleznete na stránce [Přehled XAML pro WPF](/dotnet/framework/wpf/advanced/xaml-overview-wpf) .

Poté, co jste projekt vytvořili, jej můžete upravit. Provedete to tak, že v nabídce **zobrazení** kliknete na **okno Vlastnosti** nebo stisknete **F4**. Pak můžete zobrazit a změnit možnosti položek projektu, ovládacích prvků a dalších položek v aplikaci.

   ![Okno Vlastnosti](../media/exploreide-hellowpfappfiles.png "Snímek obrazovky okno Vlastnosti s názvy aplikací WPF souborů")   

### <a name="change-the-name-of-mainwindowxaml"></a>Změna názvu souboru MainWindow. XAML

Pojďme dát MainWindow konkrétnější název.

1. V **Průzkumník řešení**vyberte *MainWindow. XAML*. Měli byste vidět okno **vlastnosti** , ale pokud ne, zvolte nabídku **zobrazení** a poté položku **okna vlastnosti** . (Nebo stiskněte **F4**.)

1. Změňte vlastnost **název souboru** na `Greetings.xaml`.

     ![Okno Vlastnosti se zvýrazněným názvem souboru](../media/exploreide-filenameinpropertieswindow.png "Snímek obrazovky okno Vlastnosti se zvýrazněným názvem souboru")

     **Průzkumník řešení** ukazuje, že název souboru je nyní Greetings *. XAML*a vnořený soubor kódu se nyní nazývá *Greetings.XAML.cs*. Tento soubor kódu je vnořený pod uzlem souboru *. XAML* , aby se zobrazily vzájemně propojené.

     ![Okno okno Vlastnosti a Průzkumník řešení s názvem souboru s pozdravem](../media/exploreide-greetingsfilename.png "Snímek obrazovky okna okno Vlastnosti a Průzkumník řešení s názvem souboru s pozdravem")     

## <a name="design-the-user-interface-ui"></a>Návrh uživatelského rozhraní (UI)

Do této aplikace přidáme tři typy ovládacích prvků: <xref:System.Windows.Controls.TextBlock> ovládací prvek, dva <xref:System.Windows.Controls.RadioButton> ovládací prvky a <xref:System.Windows.Controls.Button> ovládací prvek.

### <a name="add-a-textblock-control"></a>Přidání ovládacího prvku TextBlock

1. Zadáním **CTRL**+**Q** aktivujte vyhledávací pole a zadejte **sadu nástrojů**. V seznamu výsledků vyberte možnost **zobrazit > sada nástrojů** .

1. V **sadě nástrojů**rozbalte uzel **běžné ovládací prvky WPF** pro zobrazení ovládacího prvku TextBlock.

     ![Sada nástrojů se zvýrazněným ovládacím prvkem TextBlock](../media/exploreide-textblocktoolbox.png "Snímek obrazovky okna panelu nástrojů se zvýrazněným ovládacím prvkem TextBlock")

1. Přidejte ovládací prvek TextBlock do návrhové plochy tak, že vyberete položku **TextBlock** a přetáhnete ji do okna na návrhové ploše. Vycentrovat ovládací prvek v horní části okna.

    Okno aplikace by mělo vypadat jako na následujícím obrázku:

    ![TextBlock ovládacího prvku na formuláři Greetings](../media/exploreide-greetingswithtextblockonly.png "Snímek obrazovky ovládacího prvku TextBlock na formuláři Greetings")

   Značka XAML by měla vypadat podobně jako v následujícím příkladu:

    ```xaml
    <Grid>
        <TextBlock HorizontalAlignment="Left" Margin="387,60,0,0" TextWrapping="Wrap" Text="TextBlock" VerticalAlignment="Top"/>
    </Grid>
    ```

### <a name="customize-the-text-in-the-text-block"></a>Přizpůsobení textu v textovém bloku

1. V zobrazení XAML vyhledejte značku pro **TextBlock** a změňte atribut **text** z `TextBox` na`Select a message option and then choose the Display button.`

   Značka XAML by měla vypadat podobně jako v následujícím příkladu:

   ```xaml
   <Grid>
       <TextBlock HorizontalAlignment="Left" Margin="387,60,0,0" TextWrapping="Wrap" Text="Select a message option and then choose the Display button." VerticalAlignment="Top"/>
   </Grid>
   ```

1. Vycentrovat TextBlock znovu, pokud chcete, a potom změny uložte stisknutím **kláves CTRL + S** nebo pomocí položky nabídky **soubor** .

Dále do formuláře přidejte dva ovládací prvky [RadioButton](/dotnet/framework/wpf/controls/radiobutton) .

### <a name="add-radio-buttons"></a>Přidat přepínače

1. V **sadě nástrojů**Najděte ovládací prvek **RadioButton** .

     ![Okno panelu nástrojů s vybraným ovládacím prvkem RadioButton](../media/exploreide-radiobuttontoolbox.png "Snímek obrazovky okna panelu nástrojů s vybraným ovládacím prvkem RadioButton")

1. Přidejte dva ovládací prvky RadioButton na návrhovou plochu tak, že vyberete položku **RadioButton** a přetáhnete ji do okna na návrhové ploše. Přesuňte tlačítka (tak, že je vyberete a použijete klávesy se šipkami), aby se tlačítka zobrazovala vedle sebe pod ovládacím prvkem TextBlock.

   Okno aplikace by mělo vypadat takto:

   ![Formulář s pozdravem s TextBlock a dvěma přepínači](../media/exploreide-greetingswithradiobuttons.png "Snímek formuláře s pozdravem s TextBlock a dvěma přepínači")

1. V okně **vlastnosti** levého ovládacího prvku RadioButton změňte vlastnost **Name** (vlastnost v horní části okna **vlastnosti** ) na `HelloButton`.

    ![Okno vlastností RadioButton](../media/exploreide-buttonproperties.png "Snímek obrazovky okna vlastností RadioButton")

1. V okně **vlastnosti** pravého ovládacího prvku RadioButton změňte vlastnost **Name** na `GoodbyeButton`a uložte provedené změny.

Dále přidáte zobrazený text pro každý ovládací prvek RadioButton. Následující postup aktualizuje vlastnost **obsah** ovládacího prvku RadioButton.

### <a name="add-display-text-for-each-radio-button"></a>Přidat text zobrazení pro každý přepínač

1. Na návrhové ploše otevřete místní nabídku pro HelloButton tak, že stisknete pravé tlačítko myši na HelloButton, zvolíte **Upravit text**a pak zadáte `Hello`.

1. Otevřete místní nabídku pro GoodbyeButton tak, že stisknete pravé tlačítko myši na GoodbyeButton, vyberete **Upravit text**a pak zadáte `Goodbye`.

   Kód XAML by teď měl vypadat podobně jako v následujícím příkladu:

   ```xaml
   <Grid>
        <TextBlock HorizontalAlignment="Left" Margin="252,47,0,0" TextWrapping="Wrap" Text="Select a message option and then choose the Display button." VerticalAlignment="Top"/>
        <RadioButton x:Name="HelloButton" Content="Hello" HorizontalAlignment="Left" Margin="297,161,0,0" VerticalAlignment="Top"/>
        <RadioButton x:Name="GoodbyeButton" Content="Goodbye" HorizontalAlignment="Left" Margin="488,161,0,0" VerticalAlignment="Top"/>
   </Grid>
   ```

### <a name="set-a-radio-button-to-be-checked-by-default"></a>Nastaví přepínač pro kontrolu ve výchozím nastavení.

V tomto kroku nastavíme HelloButton, aby se kontrolovaly ve výchozím nastavení, takže se vždycky vybrala jedna z těchto dvou přepínačů.

1. V zobrazení XAML vyhledejte značku pro HelloButton.

1. Přidejte atribut -Checked a nastavte jej na **hodnotu true**. Konkrétně přidejte `IsChecked="True"`.

   Kód XAML by teď měl vypadat podobně jako v následujícím příkladu:

   ```xaml
   <Grid>
        <TextBlock HorizontalAlignment="Left" Margin="252,47,0,0" TextWrapping="Wrap" Text="Select a message option and then choose the Display button." VerticalAlignment="Top"/>
        <RadioButton x:Name="HelloButton" Content="Hello" IsChecked="True" HorizontalAlignment="Left" Margin="297,161,0,0" VerticalAlignment="Top"/>
        <RadioButton x:Name="GoodbyeButton" Content="Goodbye" HorizontalAlignment="Left" Margin="488,161,0,0" VerticalAlignment="Top"/>
   </Grid>
   ```

Konečný prvek uživatelského rozhraní, který přidáte, je ovládací prvek [tlačítko](/dotnet/framework/wpf/controls/button) .

### <a name="add-the-button-control"></a>Přidání ovládacího prvku tlačítko

1. V sadě **nástrojů**vyhledejte ovládací prvek **tlačítko** a poté jej přidejte do návrhové plochy v ovládacích prvcích RadioButton přetažením do formuláře v zobrazení Návrh.

1. V zobrazení XAML změňte hodnotu **obsahu** pro ovládací prvek tlačítko z `Content="Button"` na `Content="Display"`a poté změny uložte.

     Okno aplikace by mělo vypadat jako na následujícím obrázku.

     ![Formulář s pozdravem s popisky ovládacích prvků](media/exploreide-greetingswithcontrollabels-cs.png "Snímek formuláře s pozdravy s popisky ovládacích prvků")

   Kód XAML by teď měl vypadat podobně jako v následujícím příkladu:

   ```xaml
   <Grid>
        <TextBlock HorizontalAlignment="Left" Margin="252,47,0,0" TextWrapping="Wrap" Text="Select a message option and then choose the Display button." VerticalAlignment="Top"/>
        <RadioButton x:Name="HelloButton" Content="Hello" IsChecked="True" HorizontalAlignment="Left" Margin="297,161,0,0" VerticalAlignment="Top"/>
        <RadioButton x:Name="GoodbyeButton" Content="Goodbye" HorizontalAlignment="Left" Margin="488,161,0,0" VerticalAlignment="Top"/>
        <Button Content="Display" HorizontalAlignment="Left" Margin="377,270,0,0" VerticalAlignment="Top" Width="75"/>
   </Grid>
   ```

### <a name="add-code-to-the-display-button"></a>Přidání kódu k tlačítku zobrazit

Po spuštění této aplikace se zobrazí okno se zprávou, když uživatel zvolí přepínač a pak zvolí tlačítko pro **zobrazení** . Objeví se jedno okno se zprávou pro Hello a druhé se zprávou pro Goodbye. Pro vytvoření tohoto chování přidáte kód do `Button_Click` události v *Greetings.XAML.cs*.

1. Na návrhové ploše poklikejte na tlačítko **Zobrazit** .

     *Greetings.XAML.cs* se otevře s kurzorem v `Button_Click` události.

    ```csharp
    private void Button_Click_1(object sender, RoutedEventArgs e)
    {

    }
    ```

1. Zadejte následující kód:

    ```csharp
    if (HelloButton.IsChecked == true)
    {
         MessageBox.Show("Hello.");
    }
    else if (GoodbyeButton.IsChecked == true)
    {
        MessageBox.Show("Goodbye.");
    }
    ```

1. Uložte aplikaci.

## <a name="debug-and-test-the-application"></a>Ladění a testování aplikace

V dalším kroku aplikaci provedete tak, aby hledala chyby a otestovali, že se obě okna se zprávou zobrazují správně. V následujících pokynech se dozvíte, jak sestavit a spustit ladicí program, ale později si můžete přečíst [sestavení aplikace WPF (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf) a [ladění WPF](../../debugger/debugging-wpf.md) pro další informace.

### <a name="find-and-fix-errors"></a>Vyhledání a oprava chyb

V tomto kroku zjistíte chybu, kterou jsme dříve způsobili změnou názvu souboru *MainWindow. XAML* .

#### <a name="start-debugging-and-find-the-error"></a>Spustit ladění a najít chybu

1. Spusťte ladicí program stisknutím klávesy **F5** nebo výběrem možnosti **ladění**a potom **Spusťte ladění**.

   Zobrazí se okno **režim přerušení** a okno **výstup** indikuje, že došlo k IOException: Nelze najít prostředek ' MainWindow. XAML '.

   ![Zpráva IOException](../media/exploreide-ioexception.png "Snímek obrazovky IOException zprávy")

1. Ukončete ladicí program kliknutím na **ladění** > **Zastavit ladění**.

Na začátku tohoto kurzu jsme přejmenovali *MainWindow.* XAML na *Greetings. XAML* , ale kód pořád odkazuje na *MainWindow. XAML* jako spouštěcí identifikátor URI pro aplikaci, takže projekt nejde spustit.

#### <a name="specify-greetingsxaml-as-the-startup-uri"></a>Jako spouštěcí identifikátor URI zadejte Greetings. XAML.

1. V **Průzkumník řešení**otevřete soubor *App. XAML* .

1. Změňte `StartupUri="MainWindow.xaml"` na`StartupUri="Greetings.xaml"`a pak změny uložte.

Znovu spusťte ladicí program (stiskněte klávesu **F5**). Měli byste vidět okno **Greetings** aplikace. Nyní zavřete okno aplikace a zastavte ladění.

### <a name="debug-with-breakpoints"></a>Ladění pomocí zarážek

Můžete otestovat kód během ladění přidáním některých zarážek. Zarážky > můžete přidat kliknutím na levý okraj editoru vedle řádku kódu, kde chcete, aby došlo k přerušení, nebo stisknutím klávesy **F9**.

#### <a name="add-breakpoints"></a>Přidat zarážky

1. Otevřete *Greetings.XAML.cs*a vyberte následující řádek:`MessageBox.Show("Hello.")`

1. Přidejte zarážku z nabídky tak, že vyberete **ladění**a potom **přepnete zarážku**.

     Na levém okraji okna editoru se vedle řádku kódu zobrazí červený kruh.

1. Vyberte následující řádek: `MessageBox.Show("Goodbye.")`.

1. Stisknutím klávesy **F9** přidejte zarážku a stisknutím klávesy **F5** spusťte ladění.

1. V okně **Greetings** vyberte přepínač **Hello** a pak klikněte na tlačítko **Zobrazit** .

    Řádek `MessageBox.Show("Hello.")` je zvýrazněn žlutě. V dolní části rozhraní IDE jsou okna Automatické hodnoty, místní hodnoty a kukátka ukotvena na levé straně a zásobník volání, zarážky, nastavení výjimek, příkaz, okamžité a výstupní okna jsou ukotveny společně na pravé straně.

    ![Zarážka v ladicím programu](media/exploreide-debugbreakpoint.png "Snímek obrazovky se zarážkou v ladicím programu")

1. Na panelu nabídek vyberte možnost **ladit** > **Krok ven**.

     Aplikace bude pokračovat v provádění a zobrazí se okno se zprávou se slovem "Hello".

1. Kliknutím na tlačítko **OK** v okně se zprávou ho zavřete.

1. V okně **Greetings** vyberte přepínač rozdálení a pak klikněte na tlačítko **Zobrazit** .

     Řádek `MessageBox.Show("Goodbye.")` je zvýrazněn žlutě.

1. Pokračujte v ladění kliknutím na klávesu **F5** . Když se zobrazí okno se zprávou, zavřete ho kliknutím na tlačítko **OK** v okně se zprávou.

1. Zavřete okno aplikace a zastavte ladění.

1. Na panelu nabídek vyberte možnost **ladit** > **Zakázat všechny zarážky**.

### <a name="build-a-release-version-of-the-application"></a>Sestavení verze pro vydání aplikace

Teď, když jste ověřili, že vše funguje, si můžete připravit sestavení pro vydání aplikace.

1. V hlavní nabídce vyberte **sestavit** > **Vyčistit řešení** a odstraňte mezilehlé soubory a výstupní soubory, které byly vytvořeny během předchozích sestavení. To není nutné, ale čistí výstupy sestavení ladění.

1. Změňte konfiguraci sestavení pro HelloWPFApp z **Debug** na **release** pomocí ovládacího prvku rozevíracího seznamu na panelu nástrojů (aktuálně říká "ladit").

1. Sestavte řešení kliknutím na **sestavit** > sestavení**řešení**.

Blahopřejeme k dokončení tohoto kurzu! Můžete najít soubor *. exe* , který jste vytvořili v rámci vašeho řešení a adresáře projektu ( *. ..\HelloWPFApp\HelloWPFApp\bin\Release*).

## <a name="next-steps"></a>Další postup

Blahopřejeme k dokončení tohoto kurzu! Pokud se chcete dozvědět ještě víc, pokračujte v následujících kurzech.

> [!div class="nextstepaction"]
> [Pokračovat s dalšími kurzy WPF](/dotnet/framework/wpf/getting-started/wpf-walkthroughs/)

## <a name="see-also"></a>Viz také:

- [Tipy pro vyšší produktivitu](../../ide/productivity-features.md)
