---
title: Změna barev písma, velikosti textu a možností vysokého kontrastu
description: Naučte se, jak změnit barvu písma a velikost textu v aplikaci Visual Studio a jak vybrat možnosti kontrastu pro usnadnění přístupu.
ms.date: 08/20/2020
ms.topic: how-to
ms.custom: contperfq1
helpviewer_keywords:
- Visual Studio, color themes
- color themes, Visual Studio
ms.assetid: 60d91ba1-244b-4c43-847f-60b744f1352a
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 280873a2f855aa4c0d7e9951e141ca5492357b5a
ms.sourcegitcommit: de98ed7edc81383e47b87ae6e61143fbbbe7bc56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/21/2020
ms.locfileid: "88711687"
---
# <a name="how-to-change-fonts-colors-and-high-contrast-options-in-visual-studio"></a>Postupy: Změna písem, barev a možností vysokého kontrastu v aplikaci Visual Studio

Písma a barvy v aplikaci Visual Studio můžete změnit mnoha způsoby. Například můžete změnit výchozí modrý barevný motiv na tmavý motiv (označuje se také jako "tmavý režim"). A výchozí velikost písma a textu můžete změnit na jiné písmo a velikost. Pokud to nejlépe vyhovuje vašim potřebám, můžete také vybrat motiv s vysokým kontrastem.

## <a name="change-the-color-theme"></a>Změna barevného motivu

Zde je postup změny barevného motivu rámce IDE a oken nástrojů v aplikaci Visual Studio.

1. Na panelu nabídek vyberte **Tools**  >  **Možnosti**nástroje.

1. V seznamu Možnosti vyberte možnost **prostředí**  >  **Obecné**.

1. V seznamu **barevný motiv** vyberte výchozí **modrý** motiv, **světlý** motiv, **tmavý** motiv nebo **modrý (velmi kontrastní)** motiv.

   ![Snímek obrazovky dialogového okna Možnosti pro změnu barevného motivu](media/fonts-colors-theme.png "Snímek obrazovky dialogového okna Možnosti, které můžete použít ke změně barevného motivu")

    > [!NOTE]
    > Když změníte barevný motiv, text v integrovaném vývojovém prostředí vrátí výchozí nebo dříve přizpůsobenou písma a velikosti pro daný motiv.

    :::moniker range="vs-2017"

    > [!TIP]
    > Můžete vytvářet a upravovat vlastní motivy sady Visual Studio, a to tak, že nainstalujete [Editor motivů barev pro Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.VisualStudio2017ColorThemeEditor).

    :::moniker-end

    :::moniker range="vs-2019"

    > [!TIP]
    > Můžete vytvářet a upravovat vlastní motivy sady Visual Studio, a to tak, že nainstalujete [Návrháře barevných motivů sady Visual Studio](https://marketplace.visualstudio.com/items?itemName=ms-madsk.ColorThemeDesigner).

    :::moniker-end

## <a name="change-fonts-and-text-size"></a>Změna písma a velikosti textu

Můžete změnit velikost písma a textu pro všechna okna rámců a nástrojů IDE nebo pouze pro určité prvky systému Windows nebo text. Také můžete změnit písmo a velikost textu v editoru.

### <a name="to-change-the-font-and-text-size-in-the-ide"></a>Změna písma a velikosti textu v integrovaném vývojovém prostředí

1. Na panelu nabídek vyberte **Tools**  >  **Možnosti**nástroje.

1. V seznamu Možnosti vyberte možnost **Environment**  >  **písma a barvy**prostředí.

1. V seznamu **Zobrazit nastavení pro** vyberte možnost **prostředí**.

   ![Snímek obrazovky dialogového okna Možnosti pro změnu písma a barev v integrovaném vývojovém prostředí](media/fonts-colors-environment.png "Snímek obrazovky dialogového okna Možnosti pro změnu písma a barev v integrovaném vývojovém prostředí")

    > [!NOTE]
    > Chcete-li změnit písmo pouze pro okna nástrojů, v seznamu **Zobrazit nastavení pro** vyberte možnost **všechna okna textových nástrojů**.

1. Upravte možnosti **písmo** a **Velikost** pro změnu písma a velikosti textu pro rozhraní IDE.

1. Vyberte příslušnou položku v části **Zobrazit položky**a pak změňte možnosti pozadí **položky** a **pozadí položky** .

### <a name="to-change-the-font-and-text-size-in-the-editor"></a>Změna písma a velikosti textu v editoru

1. Na panelu nabídek vyberte **Tools**  >  **Možnosti**nástroje.

1. V seznamu Možnosti vyberte možnost **Environment**  >  **písma a barvy**prostředí.

1. V seznamu **Zobrazit nastavení pro** vyberte možnost **textový editor**.

   ![Snímek obrazovky dialogového okna Možnosti pro změnu písma a barev v editoru](media/fonts-colors-text-editor.png "Snímek obrazovky dialogového okna Možnosti pro změnu písma a barev v editoru")

1. Upravte možnosti **písmo** a **Velikost** pro změnu písma a velikosti textu pro Editor.

1. Vyberte příslušnou položku v části **Zobrazit položky**a pak změňte možnosti pozadí **položky** a **pozadí položky** .

Další informace najdete v tématu [Změna písma a barev pro stránku editoru](../ide/reference/how-to-change-fonts-and-colors-in-the-editor.md) .

## <a name="accessibility-options"></a>Možnosti usnadnění

Pokud máte zkušenosti s nízkou schopností, máte k dispozici možnosti barevného motivu. Pro *všechny* aplikace a uživatelské rozhraní v počítači můžete použít možnost vysokého kontrastu, případně možnost vyššího kontrastu jenom pro Visual Studio.

### <a name="use-windows-high-contrast"></a>Použít vysoký kontrast Windows

Chcete-li přepnout možnost vysoký kontrast systému Windows, použijte některý z následujících postupů:

- V systému Windows nebo v libovolné aplikaci společnosti Microsoft stiskněte klávesy **levý ALT** + **levý SHIFT** + **Print Screen** .

- V systému Windows vyberte možnost **Spustit**  >  **Nastavení**  >  **usnadnění přístupu**  >  **vysoký kontrast**.

    > [!WARNING]
    > Nastavení vysokého kontrastu systému Windows má vliv na všechny aplikace a uživatelské rozhraní v počítači.

### <a name="use-visual-studio-extra-contrast"></a>Použít extra kontrast sady Visual Studio

Pomocí následujících postupů můžete zapnout možnost speciálního kontrastu sady Visual Studio:

1. Na panelu nabídek v aplikaci Visual Studio zvolte možnost **nástroje**  >  **Možnosti**a potom v seznamu možnosti zvolte možnost **Environment**  >  **Obecné**prostředí.

1. V rozevíracím seznamu **barevný motiv** zvolte motiv **Blue (extra Contrast)** a klikněte na **tlačítko OK**.

Další informace o dalších možnostech usnadnění sady Visual Studio, které jsou k dispozici pro vás, najdete na stránce [funkce usnadnění v aplikaci Visual Studio](../ide/reference/accessibility-features-of-visual-studio.md) .

> [!TIP]
> Pokud máte možnost usnadnění pro barvy nebo písma, která jsou možná užitečná, ale nejsou aktuálně dostupná v aplikaci Visual Studio, dejte nám prosím na výběr **navrhnout funkci** v [komunitě vývojářů sady Visual Studio](https://developercommunity.visualstudio.com/). Další informace o tomto fóru a o tom, jak to funguje, najdete na stránce [navrhnout funkci](../ide/suggest-a-feature.md) .

## <a name="next-steps"></a>Další kroky

Chcete-li získat další informace o všech prvcích uživatelského rozhraní, pro které můžete změnit schémata písma a barev, Projděte si stránku [písma a barvy, prostředí, dialogové okno Možnosti](../ide/reference/fonts-and-colors-environment-options-dialog-box.md) .

## <a name="see-also"></a>Viz také:

- [Změna písma a barev editoru kódu](../ide/reference/how-to-change-fonts-and-colors-in-the-editor.md)
- [Funkce editoru kódu sady Visual Studio](../ide/writing-code-in-the-code-and-text-editor.md)