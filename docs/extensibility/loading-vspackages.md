---
title: Načítání VSPackage | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, autoloading
- VSPackages, loading
ms.assetid: f4c3dcea-5051-4065-898f-601269649d92
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b1c221bf06ef3b7e37e2afc1856f3e54fe5ad95e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80702956"
---
# <a name="load-vspackages"></a>Načíst VSPackage
Sady VSPackage jsou načteny do sady Visual Studio pouze v případě, že jsou jejich funkce požadovány. Například VSPackage je načten, když aplikace Visual Studio používá objekt pro vytváření projektu nebo službu, kterou VSPackage implementuje. Tato funkce se nazývá opožděné načítání, které se používá, kdykoli je to možné, ke zvýšení výkonu.

> [!NOTE]
> Visual Studio může určit určité informace VSPackage, například příkazy, které VSPackage nabízí, bez načítání VSPackage.

 Sady VSPackage lze nastavit na automatické načítání v konkrétním kontextu uživatelského rozhraní, například při otevření řešení. <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute>Atribut nastaví tento kontext.

### <a name="autoload-a-vspackage-in-a-specific-context"></a>Automatické načtení VSPackage v konkrétním kontextu

- Přidejte `ProvideAutoLoad` atribut do atributů VSPackage:

    ```csharp
    [DefaultRegistryRoot(@"Software\Microsoft\VisualStudio\14.0")]
    [PackageRegistration(UseManagedResourcesOnly = true)]
    [ProvideAutoLoad(UIContextGuids80.SolutionExists)]
    [Guid("00000000-0000-0000-0000-000000000000")] // your specific package GUID
    public class MyAutoloadedPackage : Package
    {. . .}
    ```

     <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80>Seznam kontextů uživatelského rozhraní a jejich hodnot GUID naleznete v výčtových polích pro.

- Nastavte zarážku v <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> metodě.

- Sestavte rozhraní VSPackage a spusťte ladění.

- Načtěte řešení nebo ho vytvořte.

     Rozhraní VSPackage načte a zastaví na zarážce.

## <a name="force-a-vspackage-to-load"></a>Vynutit načtení VSPackage
 Za určitých okolností může být nutné, aby VSPackage vynutil načtení jiného VSPackage. Například odlehčené VSPackage mohou načíst větší VSPackage v kontextu, který není k dispozici jako CMDUIContext.

 Metodu můžete použít <xref:Microsoft.VisualStudio.Shell.Interop.IVsShell.LoadPackage%2A> k vynucení načtení VSPackage.

- Vložte tento kód do <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> metody VSPackage, která vynutí načtení další VSPackage:

    ```csharp
    IVsShell shell = GetService(typeof(SVsShell)) as IVsShell;
    if (shell == null) return;

    IVsPackage package = null;
    Guid PackageToBeLoadedGuid =
        new Guid(Microsoft.PackageToBeLoaded.GuidList.guidPackageToBeLoadedPkgString);
    shell.LoadPackage(ref PackageToBeLoadedGuid, out package);

    ```

     Po inicializaci rozhraní VSPackage se vynutí `PackageToBeLoaded` načtení.

     Pro komunikaci VSPackage by se nemělo používat vynucené načítání. Místo toho použijte [a poskytněte služby](../extensibility/using-and-providing-services.md) .

## <a name="see-also"></a>Viz také
- [Balíčky VSPackage](../extensibility/internals/vspackages.md)
