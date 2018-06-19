---
title: Mergelocalizationdirectives – úloha | Microsoft Docs
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
- localizing XAML [WPF MSBuild], moving comments and attributes to a separate file
- MergeLocalizationDirectives task [WPF MSBuild], parameters
- MergeLocalizationDirectives task [WPF MSBuild]
- moving localization comments and attributes to a separate file [WPF MSBuild]
ms.assetid: 9095b4f1-88da-4194-914b-ee1456826830
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9cb696aae19675a12aeb9aa6f2b76c8e6b710ea1
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31571240"
---
# <a name="mergelocalizationdirectives-task"></a>MergeLocalizationDirectives – úloha
<xref:Microsoft.Build.Tasks.Windows.MergeLocalizationDirectives> Úloh sloučí atributů lokalizace a komentáře jednoho nebo více [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] binární formát souborů do jediného souboru pro celou sestavení.  
  
## <a name="task-parameters"></a>Parametry úlohy  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`GeneratedLocalizationFiles`|Požadované **[ITaskItem]** parametr.<br /><br /> Určuje seznam souborů direktivy lokalizace u jednotlivých souborů v [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] binární formát.|  
|`OutputFile`|Požadované **řetězec** výstupní parametr.<br /><br /> Určuje cestu výstupního sestavení kompilované lokalizace – direktivy.|  
  
## <a name="remarks"></a>Poznámky  
 Můžete přidat atributů lokalizace a komentáře [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] obsah. S [!INCLUDE[TLA#tla_wpf](../msbuild/includes/tlasharptla_wpf_md.md)] lokalizace podporu, můžete odstranit atributů lokalizace a komentáře a je uložit .loc souboru, která je oddělená od vygenerované sestavení. Můžete to provést pomocí **LocalizationPropertyStorage** atribut. Další informace o lokalizaci atributy a komentáře a **LocalizationPropertyStorage**, najdete v části [atributů lokalizace a komentáře](/dotnet/framework/wpf/advanced/localization-attributes-and-comments).  
  
## <a name="example"></a>Příklad  
 Následující příklad sloučí lokalizace připomínky několik [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] binární formát souborů do jednoho .loc souboru.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.MergeLocalizationDirectives"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="MergeLocalizationDirectivesTask">  
    <MergeLocalizationDirectives   
      GeneratedLocalizationFiles="obj\debug\page1.loc;obj\debug\page2.loc;obj\debug\page3.loc"  
      OutputFile="obj\debug\WPFMSBuildSample.loc" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [WPF MSBuild – Reference](../msbuild/wpf-msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild – Reference](../msbuild/msbuild-reference.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Vytvoření aplikace WPF (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)