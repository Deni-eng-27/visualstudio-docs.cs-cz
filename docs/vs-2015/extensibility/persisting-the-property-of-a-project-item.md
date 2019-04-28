---
title: Trvalé uložení vlastnosti položky projektu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- properties, adding to a project item
- project items, adding properties
ms.assetid: d7a0f2b0-d427-4d49-9536-54edfb37c0f3
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 4adcf0f5c5770f5d3ffc0e0ed9bffdb108869c7f
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63441547"
---
# <a name="persisting-the-property-of-a-project-item"></a>Trvalé uložení vlastnosti položky projektu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete chtít zachovat vlastnosti, které přidáte do položky projektu, jako je například autor zdrojového souboru. To lze provést uložení vlastnost v souboru projektu.  
  
 Prvním krokem k uchování vlastností v souboru projektu je získat hierarchii projektu jako <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> rozhraní. Toto rozhraní můžete získat pomocí služby Automation nebo s použitím <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection>. Po získání rozhraní můžete určit, která položka projektu je aktuálně vybrána. Jakmile budete mít ID položky projektu, můžete použít <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetItemAttribute%2A> přidat vlastnost.  
  
 V následujících postupech zachovat vlastnost VsPkg.cs `Author` s hodnotou `Tom` v souboru projektu.  
  
### <a name="to-obtain-the-project-hierarchy-with-the-dte-object"></a>Chcete-li získat hierarchii projektu s objekt DTE  
  
1. Přidejte následující kód do vašeho balíčku VSPackage:  
  
    ```csharp  
    EnvDTE.DTE dte = (EnvDTE.DTE)Package.GetGlobalService(typeof(EnvDTE.DTE));  
    EnvDTE.Project project = dte.Solution.Projects.Item(1);  
  
    string uniqueName = project.UniqueName;  
    IVsSolution solution = (IVsSolution)Package.GetGlobalService(typeof(SVsSolution));  
    IVsHierarchy hierarchy;  
    solution.GetProjectOfUniqueName(uniqueName, out hierarchy);  
    ```  
  
### <a name="to-persist-the-project-item-property-with-the-dte-object"></a>Zachovat vlastnosti položky projektu s objekt DTE  
  
1. Přidejte následující kód do kódu uvedeného v metodě v předchozím postupu:  
  
    ```csharp  
    IVsBuildPropertyStorage buildPropertyStorage =   
        hierarchy as IVsBuildPropertyStorage;  
    if (buildPropertyStorage != null)  
    {  
        uint itemId;  
        string fullPath = (string)project.ProjectItems.Item(  
            "VsPkg.cs").Properties.Item("FullPath").Value;  
        hierarchy.ParseCanonicalName(fullPath, out itemId);  
        buildPropertyStorage.SetItemAttribute(itemId, "Author", "Tom");  
    }  
    ```  
  
### <a name="to-obtain-the-project-hierarchy-using-ivsmonitorselection"></a>Chcete-li získat hierarchii projektu pomocí IVsMonitorSelection  
  
1. Přidejte následující kód do vašeho balíčku VSPackage:  
  
    ```csharp  
    IVsHierarchy hierarchy = null;  
    IntPtr hierarchyPtr = IntPtr.Zero;  
    IntPtr selectionContainer = IntPtr.Zero;  
    uint itemid;  
  
    // Retrieve shell interface in order to get current selection  
    IVsMonitorSelection monitorSelection =     Package.GetGlobalService(typeof(SVsShellMonitorSelection)) as     IVsMonitorSelection;  
    if (monitorSelection == null)  
        throw new InvalidOperationException();  
  
    try  
    {  
        // Get the current project hierarchy, project item, and selection container for the current selection  
        // If the selection spans multiple hierachies, hierarchyPtr is Zero  
        IVsMultiItemSelect multiItemSelect = null;  
        ErrorHandler.ThrowOnFailure(  
            monitorSelection.GetCurrentSelection(  
                out hierarchyPtr, out itemid,   
                out multiItemSelect, out selectionContainer));  
  
        // We only care if there is only one node selected in the tree  
        if (!(itemid == VSConstants.VSITEMID_NIL ||   
            hierarchyPtr == IntPtr.Zero ||  
            multiItemSelect != null ||  
            itemid == VSConstants.VSITEMID_SELECTION))  
        {  
            hierarchy = Marshal.GetObjectForIUnknown(hierarchyPtr)  
                as IVsHierarchy;  
        }  
    }  
    finally  
    {  
        if (hierarchyPtr != IntPtr.Zero)  
            Marshal.Release(hierarchyPtr);  
        if (selectionContainer != IntPtr.Zero)  
            Marshal.Release(selectionContainer);  
    }  
    ```  
  
2. 
  
### <a name="to-persist-the-selected-project-item-property-given-the-project-hierarchy"></a>Zachovat položky vlastnosti vybraného projektu dána hierarchie projektu  
  
1. Přidejte následující kód do kódu uvedeného v metodě v předchozím postupu:  
  
    ```  
    IVsBuildPropertyStorage buildPropertyStorage =   
        hierarchy as IVsBuildPropertyStorage;  
    if (buildPropertyStorage != null)  
    {  
        buildPropertyStorage.SetItemAttribute(itemId, "Author", "Tom");  
    }  
    ```  
  
### <a name="to-verify-that-the-property-is-persisted"></a>Chcete-li ověřit, že vlastnost je trvalá.  
  
1. Spustit [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] a poté otevřete nebo vytvořte řešení.  
  
2. Vyberte projekt položku VsPkg.cs v **Průzkumníka řešení**.  
  
3. Použijte zarážku nebo jinak určit, že je načten vašeho balíčku VSPackage a že SetItemAttribute běží.  
  
    > [!NOTE]
    > Je možné vykonat autoload VSPackage v kontextu uživatelského rozhraní <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionExists_guid>. Další informace najdete v tématu [načítání rozšíření VSPackages](../extensibility/loading-vspackages.md).  
  
4. Zavřít [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] a pak otevřete soubor projektu v poznámkovém bloku. Měli byste vidět \<Autor > Označit hodnota vlastní, následujícím způsobem:  
  
    ```  
    <Compile Include="VsPkg.cs">  
        <Author>Tom</Author>  
    </Compile>  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Vlastní nástroje](../extensibility/internals/custom-tools.md)
