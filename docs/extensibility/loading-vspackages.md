---
title: "Načítání VSPackages | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSPackages, autoloading
- VSPackages, loading
ms.assetid: f4c3dcea-5051-4065-898f-601269649d92
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 5efc043ae6e88f3f7b3c989a2c37c0ff9f555dd6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="loading-vspackages"></a>Načítání VSPackages
VSPackages jsou načteny do sady Visual Studio jenom v případě, že se požaduje jejich funkce. Například VSPackage je načtena, když Visual Studio použije objekt pro vytváření projektu nebo služba, která implementuje VSPackage. Tato funkce je volána zpožděné načítání, který se používá, pokud je to možné ke zlepšení výkonu.  
  
> [!NOTE]
>  Visual Studio můžete určit určité VSPackage informace, například příkazy, které nabízí VSPackage, bez načítání VSPackage.  
  
 VSPackages může být nastavena na autoload v kontextu určitého uživatelského rozhraní (UI), například když je řešení otevřené. <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> Atribut nastaví tento kontext.  
  
### <a name="autoloading-a-vspackage-in-a-specific-context"></a>Autoloading VSPackage v konkrétní kontextu  
  
-   Přidat `ProvideAutoLoad` atribut VSPackage atributy:  
  
    ```csharp  
    [DefaultRegistryRoot(@"Software\Microsoft\VisualStudio\14.0")]  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [ProvideAutoLoad(UIContextGuids80.SolutionExists)]  
    [Guid("00000000-0000-0000-0000-000000000000")] // your specific package GUID  
    public class MyAutoloadedPackage : Package  
    {. . .}  
    ```  
  
     V tématu Výčtové pole <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80> seznam kontexty uživatelského rozhraní a jejich hodnoty identifikátor GUID.  
  
-   Nastavte zarážky v <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> metoda.  
  
-   Sestavení VSPackage a spusťte ladění.  
  
-   Spouštění řešení nebo ji vytvořte.  
  
     VSPackage načte a zastaví u zarážky.  
  
## <a name="forcing-a-vspackage-to-load"></a>Vynucení VSPackage načíst  
 Za určitých okolností může mít VSPackage vynutit jiný VSPackage má být načten. Například lightweight VSPackage může načíst větší VSPackage v kontextu, který není k dispozici jako CMDUIContext.  
  
 Můžete použít <xref:Microsoft.VisualStudio.Shell.Interop.IVsShell.LoadPackage%2A> metoda vynutit VSPackage načíst.  
  
-   Vložte tento kód do <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> metoda VSPackage, který vynutí jiné VSPackage načíst:  
  
    ```csharp  
    IVsShell shell = GetService(typeof(SVsShell)) as IVsShell;  
    if (shell == null) return;  
  
    IVsPackage package = null;  
    Guid PackageToBeLoadedGuid =   
        new Guid(Microsoft.PackageToBeLoaded.GuidList.guidPackageToBeLoadedPkgString);  
    shell.LoadPackage(ref PackageToBeLoadedGuid, out package);  
  
    ```  
  
     Při inicializaci VSPackage vynutí `PackageToBeLoaded` načíst.  
  
     Platnost načítání není vhodné používat pro komunikaci VSPackage. Použití [pomocí a poskytování služeb](../extensibility/using-and-providing-services.md) místo.
  
## <a name="see-also"></a>Viz také  
 [Balíčky VSPackage](../extensibility/internals/vspackages.md)
