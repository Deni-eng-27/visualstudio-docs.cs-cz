---
title: 'Postupy: použití proměnných prostředí v sestavení | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- environment variables, referencing
- projects [.NET Framework], environment variables
- MSBuild, environment variables
ms.assetid: 7f9e4469-8865-4b59-aab3-3ff26bd36e77
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4d66fb73972a81e421b6e7343e549b0ef3069001
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/01/2020
ms.locfileid: "75574415"
---
# <a name="how-to-use-environment-variables-in-a-build"></a>Postupy: použití proměnných prostředí v sestavení
Při sestavování projektů je často nutné nastavit možnosti sestavení pomocí informací, které nejsou v souboru projektu, nebo soubory, které tvoří projekt. Tyto informace jsou obvykle uloženy v proměnných prostředí.

## <a name="reference-environment-variables"></a>Proměnné prostředí odkazů
 Všechny proměnné prostředí jsou k dispozici pro soubor projektu [!INCLUDE[vstecmsbuildengine](../msbuild/includes/vstecmsbuildengine_md.md)] ([!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]) jako vlastnosti.

> [!NOTE]
> Pokud soubor projektu obsahuje explicitní definici vlastnosti, která má stejný název jako proměnná prostředí, vlastnost v souboru projektu přepíše hodnotu proměnné prostředí.

#### <a name="to-use-an-environment-variable-in-an-msbuild-project"></a>Použití proměnné prostředí v projektu MSBuild

- Odkazovat na proměnnou prostředí stejným způsobem jako Proměnná deklarovaná v souboru projektu. Například následující kód odkazuje na proměnnou prostředí BIN_PATH:

   `<FinalOutput>$(BIN_PATH)\MyAssembly.dll</FinalOutput>`

  Můžete použít atribut `Condition` k poskytnutí výchozí hodnoty vlastnosti, pokud nebyla proměnná prostředí nastavena.

#### <a name="to-provide-a-default-value-for-a-property"></a>Zadání výchozí hodnoty pro vlastnost

- Použijte atribut `Condition` u vlastnosti pro nastavení hodnoty pouze v případě, že vlastnost nemá žádnou hodnotu. Například následující kód nastaví vlastnost `ToolsPath` na *c:\Tools* pouze v případě, že není nastavena proměnná prostředí `ToolsPath`:

     `<ToolsPath Condition="'$(TOOLSPATH)' == ''">c:\tools</ToolsPath>`

    > [!NOTE]
    > V názvech vlastností nejsou rozlišována velká a malá písmena, takže `$(ToolsPath)` i `$(TOOLSPATH)` odkazují na stejnou vlastnost nebo proměnnou prostředí.

## <a name="example"></a>Příklad
 Následující soubor projektu používá k určení umístění adresářů proměnné prostředí.

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

## <a name="see-also"></a>Viz také:
- [MSBuild](../msbuild/msbuild.md)
- [Vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md)
- [Postupy: sestavení stejných zdrojových souborů s různými možnostmi](../msbuild/how-to-build-the-same-source-files-with-different-options.md)
