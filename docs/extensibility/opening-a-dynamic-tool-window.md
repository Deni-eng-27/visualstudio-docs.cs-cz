---
title: "Otevřete okno dynamické nástroj | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: tool windows, dynamic
ms.assetid: 21547ba7-6e81-44df-9277-265bf34f877a
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 588badc75a604df65949c99fa16f84ad4e9c9175
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="opening-a-dynamic-tool-window"></a>Otevřete okno dynamické nástroj
Nástroje systému windows jsou obvykle otevřít pomocí příkazu v nabídce, nebo ekvivalentní klávesové zkratky. V některých případech však může být zapotřebí okno nástroje, které se otevře vždy, když platí konkrétní kontext uživatelského rozhraní a zavře případě kontext uživatelského rozhraní se již nepoužívá. Nástroje systému windows, jako jsou ty se nazývají *dynamické* nebo *automaticky viditelná*.  
  
> [!NOTE]
>  Seznam předdefinovaných kontexty uživatelského rozhraní, naleznete v části <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT>. Pro  
  
 Pokud chcete otevřít okno dynamické nástroje při spuštění a je možné pro vytvoření selhání, musí implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackageDynamicToolOwnerEx> rozhraní a testování podmínky selhání v <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackageDynamicToolOwnerEx.QueryShowTool%2A> metoda. Aby prostředí vědět, že máte okno dynamické nástroje, které musí být otevřen při spuštění, je nutné přidat `SupportsDynamicToolOwner` (nastavená na hodnotu 1) registrace balíčku. Tato hodnota není součástí standardní <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute>, takže musíte vytvořit vlastní atribut ho přidejte. Další informace o vlastních atributů najdete v tématu [pomocí vlastní atribut registrace k registraci rozšíření](../extensibility/registering-and-unregistering-vspackages.md#using-a-custom-registration-attribute-to-register-an-extension).  
  
 Použití <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> otevřete okno nástroje. Panel nástrojů se vytvoří podle potřeby.  
  
> [!NOTE]
>  Okno dynamické nástroje je možné uzavřít uživatelem. Pokud chcete vytvořit příkaz nabídky, takže uživatel může znovu otevřít okno nástroje, příkaz nabídky by měly být povoleny v rámci stejné uživatelské rozhraní, které se otevře okno nástroje a zakázána, jinak hodnota.  
  
### <a name="to-open-a-dynamic-tool-window"></a>Chcete-li otevřít okno dynamické nástroje  
  
1.  Vytvoření projektu VSIX s názvem **DynamicToolWindow** a přidat šablonu nástroj okno Položka s názvem **DynamicWindowPane.cs**. Další informace najdete v tématu [vytváření rozšíření s okno nástroje](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
2.  V souboru DynamicWindowPanePackage.cs najdete DynamicWindowPanePackage deklaraci. Přidat <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> a T:Microsoft.VisualStudio.Shell.ProvideToolWindowVisibilityAttribute atributy registrace okno nástroje.  
  
    ```vb  
    [[ProvideToolWindow(typeof(DynamicWindowPane)]  
    [ProvideToolWindowVisibility(typeof(DynamicWindowPane), VSConstants.UICONTEXT.SolutionExists_string)]  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)] // Info on this package for Help/About  
    [ProvideMenuResource("Menus.ctmenu", 1)]  
    [ProvideToolWindow(typeof(DynamicToolWindow.DynamicWindowPane))]  
    [Guid(DynamicWindowPanePackageGuids.PackageGuidString)]  
    public sealed class DynamicWindowPanePackage : Package  
    {. . .}  
    ```  
  
     Takovém postupu zaregistruje panel nástrojů s názvem DynamicWindowPane jako přechodný okno, které není trvalý, když je Visual Studio zavřít a znovu otevřít. Otevření DynamicWindowPane vždy, když <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionExists_string> platí a ukončeno jinak.  
  
3.  Sestavte projekt a spusťte ladění. Experimentální instanci by se zobrazit. Panel nástrojů byste neměli vidět.  
  
4.  Otevřete projekt v experimentální instanci. By se zobrazit okno nástroje.