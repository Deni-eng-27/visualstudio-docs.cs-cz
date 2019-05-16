---
title: Updatemanifestforbrowserapplication – úloha | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- UpdateManifestForBrowserApplication task [WPF MSBuild]
- adding the <hostInBrowser /> element to the application manifest [WPF MSBuild]
- building XBAP projects [WPF MSBuild]
- UpdateManifestForBrowserApplication task [WPF MSBuild], parameters
ms.assetid: 653339f7-654b-4d64-a26a-5c9f27036895
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: a0a6dff6c9e10312241f1d95128febbd5dabb6c5
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65696943"
---
# <a name="updatemanifestforbrowserapplication-task"></a>UpdateManifestForBrowserApplication – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

<xref:Microsoft.Build.Tasks.Windows.UpdateManifestForBrowserApplication> Spuštění úlohy Přidat  **\<hostInBrowser / >** element do manifestu aplikace (*projectname*. exe.manifest) při [!INCLUDE[TLA#tla_xbap](../includes/tlasharptla-xbap-md.md)] sestavení projektu.  
  
## <a name="task-parameters"></a>Parametry úlohy  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`ApplicationManifest`|Vyžaduje **[] ITaskItem** parametru.<br /><br /> Určuje cestu a název souboru manifestu aplikace, které chcete přidat `<hostInBrowser />` elementu.|  
|`HostInBrowser`|Vyžaduje **logická** parametru.<br /><br /> Určuje, jestli se má upravit manifest aplikace, které chcete zahrnout  **\<hostInBrowser / >** elementu. Pokud **true**, nový `<` **hostInBrowser / >** element je součástí  **\<vstupního bodu / >** elementu. Poznámka: Tento prvek je kumulativní zahrnutí: Pokud  **\<hostInBrowser / >** element už existuje, není odebrat nebo přepsat. Místo toho další  **\<hostInBrowser / >** vytvořit prvek. Pokud **false**, manifest aplikace se nezmění.|  
  
## <a name="remarks"></a>Poznámky  
 [!INCLUDE[TLA2#tla_xbap#plural](../includes/tla2sharptla-xbapsharpplural-md.md)] spuštění pomocí [!INCLUDE[TLA#tla_clickonce](../includes/tlasharptla-clickonce-md.md)] nasazení a proto musí podle publikována s podpůrnými manifesty nasazení a aplikace. [!INCLUDE[TLA#tla_msbuild](../includes/tlasharptla-msbuild-md.md)] používá [generateapplicationmanifest –](http://msdn2.microsoft.com/library/6wc2ccdc.aspx) úkolů ke generování manifestu aplikace.  
  
 Pak nakonfigurujte aplikaci zajistit také jejich hostování v prohlížeči, další prvek  **\<hostInBrowser / >** musí být přidán do manifestu aplikace, jak je vidět v následujícím příkladu:  
  
```  
<!--MyXBAPApplication.exe.manifest-->  
<?xml version="1.0" encoding="utf-8"?>  
<asmv1:assembly ... >  
    <asmv1:assemblyIdentity ... />  
    <application />  
    <entryPoint>  
      ...  
      <hostInBrowser xmlns="urn:schemas-microsoft-com:asm.v3" />  
    </entryPoint>  
  ...  
/>  
```  
  
 <xref:Microsoft.Build.Tasks.Windows.UpdateManifestForBrowserApplication> Při spuštění úlohy [!INCLUDE[TLA2#tla_xbap](../includes/tla2sharptla-xbap-md.md)] sestavení projektu, aby bylo možné přidat `<hostInBrowser />` elementu.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak zajistit, aby `<hostInBrowser />` element je součástí souboru manifestu aplikace.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.UpdateManifestForBrowserApplication"  
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="UpdateManifestForBrowserApplicationTask">  
    <UpdateManifestForBrowserApplication  
      ApplicationManifest="MyXBAPApplication.exe.manifest"  
      HostInBrowser="true" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace WPF MSBuild](../msbuild/wpf-msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/wpf-msbuild-task-reference.md)   
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Sestavení aplikace WPF (WPF)](https://msdn.microsoft.com/library/a58696fd-bdad-4b55-9759-136dfdf8b91c)   
 [Přehled aplikací Prohlížeče WPF XAML](https://msdn.microsoft.com/library/3a7a86a8-75d5-4898-96b9-73da151e5e16)
