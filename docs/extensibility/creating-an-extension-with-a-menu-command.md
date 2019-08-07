---
title: Vytvoření rozšíření pomocí příkazu nabídky | Microsoft Docs
ms.date: 3/16/2019
ms.topic: conceptual
helpviewer_keywords:
- write a vspackage
- vspackage
- tutorials
- visual studio package
ms.assetid: f97104c8-2bcb-45c7-a3c9-85abeda8df98
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7cb82a2a5e02b2e109bb5b27ec54d1a2cd965901
ms.sourcegitcommit: 90c3187d804ad7544367829d07ed4b47d3f8a72d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2019
ms.locfileid: "68821536"
---
# <a name="create-an-extension-with-a-menu-command"></a>Vytvoření rozšíření pomocí příkazu nabídky

Tento návod ukazuje, jak vytvořit rozšíření pomocí příkazu nabídky, který spustí Poznámkový blok.

## <a name="prerequisites"></a>Požadavky

Spouští se v sadě Visual Studio 2015, nenainstalujete sadu Visual Studio SDK ze služby Stažení softwaru. Je zahrnut jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).

## <a name="create-a-menu-command"></a>Vytvoření příkazu nabídky

1. Vytvořte projekt VSIX s názvem **FirstMenuCommand**. Šablonu projektu VSIX můžete najít v dialogovém okně **Nový projekt** hledáním "VSIX".

2. Po otevření projektu přidejte šablonu vlastní položky příkazu s názvem **FirstCommand**. V **Průzkumník řešení**klikněte pravým tlačítkem myši na uzel projektu a vyberte možnost **Přidat** > **novou položku**. V dialogovém okně **Přidat novou položku** přejdete na **rozšiřitelnost** **vizuálů C#**   > a vyberte **vlastní příkaz**. V poli **název** v dolní části okna změňte název souboru příkazů na *FirstCommand.cs*.

3. Sestavte projekt a spusťte ladění.

    Zobrazí se experimentální instance aplikace Visual Studio. Další informace o experimentální instanci naleznete v [experimentální instanci](../extensibility/the-experimental-instance.md).

::: moniker range="vs-2017"

4. V experimentální instanci otevřete okno**rozšíření a aktualizace** **nástrojů** > . Tady byste měli vidět rozšíření **FirstMenuCommand** . (Pokud v pracovní instanci sady Visual Studio otevřete **rozšíření a aktualizace** , neuvidíte **FirstMenuCommand**).

::: moniker-end

::: moniker range=">=vs-2019"

4. V experimentální instanci otevřete okno **rozšíření** > **Spravovat rozšíření** . Tady byste měli vidět rozšíření **FirstMenuCommand** . (Pokud otevřete **Spravovat rozšíření** v pracovní instanci sady Visual Studio, neuvidíte **FirstMenuCommand**).

::: moniker-end

Nyní přejděte do nabídky **nástroje** v experimentální instanci. Měl by se zobrazit příkaz **Invoke FirstCommand** . V tomto okamžiku příkaz zobrazí okno se zprávou, které říká **FirstCommandPackage uvnitř FirstMenuCommand. FirstCommand. MenuItemCallback ()** . V další části se dozvíte, jak ve skutečnosti spustit program Poznámkový blok z tohoto příkazu.

## <a name="change-the-menu-command-handler"></a>Změna obslužné rutiny příkazu nabídky

Nyní aktualizujeme obslužnou rutinu příkazu na spustit Poznámkový blok.

1. Zastavte ladění a vraťte se do funkční instance sady Visual Studio. Otevřete soubor *FirstCommand.cs* a přidejte následující příkaz using:

    ```csharp
    using System.Diagnostics;
    ```

2. Vyhledejte privátní konstruktor FirstCommand. V tomto případě se příkaz připojí ke službě Command Service a zadává se obslužná rutina příkazu. Změňte název obslužné rutiny příkazu na StartNotepad následujícím způsobem:

    ```csharp
    private FirstCommand(AsyncPackage package, OleMenuCommandService commandService)
    {
        this.package = package ?? throw new ArgumentNullException(nameof(package));
        commandService = commandService ?? throw new ArgumentNullException(nameof(commandService));

        CommandID menuCommandID = new CommandID(CommandSet, CommandId);
        // Change to StartNotepad handler.
        MenuCommand menuItem = new MenuCommand(this.StartNotepad, menuCommandID);
        commandService.AddCommand(menuItem);
    }
    ```

3. Odeberte metodu a přidejte metodu, která bude jednoduše spouštět program Poznámkový blok: `StartNotepad` `MenuItemCallback`

    ```csharp
    private void StartNotepad(object sender, EventArgs e)
    {
        Process proc = new Process();
        proc.StartInfo.FileName = "notepad.exe";
        proc.Start();
    }
    ```

4. Nyní to vyzkoušejte. Když spustíte ladění projektu a kliknete na **nástroje** > **vyvolání FirstCommand**, měla by se zobrazit instance poznámkového bloku.

    Můžete použít instanci <xref:System.Diagnostics.Process> třídy pro spuštění libovolného spustitelného souboru, nikoli pouze Poznámkový blok. Zkuste to třeba `calc.exe`s.

## <a name="clean-up-the-experimental-environment"></a>Vyčištění experimentálního prostředí

Pokud vyvíjíte více rozšíření nebo pouze prozkoumáte výsledky s různými verzemi kódu rozšíření, může vaše experimentální prostředí přestat pracovat způsobem, který by měl. V takovém případě byste měli spustit skript pro resetování. Nazývá se to **resetování experimentální instance sady Visual Studio**a dodává se jako součást sady Visual Studio SDK. Tento skript odebere všechny odkazy na vaše rozšíření z experimentálního prostředí, takže můžete začít od začátku.

Tento skript se dá získat jedním ze dvou způsobů:

1. Z plochy Najděte **obnovení experimentální instance sady Visual Studio**.

2. Z příkazového řádku spusťte následující příkaz:

    ```xml
    <VSSDK installation>\VisualStudioIntegration\Tools\Bin\CreateExpInstance.exe /Reset /VSInstance=<version> /RootSuffix=Exp && PAUSE

    ```

## <a name="deploy-your-extension"></a>Nasazení rozšíření

Teď, když máte vaše rozšíření nástroje spuštěné požadovaným způsobem, je čas si představit, jak ho sdílet s vašimi přáteli a kolegy. To je snadné, pokud máte nainstalovanou aplikaci Visual Studio 2015. Vše, co je třeba udělat, je odeslat do souboru *. vsix* , který jste vytvořili. (Nezapomeňte ho sestavit v režimu vydání.)

Soubor *. vsix* pro toto rozšíření najdete v adresáři *FirstMenuCommand* bin. Konkrétně za předpokladu, že jste vytvořili konfiguraci vydané verze, bude v:

*\<Adresář kódu > \FirstMenuCommand\FirstMenuCommand\bin\Release\ FirstMenuCommand. vsix*

Chcete-li nainstalovat rozšíření, váš přítel potřebuje zavřít všechny otevřené instance aplikace Visual Studio a potom poklikejte na soubor *. vsix* , který spustí **instalační program VSIX**. Soubory jsou zkopírovány do *%localappdata%\Microsoft\VisualStudio\<verze > adresáři \Extensions* .

Když váš přítel znovu vyvolá Visual Studio, nalezne rozšíření FirstMenuCommand v části**rozšíření a aktualizace** **nástrojů** > . Můžou přejít na **rozšíření a aktualizace** pro odinstalaci nebo zakázání rozšíření.

## <a name="next-steps"></a>Další postup

Tento názorný postup vám ukázal jenom malou část toho, co můžete dělat s rozšířením sady Visual Studio. Tady je krátký seznam dalších (rozumně jednoduchých) věcí, které můžete dělat s rozšířeními sady Visual Studio:

1. Pomocí jednoduchého příkazu nabídky můžete udělat spoustu dalších věcí:

   1. Přidat vlastní ikonu: [Přidat ikony do příkazů nabídky](../extensibility/adding-icons-to-menu-commands.md)

   2. Změňte text příkazu nabídky: [Změna textu příkazu nabídky](../extensibility/changing-the-text-of-a-menu-command.md)

   3. Přidat zástupce nabídky do příkazu: [Vázání klávesových zkratek k položkám nabídky](../extensibility/binding-keyboard-shortcuts-to-menu-items.md)

2. Přidejte různé druhy příkazů, nabídek a panelů nástrojů: [Rozšiřování nabídek a příkazů](../extensibility/extending-menus-and-commands.md)

3. Přidání oken nástrojů a rozšiřování integrovaných oken nástrojů sady Visual Studio: [Rozšiřování a přizpůsobení oken nástrojů](../extensibility/extending-and-customizing-tool-windows.md)

4. Přidejte IntelliSense, návrhy kódu a další funkce do existujících editorů kódu: [Rozšiřování editoru a jazykových služeb](../extensibility/extending-the-editor-and-language-services.md)

5. Přidejte možnosti a stránky vlastností a uživatelská nastavení do svého rozšíření: [Rozšiřování vlastností a okna vlastností](../extensibility/extending-properties-and-the-property-window.md) a [roztažení uživatelských nastavení a možností](../extensibility/extending-user-settings-and-options.md)

   Jiné druhy rozšíření vyžadují trochu více práce, jako je například vytvoření nového typu projektu ([rozšíření projektů](../extensibility/extending-projects.md)), vytvoření nového typu editoru ([Vytvoření vlastních editorů a návrhářů](../extensibility/creating-custom-editors-and-designers.md)) nebo implementace rozšíření v izolovaném prostředí: [Izolované prostředí sady Visual Studio](https://visualstudio.microsoft.com/vs/older-downloads/isolated-shell/)
