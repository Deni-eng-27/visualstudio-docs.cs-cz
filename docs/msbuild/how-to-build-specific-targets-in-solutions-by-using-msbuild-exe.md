---
title: Použití nástroje MSBuild. exe k sestavování specifických cílů v řešeních
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, building specific targets in a solution
- msbuild.exe, building specific targets in a solution
- MSBuild, msbuild.exe
ms.assetid: f46feb9b-4c16-4fec-b6e1-36a959692ba3
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 921b5d2d4aad7cfe48b7f6cc9cb802fde9520e19
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/01/2020
ms.locfileid: "75585255"
---
# <a name="how-to-build-specific-targets-in-solutions-by-using-msbuildexe"></a>Postupy: sestavování specifických cílů v řešení pomocí nástroje MSBuild. exe
Nástroj *MSBuild. exe* můžete použít k sestavení specifických cílů konkrétních projektů v řešení.

#### <a name="to-build-a-specific-target-of-a-specific-project-in-a-solution"></a>Sestavení konkrétního cíle konkrétního projektu v řešení

1. Do příkazového řádku zadejte `MSBuild.exe <SolutionName>.sln`, kde `<SolutionName>` odpovídá názvu souboru řešení, které obsahuje cíl, který chcete spustit.

2. Zadejte cíl za přepínačem `-target:` ve formátu \<ProjectName >:\<cílový_název >. Pokud název projektu obsahuje některý ze znaků `%`, `$`, `@`, `;`, `.`, `(`, `)`nebo `'`, nahraďte je `_`m v zadaném cílovém názvu.

## <a name="example"></a>Příklad
 Následující příklad spustí `Rebuild` cíl projektu `NotInSlnFolder` a potom spustí `Clean` cíl projektu `InSolutionFolder`, který je umístěn ve složce řešení *NewFolder* .

```cmd
msbuild SlnFolders.sln -target:NotInSlnfolder:Rebuild;NewFolder\InSolutionFolder:Clean
```

## <a name="troubleshooting"></a>Odstraňování problémů

Pokud chcete prostudovat možnosti, které máte k dispozici, můžete k tomu použít možnost ladění poskytovanou nástrojem MSBuild. Nastavte proměnnou prostředí `MSBUILDEMITSOLUTION=1` a sestavte řešení. Tím se vytvoří soubor MSBuild s názvem *\<název sady >. sln. metaproj* , který ukazuje interní zobrazení řešení MSBuild v době sestavení. Můžete zkontrolovat toto zobrazení, abyste zjistili, jaké cíle jsou k dispozici pro sestavení.

Nevytvářejte s touto sadou proměnných prostředí, pokud nepotřebujete toto interní zobrazení. Toto nastavení může způsobit problémy při vytváření projektů ve vašem řešení.

## <a name="see-also"></a>Viz také:
- [Reference k příkazovému řádku](../msbuild/msbuild-command-line-reference.md)
- [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)
- [MSBuild](../msbuild/msbuild.md)
- [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)
