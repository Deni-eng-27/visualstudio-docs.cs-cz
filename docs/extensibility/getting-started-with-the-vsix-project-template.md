---
title: Začínáme s šablonou projektu VSIX | Dokumentace Microsoftu
ms.date: 3/16/2019
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio SDK, VSIX project template
ms.assetid: 89fac33e-9380-4723-9b45-048a6e16f0ed
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b6176fda41b16a092b52e83e0ce894e1d1898e0a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62911879"
---
# <a name="get-started-with-the-vsix-project-template"></a>Začínáme se šablonou projektu VSIX

Šablona projektu VSIX k vytvoření rozšíření nebo balíčku existujícího rozšíření pro nasazení. Šablona projektu VSIX má verze jazyka Visual Basic a Visual C# a je nainstalován jako součást sady Visual Studio SDK.

 Šablona projektu VSIX se skládá právě z *source.extension.vsixmanifest* soubor, který obsahuje informace o rozšíření a prostředky, je dodáván.

 Pokud chcete najít šablonou projektu VSIX, musíte nainstalovat Visual Studio SDK. Další informace najdete v tématu [Visual Studio SDK](../extensibility/visual-studio-sdk.md).

## <a name="deploy-a-custom-project-template-using-the-vsix-project-template"></a>Nasazení vlastní šablony projektu pomocí šablony projektu VSIX

 Následující kroky ukazují, jak pomocí projektu VSIX balíček šablony projektu, který můžete sdílet s jinými vývojáři nebo odeslat do Galerie Visual Studio.

1. Vytvořte šablonu projektu.

    1. Otevřete projekt, ze kterého chcete vytvořit šablonu. Tento projekt může být libovolným typem projektu.

    2. Na **projektu** nabídky, klikněte na tlačítko **exportovat šablonu**. Postupujte podle pokynů průvodce.

         A *ZIP* soubor se vytvoří v *\My Documents\Visual Studio {version} %USERPROFILE%\My exportované šablony\\*.

2. Vytvoření prázdného projektu VSIX.

     Vyberte **Soubor** > **Nový** > **Projekt**. Do vyhledávacího pole zadejte "vsix" a vyberte buď **C#** nebo **jazyka Visual Basic** verzi **projekt VSIX**.

3. Přidat *ZIP* soubor do projektu. Nastavte jeho **kopírovat do výstupního adresáře** vlastnost `Copy Always`.

4. V **Průzkumníka řešení**, dvakrát klikněte *source.extension.vsixmanifest* soubor otevřít v **Návrhář manifestu VSIX**a pak proveďte následující změny:

    - Nastavte **název produktu** pole **moje šablona projektu**.

    - Nastavte **ID produktu** pole **MyProjectTemplate - 1**.

    - Nastavte **Autor** pole **Fabrikam**.

    - Nastavte **popis** pole **šablonu moje šablona projektu**.

    - V **prostředky** části, přidejte **Microsoft.VisualStudio.ProjectTemplate** typ a nastavte jeho cesty na název *ZIP* souboru.

5. Uložte a zavřete *source.extension.vsixmanifest* souboru.

6. Sestavte projekt.

7. Ve výstupním adresáři, dvakrát klikněte *VSIX* souboru.

8. A **instalátor VSIX** se zobrazí okno se zprávou. Postupujte podle pokynů k instalaci rozšíření.

9. Zavřete sadu Visual Studio a znovu ho otevřít.

::: moniker range="vs-2017"

10. Vyberte **rozšíření a aktualizace** (na **nástroje** nabídky) a vyberte **šablony** kategorie. Jeden z dostupných rozšíření by měl být **moje šablona projektu**.

::: moniker-end

::: moniker range=">=vs-2019"

10. Vyberte **spravovat rozšíření** (na **rozšíření** nabídky) a vyberte **šablony** kategorie. Jeden z dostupných rozšíření by měl být **moje šablona projektu**.

::: moniker-end

11. Nová šablona projektu se zobrazí v **nový projekt** dialogového okna na stejném místě jako původní šablony projektu. Například, pokud jste vytvořili šablonu s názvem **VB konzoly** z konzolové aplikace jazyka Visual Basic, **VB konzoly** se zobrazí v podokně stejné jako jazyka Visual Basic **konzolovou aplikaci**šablony.

### <a name="to-specify-the-location-of-the-template-in-the-new-project-dialog-box"></a>K určení umístění šablony do pole dialogové okno nového projektu

1. Šablona složky jsou umístěny v *\Common7\IDE\ProjectTemplates {Visual Studio Instalační cesta}* a *{Visual Studio Instalační cesta} \Common7\IDE\ItemTemplates* adresáře. Názvy nejvyšší úrovně v částech **nový projekt** dialogové okno přesně shodovat s názvy složek šablony. Pokud se liší, použijte název složky šablony.

    Změnit *VSIX* soubor rozšíření *ZIP*a pak otevřete soubor.

2. Vytvořte novou složku se stejným názvem jako část **nový projekt** šablony by se zobrazit v dialogovém okně.

3. Pokud se zobrazí v dílčí část je šablona, vytvořte podsložku se stejným názvem.

4. Přesunout šablony *ZIP* souboru do nové složky.

5. Změnit *ZIP* rozšíření *VSIX*.

6. Otevření manifestu VSIX.

7. V manifestu VSIX, aktualizujte **Asset** cestu k šabloně tak, že odkazuje na kořen stromu adresářů, který obsahuje soubor šablony. Například, pokud je šablona v *\CSharp\Windows*, odkaz by měl ukazovat na *\CSharp*.
