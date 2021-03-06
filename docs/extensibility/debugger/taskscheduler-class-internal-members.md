---
title: TaskScheduler třída – interní členové | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- TaskScheduler class [.NET Framework debug engines]
- debug engines, TaskScheduler class [.NET Framework]
ms.assetid: 87f1c969-0217-4464-8907-7609c1bf61d3
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a53abc8b24edb06445c23c19744d00d50de8735d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80712566"
---
# <a name="taskscheduler-class---internal-members"></a>TaskScheduler třída – interní členy
Tento článek popisuje interní členy <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName> třídy, které vám pomůžou implementovat vlastní ladicí program. Obecné informace o této třídě naleznete v <xref:System.Threading.Tasks.TaskScheduler> referenčním článku.

 **Obor názvů:**<xref:System.Threading.Tasks?displayProperty=fullName>

 **Sestavení:** mscorlib (v *mscorlib.dll*)

 Vzhledem k tomu, že nemůžete získat přístup k těmto interním členům z .NET Framework, je k dispozici následující syntaxe v Common Intermediate Language (CIL).

## <a name="syntax"></a>Syntax

```csharp
.class public abstract auto ansi beforefieldinit System.Threading.Tasks.TaskScheduler
       extends System.Object
```

## <a name="members"></a>Členové

### <a name="methods"></a>Metody

|Název|Popis|
|----------|-----------------|
|[GetScheduledTasksForDebugger](../../extensibility/debugger/getscheduledtasksfordebugger-method.md)|Načte pole všech naplánovaných úloh.|
|[GetTaskSchedulersForDebugger](../../extensibility/debugger/gettaskschedulersfordebugger-method.md)|Načte pole všech <xref:System.Threading.Tasks.TaskScheduler> objektů, které jsou aktuálně aktivní.|

## <a name="remarks"></a>Poznámky

## <a name="see-also"></a>Viz také
- <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>
- [Vnitřní rozšíření pro .NET Framework](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)
