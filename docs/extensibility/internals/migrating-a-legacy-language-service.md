---
title: Migrace služby starší verze jazyka | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- language services, migrating
ms.assetid: e0f666a0-92a7-4f9c-ba79-d05b13fb7f11
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d508c26e27b6a9d9709eff00b2b248ee5feb3466
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55000234"
---
# <a name="migrating-a-legacy-language-service"></a>Migrace služby starší verze jazyka
Služby starší verze jazyka můžete migrovat na novější verzi sady Visual Studio aktualizuje se projekt a soubor source.extension.vsixmanifest přidáním do projektu. Samotnou službu jazyka se budou nadále fungovat stejně jako předtím, protože editoru sady Visual Studio přizpůsobí ho.  
  
 Služby starší verze jazyka jsou implementovány jako součást sady VSPackage, ale novější způsob implementace funkce služba jazyka je pro použití rozšíření MEF. Další informace o nový způsob implementace služby jazyka najdete v tématu [Editor a rozšíření služeb jazyka](../../extensibility/editor-and-language-service-extensions.md).  
  
> [!NOTE]
>  Doporučujeme vám, že začnete používat nový editor API co nejdříve. Tím vylepšíme výkonu vaší služby jazyka a umožňují využívat nové funkce editoru.  
  
## <a name="migrating-a-visual-studio-2008-language-service-solution-to-a-later-version"></a>Migrace řešení sady Visual Studio 2008 jazykové služby na novější verzi  
 Následující kroky ukazují, jak přizpůsobit s názvem RegExLanguageService ukázky sady Visual Studio 2008. Tato ukázka v rámci instalace sady Visual Studio 2008 SDK, můžete najít v *cestu instalace sady Visual Studio SDK*\VisualStudioIntegration\Samples\IDE\CSharp\Example.RegExLanguageService\ složky.  
  
> [!IMPORTANT]
>  Pokud vaše služba jazyk nedefinuje barvy, je nutné explicitně nastavit <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute.RequestStockColors%2A> k `true` na sady VSPackage:  
  
```  
[Microsoft.VisualStudio.Shell.ProvideLanguageService(typeof(YourLanguageService), YourLanguageServiceName, 0, RequestStockColors = true)]  
```  
  
#### <a name="to-migrate-a-visual-studio-2008-language-service-to-a-later-version"></a>Migrovat na novější verzi jazyka služby Visual Studio 2008  
  
1.  Nainstalujte novější verze sady Visual Studio a Visual Studio SDK. Další informace o způsobech instalace sady SDK najdete v tématu [instalace sady Visual Studio SDK](../../extensibility/installing-the-visual-studio-sdk.md).  
  
2.  Upravte soubor RegExLangServ.csproj (bez načtení jeho v sadě Visual Studio.  
  
     V `Import` uzel, který odkazuje na soubor Microsoft.VsSDK.targets nahraďte hodnotu s následujícím textem.  
  
    ```  
    $(MSBuildExtensionsPath)\Microsoft\VisualStudio\v14.0\VSSDK\Microsoft.VsSDK.targets  
    ```  
  
3.  Soubor uložte a zavřete jej.  
  
4.  Otevřete řešení RegExLangServ.sln.  
  
5.  **Jednosměrnou aktualizaci** zobrazí se okno. Klikněte na **OK**.  
  
6.  Aktualizujte vlastnosti projektu. Otevřít **vlastnosti projektu** tak, že vyberete uzel projektu v okně **Průzkumníku řešení**, pravým tlačítkem myši a vyberete **vlastnosti**.  
  
    -   Na **aplikace** kartu, změňte **Cílová architektura** k **4.6.1**.  
  
    -   Na **ladění** kartě **externí program Start** zadejte  **\<cestu instalace sady Visual Studio > \Common7\IDE\devenv.exe.**.  
  
         V **argumenty příkazového řádku** zadejte /**rootsuffix Exp**.  
  
7.  Aktualizujte tyto odkazy:  
  
    -   Odeberte odkaz na Microsoft.VisualStudio.Shell.9.0.dll a pak přidejte odkazy na Microsoft.VisualStudio.Shell.14.0.dll a Microsoft.VisualStudio.Shell.Immutable.11.0.dll.  
  
    -   Odeberte odkaz na Microsoft.VisualStudio.Package.LanguageService.9.0.dll a pak přidejte odkaz na Microsoft.VisualStudio.Package.LanguageService.14.0.dll.  
  
    -   Přidejte odkaz na Microsoft.VisualStudio.Shell.Interop.10.0.dll.  
  
8.  Otevřete soubor VsPkg.cs a změňte hodnotu `DefaultRegistryRoot` atribut  
  
    ```  
    "Software\\Microsoft\\VisualStudio\\14.0Exp"  
    ```  
  
9. Původní ukázce nezaregistruje jeho služba jazyka, proto do VsPkg.cs musí přidat tento atribut.  
  
    ```  
    [ProvideLanguageService(typeof(RegularExpressionLanguageService), "RegularExpressionLanguage", 0, RequestStockColors=true)]  
    ```  
  
10. Musíte přidat soubor source.extension.vsixmanifest.  
  
    -   Zkopírujte tento soubor do adresáře vašeho projektu z existujícího rozšíření. (Jedním ze způsobů, jak tento soubor je vytvoření projektu VSIX (v části **souboru**, klikněte na tlačítko **nový**, pak klikněte na tlačítko **projektu**. V jazyce Visual Basic nebo C# kliknutím **rozšiřitelnost**a pak vyberte **projekt VSIX**.)  
  
    -   Přidejte soubor do projektu.  
  
    -   V souboru **vlastnosti**, nastavte **akce sestavení** k **žádný**.  
  
    -   Otevře soubor **editoru manifestu VSIX**.  
  
    -   Změňte následující pole:  
  
    -   **ID**: RegExLangServ  
  
    -   **Název produktu**: RegExLangServ  
  
    -   **Popis**: Služba jazyka regulárních výrazů.  
  
    -   V části **prostředky**, klikněte na tlačítko **nový**, vyberte **typ** k **Microsoft.VisualStudio.VsPackage**, nastavte **zdroj** k **projekt v aktuálním řešení**a pak nastavte **projektu** k **RegExLangServ**.  
  
    -   Soubor uložte a zavřete.  
  
11. Sestavte řešení. Vytvořené soubory, které jsou nasazené na **%USERPROFILE%\AppData\Local\Microsoft\VisualStudio\14.0Exp\Extensions\MSIT\ RegExLangServ\\**.  
  
12. Spusťte ladění. Otevřít druhou instanci aplikace Visual Studio.  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření služeb starší verze jazyka](../../extensibility/internals/legacy-language-service-extensibility.md)