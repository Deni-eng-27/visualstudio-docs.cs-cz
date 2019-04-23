---
title: 'Postupy: Použití proměnných prostředí v sestavení | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- environment variables, referencing
- projects [.NET Framework], environment variables
- MSBuild, environment variables
ms.assetid: 7f9e4469-8865-4b59-aab3-3ff26bd36e77
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d6dd7f086a5e2163c1b2f6db2c6bd50c45c36e85
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60065568"
---
# <a name="how-to-use-environment-variables-in-a-build"></a>Postupy: Použití proměnných prostředí v sestavení
Při sestavování projektů, je často nutné nastavit možnosti sestavení pomocí informací, které nejsou v souboru projektu nebo soubory, které tvoří vašeho projektu. Tyto informace jsou obvykle uložená v proměnné prostředí.

## <a name="reference-environment-variables"></a>Referenční proměnné prostředí
 Všechny proměnné prostředí jsou k dispozici na [!INCLUDE[vstecmsbuildengine](../msbuild/includes/vstecmsbuildengine_md.md)] ([!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]) projektu soubor jako vlastnosti.

> [!NOTE]
>  Pokud soubor projektu obsahuje explicitní definice vlastnosti, která má stejný název jako proměnné prostředí, přepíše vlastnost v souboru projektu hodnotu proměnné prostředí.

#### <a name="to-use-an-environment-variable-in-an-msbuild-project"></a>Chcete-li použít proměnné prostředí v projektu nástroje MSBuild

- Odkazujte na proměnné prostředí stejným způsobem, jako byste to udělali proměnné deklarované v souboru projektu. Například následující kód odkazuje na proměnnou prostředí BIN_PATH:

   `<FinalOutput>$(BIN_PATH)\MyAssembly.dll</FinalOutput>`

  Můžete použít `Condition` atribut poskytnout výchozí hodnotu pro vlastnost, pokud nebyla nastavena proměnná prostředí.

#### <a name="to-provide-a-default-value-for-a-property"></a>Chcete-li zadat výchozí hodnotu pro vlastnost

- Použití `Condition` atribut u vlastnosti a nastavte vlastnost na hodnotu pouze tehdy, pokud nemá žádnou hodnotu. Například následující kód nastaví `ToolsPath` vlastnost *c:\tools* pouze tehdy, pokud `ToolsPath` není nastavena proměnná prostředí:

     `<ToolsPath Condition="'$(TOOLSPATH)' == ''">c:\tools</ToolsPath>`

    > [!NOTE]
    >  Názvy vlastností nejsou malá a velká písmena tak obě `$(ToolsPath)` a `$(TOOLSPATH)` odkazovat na stejnou vlastnost nebo prostředí proměnnou.

## <a name="example"></a>Příklad
 Následující soubor projektu používá proměnné prostředí a zadejte umístění adresáře.

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
- [Postupy: Sestavení stejných zdrojových souborů s různými možnostmi](../msbuild/how-to-build-the-same-source-files-with-different-options.md)
