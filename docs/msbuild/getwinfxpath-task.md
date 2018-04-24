---
title: Getwinfxpath – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- getting the directory of the current .NET Framework runtime [WPF MSBuild]
- GetWinFXPath task [WPF MSBuild], parameters
- GetWinFXPath task [WPF MSBuild]
- obtaining the path to the current .NET Framework runtime [WPF MSBuild]
ms.assetid: b1dfb467-f3d3-47f3-83ef-af7b0e33a772
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e02d0f93dd406df170de2d4e83023fedced7d932
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="getwinfxpath-task"></a>GetWinFXPath – úloha
<xref:Microsoft.Build.Tasks.Windows.GetWinFXPath> Úkolů vrátí adresáře aktuální [!INCLUDE[TLA#tla_winfx](../msbuild/includes/tlasharptla_winfx_md.md)] modulu runtime.  
  
## <a name="task-parameters"></a>Parametry úlohy  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`WinFXPath`|Volitelné **řetězec** výstupní parametr.<br /><br /> Určuje skutečné cestu ke [!INCLUDE[TLA2#tla_winfx](../msbuild/includes/tla2sharptla_winfx_md.md)] modulu runtime.|  
|`WinFXNativePath`|Požadované **řetězec** parametr.<br /><br /> Určuje cestu k nativního [!INCLUDE[TLA2#tla_titlewinfx](../msbuild/includes/tla2sharptla_titlewinfx_md.md)] modulu runtime.|  
|`WinFXWowPath`|Požadované **řetězec** parametr.<br /><br /> Určuje cestu k [!INCLUDE[TLA#tla_winfx](../msbuild/includes/tlasharptla_winfx_md.md)] sestavení v 32bitovou verzi **Windows v systému Windows** modulu v 64bitových systémech.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud <xref:Microsoft.Build.Tasks.Windows.GetWinFXPath> úloha se provádí na 64bitový procesor **WinFXPath** parametr nastavený na cestu, která je uložená v **WinFXWowPath** parametr, jinak hodnota **WinFXPath**  parametr nastavený na cestu, která je uložená v **WinFXNativePath** parametr.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak používat **getwinfxpath –** úloh k detekci nativní cestu k [!INCLUDE[TLA2#tla_titlewinfx](../msbuild/includes/tla2sharptla_titlewinfx_md.md)] modulu runtime.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.GetWinFXPath"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="GetWinFXPathTask">  
    <GetWinFXPath  
      WinFXNativePath="c:\WinFXNative"   
      WinFXWowPath="c:\WinFXWowNative" />  
  </Target>  
  <Import Project="$(MSBuildBinPath)\Microsoft.WinFX.targets" />  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [WPF MSBuild – Reference](../msbuild/wpf-msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild – Reference](../msbuild/msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Vytvoření aplikace WPF (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)