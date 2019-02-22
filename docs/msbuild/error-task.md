---
title: Error – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Error
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Error task [MSBuild]
- MSBuild, Error task
ms.assetid: e96a90ee-a8ae-4e5b-8ef2-b5cf5fedd8b2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d3788fae176b344f99884efe7552f33762255ddc
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56610304"
---
# <a name="error-task"></a>Error – úloha
Sestavení se zastaví a protokoly chybu na základě Vyhodnocená podmíněného příkazu.

## <a name="parameters"></a>Parametry
Následující tabulka popisuje parametry `Error` úloh.

| Parametr | Popis |
|---------------| - |
| `Code` | Volitelné `String` parametru.<br /><br /> Kód chyby, které chcete přidružit k chybě. |
| `File` | Volitelné `String` parametru.<br /><br /> Název souboru, který obsahuje chybu. Pokud je k dispozici žádný název souboru, soubor obsahující chyby úkolů se použije. |
| `HelpKeyword` | Volitelné `String` parametru.<br /><br /> Klíčové slovo nápovědy pro přidružení k chybě. |
| `Text` | Volitelné `String` parametru.<br /><br /> Text chyby, která [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] protokoly, pokud `Condition` vyhodnotí jako parametr `true`. |

## <a name="remarks"></a>Poznámky
`Error` Úloha umožňuje [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] sestavení projektů vydat Protokolovací nástroje text chyby a zastavit provádění.

Pokud `Condition` vyhodnotí jako parametr `true`, sestavení je zastavená a je zaznamenána chyba. Pokud `Condition` neexistuje parametr, se protokoluje chyby a sestavení zastaví provádění. Další informace o protokolování naleznete v tématu [protokoly o sestavení získání](../msbuild/obtaining-build-logs-with-msbuild.md).

Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Příklad
Následující příklad kódu ověřuje, že všechny požadované vlastnosti nastavené. Pokud nejsou nastavená, projektu vyvolá událost chyby a protokoly hodnotu `Text` parametr `Error` úloh.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    <Target Name="ValidateCommandLine">
        <Error
            Text=" The 0 property must be set on the command line."
            Condition="'$(0)' == ''" />
        <Error
            Text="The FREEBUILD property must be set on the command line."
            Condition="'$(FREEBUILD)' == ''" />
    </Target>
    ...
</Project>
```

## <a name="see-also"></a>Viz také:
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
- [Získání protokolů o sestavení](../msbuild/obtaining-build-logs-with-msbuild.md)
