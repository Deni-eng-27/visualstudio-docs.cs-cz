---
title: Paralelní sestavování více projektů pomocí MSBuild | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- parallel project builds
- building multiple projects in parallel
- msbuild, building projects in parallel
ms.assetid: c8c9aadc-33ad-4aa1-b07d-b879e9eabda0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 48f02e9e2f051bbdb77b0d567d79d8793787cf1c
ms.sourcegitcommit: 257fc60eb01fefafa9185fca28727ded81b8bca9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/25/2019
ms.locfileid: "72911271"
---
# <a name="build-multiple-projects-in-parallel-with-msbuild"></a>Paralelní sestavení více projektů pomocí MSBuild
Nástroj MSBuild lze použít pro rychlejší sestavení více projektů tak, že budou tyto projekty spuštěny paralelně. Pro paralelní spuštění sestavení je možné na počítači s více jádry nebo s více procesory použít následující nastavení:

- Přepínač příkazového řádku `-maxcpucount`.

- Parametr úlohy <xref:Microsoft.Build.Tasks.MSBuild.BuildInParallel%2A> na úlohu nástroje MSBuild.

> [!NOTE]
> Výkon sestavení může mít i přepínač **-verbose** ( **-v**) na příkazovém řádku. Výkon sestavení se může snížit, je-li podrobnost informací protokolu sestavení nastavena na možnosti podrobné nebo diagnostické, které se používají pro řešení potíží. Další informace najdete v tématu [získání protokolů sestavení](../msbuild/obtaining-build-logs-with-msbuild.md) a [odkazů na příkazový řádek](../msbuild/msbuild-command-line-reference.md).

## <a name="-maxcpucount-switch"></a>– Přepínač maxcpucount
Použijete-li přepínač `-maxcpucount` nebo `-m` pro krátké, nástroj MSBuild může vytvořit zadaný počet procesů *MSBuild. exe* , které mohou být spuštěny paralelně. Tyto procesy jsou známé také jako „pracovní procesy“. Každý pracovní proces používá samostatné jádro nebo procesor – je-li nějaký k dispozici – pro sestavení projektu ve stejnou dobu, kdy ostatní procesory provádějí sestavení ostatních projektů. Například nastavení tohoto přepínače na hodnotu „4“ způsobí, že nástroj MSBuild vytvoří čtyři pracovní procesy pro sestavení projektu.

Při použití přepínače `-maxcpucount` bez zadání hodnoty použije nástroj MSBuild číslo odpovídající počtu procesorů v počítači.

Další informace o tomto přepínači, který byl představen v MSBuild 3,5, najdete v tématu [Reference k příkazovému řádku](../msbuild/msbuild-command-line-reference.md).

Následující příklad nastaví nástroj MSBuild pro použití tří pracovních procesů. Použitím této konfigurace může nástroj MSBuild provádět souběžné sestavení tří projektů.

```cmd
msbuild.exe myproj.proj -maxcpucount:3
```

## <a name="buildinparallel-task-parameter"></a>BuildInParallel – parametr úlohy
`BuildInParallel` je volitelný logický parametr u úlohy [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. Pokud je `BuildInParallel` nastaveno na `true` (jeho výchozí hodnota je `false`), vygeneruje se více pracovních procesů, aby se sestavilo co nejvíce projektů. Aby tento postup správně fungoval, musí být přepínač `-maxcpucount` nastaven na hodnotu větší než 1 a systém musí být alespoň dvoujádrový nebo mít dva nebo více procesorů.

Následuje příklad, který je pořízen od *společnosti Microsoft. Common. targets*, o tom, jak nastavit parametr `BuildInParallel`.

```xml
<PropertyGroup>
    <BuildInParallel Condition="'$(BuildInParallel)' ==
        ''">true</BuildInParallel>
</PropertyGroup>
<MSBuild
    Projects="@(_MSBuildProjectReferenceExistent)"
    Targets="GetTargetPath"
    BuildInParallel="$(BuildInParallel)"
    Properties="%(_MSBuildProjectReferenceExistent.SetConfiguration);
        %(_MSBuildProjectReferenceExistent.SetPlatform)"
    Condition="'@(NonVCProjectReference)'!='' and
        ('$(BuildingSolutionFile)' == 'true' or
        '$(BuildingInsideVisualStudio)' == 'true' or
        '$(BuildProjectReferences)' != 'true') and
        '@(_MSBuildProjectReferenceExistent)' != ''"
    ContinueOnError="!$(BuildingProject)">
    <Output TaskParameter="TargetOutputs"
        ItemName="_ResolvedProjectReferencePaths"/>
</MSBuild>
```

## <a name="see-also"></a>Viz také:
- [Použití více procesorů k sestavení projektů](../msbuild/using-multiple-processors-to-build-projects.md)
- [Zápis protokolovacích nástrojů s více procesory](../msbuild/writing-multi-processor-aware-loggers.md)
- [Blog C++ o optimalizaci sestavení paralelně](https://devblogs.microsoft.com/visualstudio/tuning-c-build-parallelism-in-vs2010/)
