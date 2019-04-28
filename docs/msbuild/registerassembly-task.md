---
title: Registerassembly – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#RegisterAssembly
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, RegisterAssembly task
- RegisterAssembly task [MSBuild]
ms.assetid: ba5f19ac-6764-4d28-9b79-a86de58f8987
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7d9ebe23cab26d6a90e16623917b61d261ed12f5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62974641"
---
# <a name="registerassembly-task"></a>RegisterAssembly – úloha
Načte metadata v rámci zadaného sestavení a přidá nezbytné položky registru, které umožní klientům modelu COM vytvořit [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] třídy transparentně. Chování této úlohy je podobné, ale nejsou identické, která [Regasm.exe (Nástroj registrace sestavení)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool).

## <a name="parameters"></a>Parametry
 Následující tabulka popisuje parametry `RegisterAssembly` úloh.

|Parametr|Popis|
|---------------|-----------------|
|`Assemblies`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Určuje sestavení, které chcete být registrována pomocí modelu COM.|
|`AssemblyListFile`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Obsahuje informace o stavu mezi `RegisterAssembly` úloh a [unregisterassembly –](../msbuild/unregisterassembly-task.md) úloh. Tyto informace brání `UnregisterAssembly` úloh v pokusu o zrušení registrace sestavení, které se nepodařilo zaregistrovat v `RegisterAssembly` úloh.|
|`CreateCodeBase`|Volitelné `Boolean` parametru.<br /><br /> Pokud `true`, vytvoří položku základu kódu v registru, který určuje cestu k souboru pro sestavení, která není nainstalována v globální mezipaměti sestavení. Tuto možnost byste neměli zadávat, pokud následně instalujete sestavení, které budete registrovat do globální mezipaměti sestavení (GAC).|
|`TypeLibFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Určuje knihovnu typů, chcete-li generovat z určeného sestavení. Vygenerovanou knihovnu typů obsahuje definice dostupných typů definovaných v rámci sestavení. Knihovnu typů se vygeneruje pouze tehdy, pokud platí jedna z následujících podmínek:<br /><br /> -Knihovnu typů s tímto názvem neexistuje v tomto umístění.<br />-Existuje knihovnu typů, ale je starší než předávaný v sestavení.<br /><br /> Pokud je novější než předávaný sestavení knihovny typů, se nevytvoří nový, ale sestavení bude pořád zaregistrovaný.<br /><br /> Pokud tento parametr zadán, musí mít stejný počet položek, jako `Assemblies` parametr nebo úloha se nezdaří. Pokud nejsou zadány žádné vstupy, úloha se jako výchozí název sestavení a změňte příponu položky, která se *.tlb*.|

## <a name="remarks"></a>Poznámky
 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Příklad
 V následujícím příkladu `RegisterAssembly` úloh k registraci sestavení určené parametrem `MyAssemblies` kolekci položek.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <ItemGroup>
        <MyAssemblies Include="MyAssembly.dll" />
    <ItemGroup>

    <Target Name="RegisterAssemblies">
        <RegisterAssembly
            Assemblies="@(MyAssemblies)" >
    </Target>

</Project>
```

## <a name="see-also"></a>Viz také:
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)