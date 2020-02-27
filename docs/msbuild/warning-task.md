---
title: Úloha upozornění | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Warning
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Warning task [MSBuild]
- MSBuild, Warning task
ms.assetid: 96ba5507-8b43-4f54-a1d7-9b15644dd56c
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2e95b59b4ccc0bd2df89e45512a5bdd05c027556
ms.sourcegitcommit: 96737c54162f5fd5c97adef9b2d86ccc660b2135
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/26/2020
ms.locfileid: "77631091"
---
# <a name="warning-task"></a>Warning – úloha

Zaznamená upozornění během sestavení na základě vyhodnoceného podmíněného příkazu.

## <a name="parameters"></a>Parametry

 Následující tabulka popisuje parametry úlohy `Warning`.

| Parametr | Popis |
|---------------| - |
| `Code` | Volitelný parametr `String`.<br /><br /> Kód upozornění, který se má přidružit k upozornění. |
| `File` | Volitelný parametr `String`.<br /><br /> Určuje relevantní soubor, pokud existuje. Pokud není zadán žádný soubor, bude použit soubor obsahující varovná úloha. |
| `HelpKeyword` | Volitelný parametr `String`.<br /><br /> Klíčové slovo Help pro přidružení k upozornění |
| `Text` | Volitelný parametr `String`.<br /><br /> Text upozornění, který nástroj MSBuild zaznamená, pokud je parametr `Condition` vyhodnocen jako `true`. |

## <a name="remarks"></a>Poznámky

 Úloha `Warning` umožňuje projektům MSBuild kontrolovat přítomnost požadované konfigurace nebo vlastnosti před pokračováním v dalším kroku sestavení.

 Pokud je parametr `Condition` úlohy `Warning` vyhodnocen jako `true`, je hodnota parametru `Text` protokolována a sestavení bude nadále spuštěno. Pokud parametr `Condition` neexistuje, text upozornění se zaznamená do protokolu. Další informace o protokolování naleznete v tématu [získání protokolů sestavení](../msbuild/obtaining-build-logs-with-msbuild.md).

 Kromě výše uvedených parametrů Tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třídy, které sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popis naleznete v tématu [TaskExtension – Base Class](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Příklad

 Následující příklad kódu kontroluje vlastnosti, které jsou nastaveny na příkazovém řádku. Pokud nejsou nastaveny žádné vlastnosti, projekt vyvolá událost upozornění a zaznamená hodnotu parametru `Text` `Warning` úlohy.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    <Target Name="ValidateCommandLine">
        <Warning
            Text=" The 0 property was not set on the command line."
            Condition="'$(0)' == ''" />
        <Warning
            Text=" The FREEBUILD property was not set on the command line."
            Condition="'$(FREEBUILD)' == ''" />
    </Target>
    ...
</Project>
```

## <a name="see-also"></a>Viz také

- [Získat protokoly sestavení](../msbuild/obtaining-build-logs-with-msbuild.md)
- [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)
