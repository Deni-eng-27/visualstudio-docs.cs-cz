---
title: Vytvoření Windows Forms aplikace v sadě Visual Studio s jazykem Visual Basic | Microsoft Docs
description: Zjistěte, jak vytvořit aplikaci Windows Forms v sadě Visual Studio s jazykem Visual Basic, krok za krokem.
ms.custom: ''
ms.date: 12/04/2017
ms.technology:
- vs-acquisition
ms.topic: conceptual
ms.devlang: vb
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- vb
ms.workload:
- multiple
ms.openlocfilehash: d51c92307a7ac266da042d33a7669a3ac629b21e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="create-a-windows-forms-app-in-visual-studio-with-visual-basic"></a>Vytvoření Windows Forms aplikace v sadě Visual Studio s jazykem Visual Basic
Tento stručný úvod v sadě Visual Studio integrované vývojové prostředí (IDE) vytvoříte jednoduchou aplikaci jazyka Visual Basic, která má založené na Windows uživatelské rozhraní (UI).

Pokud jste ještě nenainstalovali Visual Studio, přejděte k [Visual Studio stáhne](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) stránky instalaci zdarma.

## <a name="create-a-project"></a>Vytvoření projektu
Nejdřív vytvoříte projekt aplikace Visual Basic. Typ projektu se dodává s všechny soubory šablony, které budete potřebovat, než jste přidali i nic.  

1. Otevřete Visual Studio 2017.  

2. V horní nabídce vyberte příkaz **soubor** > **nový** > **projektu...** .  

3. V **nový projekt** dialogové okno v levém podokně rozbalte **jazyka Visual Basic**a potom zvolte **Windows Classic Desktop**. V prostředním podokně vyberte **aplikace pro Windows Forms (rozhraní .NET Framework)**. Potom zadejte název souboru `HelloWorld`.  

     Pokud nevidíte **aplikace pro Windows Forms (rozhraní .NET Framework)** projektu šablony, zrušte mimo **nový projekt** dialogové okno a z panelu horní nabídce zvolte **nástroje**  >  **Získat funkcí a nástrojů pro...** . Spustí instalační program Visual Studio. Vyberte **vývoj aplikací .NET** zatížení, zvolte **upravit**.  

     ![.NET core zatížení v instalačním programu Visual Studio](../ide/media/install-dot-net-desktop-env.png)  

## <a name="create-the-application"></a>Vytvoření aplikace
Po výběru vaše šablona projektu jazyka Visual Basic a název souboru, Visual Studio otevře formuláře za vás. Formulář je uživatelské rozhraní systému Windows. Vytvoříme aplikaci "Hello World" přidáním ovládacích prvků formuláře a potom budete spustí aplikaci.   

### <a name="add-a-button-to-the-form"></a>Přidání tlačítka do formuláře  

1. Klikněte na tlačítko **sada nástrojů** a otevřete okno rozevírací sady nástrojů.

     ![Klikněte na panelu nástrojů, otevřete okno sady nástrojů](../ide/media/vb-toolbox-toolwindow.png)  

     (Pokud se nezobrazí **sada nástrojů** rozevírací možnost, který můžete otevřít z řádku nabídek. Chcete-li to provést, klikněte na tlačítko **zobrazení** > **sada nástrojů**. Také můžete stisknout klávesu **Ctrl**+**Alt**+**X**.)

2. Klikněte na tlačítko **Pin** ikonu ukotvení **sada nástrojů** okno.

     ![Kliknutím na ikonu Připnutí, chcete-li Připnout okno sady nástrojů a integrovaného vývojového prostředí](../ide/media/vb-pin-the-toolbox-window.png)  
3. Klikněte **tlačítko** řízení a přetáhněte ji na formuláři.

     ![Přidání tlačítka do formuláře](../ide/media/vb-add-a-button-to-form1.png)

4. V **vzhled** části **vlastnosti** zadejte `Click this`a potom stiskněte klávesu **Enter**.

     ![Přidat text pro tlačítko ve formuláři](../ide/media/vb-button-control-text.png)  

     (Pokud se nezobrazí **vlastnosti** okna, který můžete otevřít z řádku nabídek. Chcete-li to provést, klikněte na tlačítko **zobrazení** > **vlastnosti – okno**. Také můžete stisknout klávesu **F4**.)

5. V **návrhu** části **vlastnosti** okno, změňte název z **Button1** k `btnClickThis`a potom stiskněte klávesu **Enter**.

     ![Přidání funkce do tlačítko ve formuláři](../ide/media/vb-button-control-function.png)

### <a name="add-a-label-to-the-form"></a>Přidání popisku do formuláře
Teď, když jsme přidali ovládacího prvku tlačítko pro vytvoření akce, přidejme ovládací prvek popisek odeslat text.

1. Vyberte **popisek** řídit z **sada nástrojů** okně a přetáhněte ji na formuláři a umístěte jej pod **klikněte na toto** tlačítko.

2. V **návrhu** části **vlastnosti** okno, změňte název z **Label1** k `lblHelloWorld`a potom stiskněte klávesu **Enter**.

### <a name="add-code-to-the-form"></a>Přidejte kód pro formulář

1. V **Form1.vb &#91;návrhu&#93;**  okno, dvakrát klikněte na **klikněte na toto** tlačítko Otevřít **Form1.vb** okno.

      (Alternativně můžete rozšířit **Form1.vb** v **Průzkumníku řešení** okna a pak klikněte na tlačítko **Form1**.)

2. V **Form1.vb** okno, v rozmezí **privátní dílčí** řádku a **End Sub** řádek, zadejte nebo vložte `lblHelloWorld.Text = "Hello World!"`.

     ![Přidejte kód pro formulář formuláře](../ide/media/vb-add-code-to-the-form.png)

## <a name="run-the-application"></a>Spuštění aplikace
1. Klikněte **spustit** tlačítko ke spuštění aplikace.

     ![Klikněte na tlačítko Start, ladit a spuštění aplikace](../ide/media/vb-click-start-hello-world.png)

   Stane se několik věcí. V prostředí Visual Studio IDE **diagnostické nástroje** otevře se okno a **výstup** otevře se okno, příliš. Ale mimo prostředí IDE **Form1** zobrazí se dialogové okno. Bude zahrnovat vaše **klikněte na tlačítko to** tlačítko a text, který je uveden **Label1**.

2. Klikněte na tlačítko **klikněte na toto** v tlačítko **Form1** dialogové okno. Všimněte si, že **Label1** text změní na **Hello, World!**.

    ![Dialogové okno Form1, která zahrnuje Label1 text ](../ide/media/vb-form1-dialog-hello-world.png)

Blahopřejeme k dokončení tento rychlý start! Věříme, že jste se dozvěděli, chvíli o jazyka Visual Basic a Visual Studio IDE. Pokud chcete pustíte hlubší, pokračujte prosím se v kurzu **kurzy** části obsahu.  

## <a name="see-also"></a>Viz také   
* [Rychlý úvod: Vytvoření aplikace konzoly v sadě Visual Studio s jazykem Visual Basic](quickstart-visual-basic-console.md)
* [Další informace o jazyka Visual Basic IntelliSense](visual-basic-specific-intellisense.md)  
