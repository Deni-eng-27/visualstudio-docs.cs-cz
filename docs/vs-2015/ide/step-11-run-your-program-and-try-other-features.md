---
title: 'Krok 11: Spusťte program a vyzkoušejte další funkce | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 656614d0-4fe7-4a67-8edc-c10919377d09
caps.latest.revision: 14
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: bff0467cfe9447b1cc7814d471f56ab323bb853d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "75851581"
---
# <a name="step-11-run-your-program-and-try-other-features"></a>Krok 11: Spusťte svůj program a vyzkoušejte další funkce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Program je dokončen a připraven ke spuštění. Můžete spustit program a nastavit barvu pozadí ovládacího prvku PictureBox. Chcete-li získat další informace, zkuste program vylepšit změnou barvy formuláře, přizpůsobením tlačítek a zaškrtávacím políčkem a změnou vlastností formuláře.

 ![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo") Verzi videa tohoto tématu najdete v tématu [kurz 1: vytvoření prohlížeče obrázků v Visual Basic-video 5](https://msdn.microsoft.com/vbasic/gg315356.aspx) nebo v [kurzu 1: vytvoření prohlížeče obrázků v jazyce C# – video 5](https://msdn.microsoft.com/vcsharp/gg278413.aspx). Tato videa používají starší verzi sady Visual Studio, takže existují mírné rozdíly v některých příkazech nabídky a dalších prvcích uživatelského rozhraní. Koncepty a postupy však fungují podobně v aktuální verzi sady Visual Studio.

### <a name="to-run-your-program-and-set-the-background-color"></a>Spuštění programu a nastavení barvy pozadí

1. Vyberte F5 nebo na panelu nabídek vyberte **ladit**, **Spustit ladění**.

2. Než otevřete obrázek, klikněte na tlačítko **nastavit barvu pozadí** . Otevře se dialogové okno **Barva** .

     ![Dialogové okno barvy](../ide/media/express-colordialog.png "Express_ColorDialog") Dialogové okno barvy

3. Vyberte barvu pro nastavení barvy pozadí ovládacího prvku PictureBox. Prohlédněte si úzce na `backgroundButton_Click()` metodě, abyste porozuměli tomu, jak to funguje.

    > [!NOTE]
    > Obrázek můžete načíst z Internetu vložením jeho adresy URL do dialogového okna **otevřít soubor** . Zkuste najít obrázek s průhledným pozadím, aby se zobrazila barva pozadí.

4. Klikněte na tlačítko **Vymazat obrázek** , abyste se ujistili, že se vymaže. Pak ukončete program kliknutím na tlačítko **Zavřít** .

### <a name="to-try-other-features"></a>Vyzkoušení dalších funkcí

- Změňte barvu formuláře a tlačítek pomocí vlastnosti **BackColor** .

- Přizpůsobte si tlačítka a zaškrtávací políčko pomocí vlastností **Font** a **ForeColor** .

- Změňte vlastnosti **FormBorderStyle** a **ovládací nabídka** formuláře.

- Použijte vlastnosti **AcceptButton** a **CancelButton** vašeho formuláře, aby se tlačítka automaticky brala, když uživatel zvolí klávesu ENTER nebo ESC. Nastavit program tak, aby otevřel dialogové okno **otevřít soubor** , když uživatel zvolí ENTER a zavřít pole, když uživatel zvolí klávesu ESC.

### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Další informace o programování v aplikaci Visual Studio naleznete v tématu [koncepty programování](https://msdn.microsoft.com/library/65c12cca-af4f-4017-886e-2dbc00a189d6).

- Další informace o Visual Basic najdete v tématu [vývoj aplikací pomocí Visual Basic](https://msdn.microsoft.com/library/1e1c0c81-6d95-4167-a98b-44b1efb6d25f).

- Další informace o jazyce Visual C# naleznete v tématu [Úvod do jazyka C# a .NET Framework](https://msdn.microsoft.com/library/0a2dff4e-cd84-42ff-8141-e89889b24081).

- Pokud chcete přejít k dalšímu kurzu, přečtěte si článek [kurz 2: vytvoření časovaného matematického kvízu](../ide/tutorial-2-create-a-timed-math-quiz.md).

- Chcete-li se vrátit k předchozímu kroku kurzu, přečtěte si část [Krok 10: psaní kódu pro další tlačítka a zaškrtávací políčko](../ide/step-10-write-code-for-additional-buttons-and-a-check-box.md).
