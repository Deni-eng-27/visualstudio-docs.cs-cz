---
title: Začínáme s šablonou projektu VSIX | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio SDK, VSIX project template
ms.assetid: 89fac33e-9380-4723-9b45-048a6e16f0ed
caps.latest.revision: 26
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: cc3f461c9e7dbdea1fd8481594292a0a247d2173
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68204303"
---
# <a name="getting-started-with-the-vsix-project-template"></a>Začínáme se šablonou projektu VSIX
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Šablona projektu VSIX k vytvoření rozšíření nebo balíčku existujícího rozšíření pro nasazení. Šablona projektu VSIX má verze jazyka Visual Basic a Visual C# a je nainstalován jako součást sady Visual Studio SDK.  
  
 Šablona projektu VSIX se skládá právě z soubor source.extension.vsixmanifest, který obsahuje informace o rozšíření a majetek, který je dodáván.  
  
 Pokud chcete najít šablonou projektu VSIX, musíte nainstalovat Visual Studio SDK. Další informace najdete v tématu [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
## <a name="deploying-a-custom-project-template-using-the-vsix-project-template"></a>Nasazení vlastní šablony projektu pomocí šablony projektu VSIX  
 Následující kroky ukazují, jak pomocí projektu VSIX balíček šablony projektu, který můžete sdílet s jinými vývojáři nebo odeslat do Galerie Visual Studio.  
  
1. Vytvořte šablonu projektu.  
  
    1. Otevřete projekt, ze kterého chcete vytvořit šablonu. Tento projekt může být libovolným typem projektu.  
  
    2. Na **souboru** nabídky, klikněte na tlačítko **exportovat šablonu**. Postupujte podle pokynů průvodce.  
  
         Vytvoří soubor ZIP v %USERPROFILE%\My Documents\Visual Studio  *\<verze >* \My exportované šablony\\.  
  
2. Vytvoření prázdného projektu VSIX.  
  
     Na **souboru** nabídky, klikněte na tlačítko **nový** a potom klikněte na tlačítko **projektu**. Vyberte buď **jazyka Visual Basic** nebo **Visual C#** . V části vybraného uzlu, vyberte **rozšiřitelnost**a pak vyberte **projekt VSIX**.  
  
3. Přidejte do projektu soubor .zip. Nastavte jeho **kopírovat do výstupního adresáře** vlastnost `Copy Always`.  
  
4. V **Průzkumníku řešení**, dvakrát klikněte `source.extension.vsixmanifest` soubor otevřít v **Návrhář manifestu VSIX**a pak proveďte následující změny:  
  
    - Nastavte **název produktu** pole **moje šablona projektu**.  
  
    - Nastavte **ID produktu** pole **MyProjectTemplate - 1**.  
  
    - Nastavte **Autor** pole **Fabrikam**.  
  
    - Nastavte **popis** pole **šablonu moje šablona projektu**.  
  
    - V **prostředky** části, přidejte **Microsoft.VisualStudio.ProjectTemplate** zadejte a nastavte jeho cesty na název souboru .zip.  
  
5. Uložte a zavřete soubor source.extension.vsixmanifest.  
  
6. Sestavte projekt.  
  
7. Ve výstupním adresáři poklikejte na soubor .vsix.  
  
8. A **instalátor VSIX** se zobrazí okno se zprávou. Postupujte podle pokynů k instalaci rozšíření.  
  
9. Zavřete sadu Visual Studio a potom ho znovu otevřete.  
  
10. Vyberte **rozšíření a aktualizace** (na **nástroje** nabídky) a vyberte **šablony** kategorie. Jeden z dostupných rozšíření by měl být **moje šablona projektu**.  
  
11. Nová šablona projektu se zobrazí v **nový projekt** dialogového okna na stejném místě jako původní šablony projektu. Například, pokud jste vytvořili šablonu s názvem **VB konzoly** z konzolové aplikace jazyka Visual Basic, **VB konzoly** se zobrazí v podokně stejné jako jazyka Visual Basic **konzolovou aplikaci**šablony.  
  
#### <a name="to-specify-the-location-of-the-template-in-the-new-project-dialog-box"></a>K určení umístění šablony v dialogovém okně Nový projekt  
  
1. Složky šablony jsou umístěny v *Visual Studio Instalační cesta*\Common7\IDE\ProjectTemplates a *Visual Studio Instalační cesta*\Common7\IDE\ItemTemplates adresáře. Názvy oddílů nejvyšší úrovně v dialogovém okně Nový projekt přesně shodovat s názvy složek šablony. Pokud se liší, použijte název složky šablony.  
  
     Změňte příponu souboru .vsix na .zip a potom otevřete soubor.  
  
2. Vytvořte novou složku se stejným názvem jako v části dialogového okna Nový projekt, by se zobrazit v šabloně.  
  
3. Pokud se zobrazí v dílčí část je šablona, vytvořte podsložku se stejným názvem.  
  
4. Přesuňte soubor ZIP šablony do nové složky.  
  
5. Změňte příponu .zip na .vsix.  
  
6. Otevření manifestu VSIX.  
  
7. V manifestu VSIX, aktualizujte **Asset** cestu k šabloně tak, že odkazuje na kořen stromu adresářů, který obsahuje soubor šablony. Například pokud je šablona v \CSharp\Windows, odkaz by měl odkazovat na \CSharp.
