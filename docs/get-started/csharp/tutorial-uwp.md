---
description: Vytvoření aplikace pro UPW v sadě Visual Studio pomocí XAML aC#
titleSuffix: ''
ms.custom: seodec18, get-started
ms.date: 04/04/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: tutorial
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: e28ed348d0c994d38ef0614a12430f419b66ba71
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53871379"
---
# <a name="tutorial-create-your-first-universal-windows-platform-application-in-visual-studio-with-xaml-and-c35"></a>Kurz: Vytvoření první aplikace pro univerzální platformu Windows v sadě Visual Studio pomocí XAML a C&#35;

V tomto úvodu 5 až 10 minut do integrovaného vývojového prostředí (IDE) sady Visual Studio vytvoříte aplikaci "Hello World", který běží na všechna zařízení s Windows 10. V takovém případě budete používat šablonu projektu univerzální platformu Windows (UPW), Extensible Application Markup Language (XAML) a C# programovací jazyk.

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) stránku a nainstalovat zdarma.

## <a name="create-a-project"></a>Vytvoření projektu

Nejprve vytvořte projekt univerzální platformy Windows. Typ projektu obsahuje všechny soubory šablon, které potřebujete, než jste přidali ještě nic!

1. Otevřete Visual Studio 2017.

2. V horním řádku nabídek zvolte **Soubor** > **Nový** > **Projekt**.

3. V levém podokně **nový projekt** dialogového okna rozbalte **Visual C#** a klikněte na tlačítko **Windows Universal**. V prostředním podokně vyberte **prázdná aplikace (Universal Windows)**. Pojmenujte projekt *HelloWorld* a zvolte **OK**.

   ![Windows Universal šablonu projektu v dialogovém okně Nový projekt v integrovaném vývojovém prostředí sady Visual Studio](media/new-project-csharp-uwp-helloworld.png)

   > [!NOTE]
   > Pokud se nezobrazí **prázdná aplikace (Universal Windows)** šablony projektu, klikněte na tlačítko **otevřít instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno.<br><br>![Klikněte na odkaz otevřít instalační program Visual Studio z dialogového okna Nový projekt](../../ide/media/vb-open-visual-studio-installer-hello-world.png)<br><br>Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro univerzální platformu Windows** úlohy a klikněte na tlačítko **změnit**.<br><br>![Úlohu vývoje univerzální platformy Windows v instalačním programu sady Visual Studio](media/uwp-dev-workload.png)

4. Když **nový projekt univerzální platformy Windows** dialogového okna zvolte **OK**.

   ![Přijměte výchozí cílová verze a minimální verzi nastavení v dialogovém okně Nový projekt univerzální platformy Windows](media/new-uwp-project-target-minver-dialog.png)

   > [!NOTE]
   > Pokud je to první sady Visual Studio jste použili k vytvoření aplikace pro UPW, **nastavení** může otevřít dialogové okno. Zvolte **vývojářský režim**a klikněte na tlačítko **Ano**.<br><br>
   ![Povolení režimu pro vývojáře v dialogovém okně Nastavení UPW](media/enable-developer-mode.png)<br><br>Další balíčky režimu pro vývojáře Visual Studio nainstaluje za vás. Po dokončení instalace balíčku, zavřete **nastavení** dialogové okno.

## <a name="create-the-application"></a>Vytvoření aplikace

Je čas začít s vývojem. Budete přidejte ovládací prvek tlačítko, přidání akce pro tlačítko a pak spusťte aplikaci "Hello World", můžete zjistit, jak to vypadá.

### <a name="add-a-button-to-the-design-canvas"></a>Přidání tlačítka na plátno s návrhem

1. V **Průzkumníka řešení**, dvakrát klikněte na panel *MainPage.xaml* otevřete rozdělené zobrazení.

   ![V Průzkumníku řešení otevřete MainPage.xaml ](media/uwp-solution-explorer-MainPage-xaml.png)

   Existují dvě podokna: **Návrháře XAML**, což zahrnuje návrh plátna a **editoru XAML**, ve kterém můžete přidat nebo změnit kód.

   ![V podokně návrháře XAML v editoru XAML](media/uwp-xaml-editor.png)

2. Zvolte **nástrojů** nabídka okno nástrojů.

   ![Klikněte na panelu nástrojů otevřete okno nabídka sady nástrojů](media/uwp-toolbox.png)

   (Pokud se nezobrazí **nástrojů** možnost, lze jej otevřít z řádku nabídek. Chcete-li to provést, zvolte **zobrazení** > **nástrojů**. Také můžete stisknout klávesu **Ctrl**+**Alt**+**X**.)

3. Klikněte na tlačítko **Pin** ikonu Ukotvit okno nástrojů.

   ![Kliknutím na ikonu Připnutí, chcete-li ukotvit okno nástrojů](media/uwp-toolbox-autohide.png)

4. Klikněte na tlačítko **tlačítko** řídit a přetáhněte ji na plátno s návrhem.

   ![Klikněte na ovládací prvek tlačítko a přetáhněte ji na plátno s návrhem](media/uwp-toolbox-add-button-control.png)

   Když se podíváte na kód v **editoru XAML**, uvidíte, že tlačítko jsme tam také:

   ![Klikněte na ovládací prvek tlačítko a přetáhněte ji na plátno s návrhem](media/uwp-xaml-control-code-window.png)

### <a name="add-a-label-to-the-button"></a>Přidat popisek k tlačítku

1. V **editoru XAML**, změňte hodnotu tlačítka obsahu z "Button" na "Hello World!"

   ![Změňte hodnotu obsahu tlačítka na Hello World](media/uwp-change-button-text-in-xaml-code-window.png)

2. Všimněte si, že tlačítko v **návrháře XAML** příliš změní.

   ![Tlačítko se změní na Hello World na plátno s návrhem](media/uwp-button-text-change-in-design-canvas.png)

### <a name="add-an-event-handler"></a>Přidání obslužné rutiny událostí

"Obslužné rutiny události" zvuky složité, ale je stejně jiný název pro kód, který se volá, když určité události. V takovém případě přidá akci, která "Hello World!" tlačítko.

1. Dvakrát klikněte na tlačítko ovládacího prvku na návrhové plátno.

2. Upravit kód pro obslužnou rutinu události v *MainPage.xaml.cs*, použití modelu code-behind stránky.

   Je to, kde získat zajímavé věci. Obslužnou rutinu výchozí události vypadá takto:

   ![Obslužnou rutinu výchozí události Button_Click ](media/uwp-button-click-code.png)

   Pojďme ho změnit tak, aby vypadala takto:

    ![Obslužná rutina události Button_Click na asynchronní ](media/uwp-add-hello-world-async-code.png)

   Tady je kód zkopírovat a vložit:

   ```C#
   private async void Button_Click(object sender, RoutedEventArgs e)
         {
             MediaElement mediaElement = new MediaElement();
             var synth = new Windows.Media.SpeechSynthesis.SpeechSynthesizer();
             Windows.Media.SpeechSynthesis.SpeechSynthesisStream stream = await synth.SynthesizeTextToStreamAsync("Hello, World!");
             mediaElement.SetSource(stream, stream.ContentType);
             mediaElement.Play();
         }
   ```

#### <a name="what-did-we-just-do"></a>Co jsme změnili pouze?

Tento kód používá některá rozhraní Windows API k vytvoření objektu syntézu řeči a dá jí nějaký text říct. (Další informace o používání `SpeechSynthesis`, naleznete v tématu <xref:System.Speech.Synthesis>.)

## <a name="run-the-application"></a>Spuštění aplikace

Je čas vytvořit, nasadit a spustit aplikaci UPW "Hello World", vypadá a snaha. Tady je způsob.

1. Zvolte **místního počítače** ke spuštění aplikace.

   ![Klikněte na místním počítači spustit a ladit aplikace pro UPW](media/uwp-start-or-debug.png)

   (Alternativně můžete zvolit **ladění** > **spustit ladění** z panelu nabídek nebo stisknete klávesu **F5** ke spuštění vaší aplikace.)

2. Zobrazení vaší aplikace, které se zobrazí krátce po úvodní obrazovka zmizí. Aplikace by měla vypadat nějak takto:

   ![UPW aplikace "Hello World"](media/uwp-hello-world-app.png)

3. Klikněte na tlačítko **Hello World** tlačítko.

   Zařízení bude sdělení doslova Windows 10, "Hello, World!"

4. Pokud chcete aplikaci zavřít, klikněte na tlačítko **Zastavit ladění** tlačítko na panelu nástrojů. (Další možností je zvolit **ladění** > **Zastavit ladění** z panelu nabídek nebo stisknete klávesu **Shift**+**F5**.)

## <a name="next-steps"></a>Další kroky

Blahopřejeme k dokončení tohoto rychlého startu! Doufáme, že jste se naučili základy o UPW a integrovaném vývojovém prostředí sady Visual Studio. Další informace najdete v následujícím kurzu:

> [!div class="nextstepaction"]
> [Vytvoření uživatelského rozhraní](/windows/uwp/design/basics/xaml-basics-ui)
