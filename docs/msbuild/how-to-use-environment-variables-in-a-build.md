---
title: 'Postupy: použití proměnných prostředí v sestavení | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- environment variables, referencing
- projects [.NET Framework], environment variables
- MSBuild, environment variables
ms.assetid: 7f9e4469-8865-4b59-aab3-3ff26bd36e77
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 33156719cab40490b63ec945bf9c9600b3a92bda
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31572537"
---
# <a name="how-to-use-environment-variables-in-a-build"></a>Postupy: Použití proměnných prostředí v sestavení
Při sestavování projektů, je často nutné k nastavení možností pomocí informací, které nejsou v souboru projektu nebo soubory, které tvoří projektu. Tyto informace je obvykle uložen v proměnných prostředí.  
  
## <a name="referencing-environment-variables"></a>Odkazování na proměnné prostředí  
 Všechny proměnné prostředí jsou k dispozici [!INCLUDE[vstecmsbuildengine](../msbuild/includes/vstecmsbuildengine_md.md)] ([!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]) souboru projektu jako vlastnosti.  
  
> [!NOTE]
>  Pokud projekt soubor obsahuje definici explicitní vlastnosti, která má stejný název jako proměnné prostředí, vlastnost v souboru projektu přepíše hodnotu proměnné prostředí.  
  
#### <a name="to-use-an-environment-variable-in-an-msbuild-project"></a>Chcete-li použít proměnné prostředí v projektu nástroje MSBuild  
  
-   Referenční proměnné prostředí stejným způsobem, jako by proměnná definovaná v souboru projektu. Například následující kód odkazuje na proměnnou prostředí BIN_PATH:  
  
     `<FinalOutput>$(BIN_PATH)\MyAssembly.dll</FinalOutput>`  
  
 Můžete použít `Condition` atribut zadat výchozí hodnotu pro vlastnost, pokud nebyla nastavena proměnná prostředí.  
  
#### <a name="to-provide-a-default-value-for-a-property"></a>Chcete-li zadat výchozí hodnotu pro vlastnost.  
  
-   Použití `Condition` atribut na vlastnost, nastavte hodnotu pouze tehdy, pokud vlastnost nemá žádnou hodnotu. Například následující kód nastaví `ToolsPath` vlastnost c:\tools, jenom když se `ToolsPath` není nastavena proměnná prostředí:  
  
     `<ToolsPath Condition="'$(TOOLSPATH)' == ''">c:\tools</ToolsPath>`  
  
    > [!NOTE]
    >  Názvy vlastností nejsou malá a velká písmena tak obě `$(ToolsPath)` a `$(TOOLSPATH)` odkazovat na stejnou proměnnou prostředí nebo vlastnost.  
  
## <a name="example"></a>Příklad  
 Následující soubor projektu používá proměnné prostředí a určete tak umístění adresáře.  
  
```xml  
<Project DefaultTargets="FakeBuild">  
    <PropertyGroup>  
        <FinalOutput>$(BIN_PATH)\myassembly.dll</FinalOutput>  
        <ToolsPath Condition=" '$(ToolsPath)' == '' ">  
            C:\Tools  
        </ToolsPath>  
    </PropertyGroup>  
    <Target Name="FakeBuild">  
        <Message Text="Building $(FinalOutput) using the tools at $(ToolsPath)..."/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
[Nástroje MSBuild ](../msbuild/msbuild.md)  
[Vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md)  
[Postupy: Sestavení stejných zdrojových souborů s různými možnostmi](../msbuild/how-to-build-the-same-source-files-with-different-options.md)  
