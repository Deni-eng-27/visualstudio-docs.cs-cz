---
title: Třída Task – interní členové | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debug engines, Task class [.NET Framework]
- Task class [.NET Framework debug engines]
ms.assetid: 28e47c3b-9323-424a-80ac-6cc3bf19e09b
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: dcf278c0248b344cea4be7cf161ecc91581f5f2e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80712737"
---
# <a name="task-class---internal-members"></a>Třída Task – interní členy
Tento článek popisuje interní členy <xref:System.Threading.Tasks.Task?displayProperty=fullName> třídy, které vám pomůžou implementovat vlastní ladicí program. Obecné informace o této třídě naleznete v <xref:System.Threading.Tasks.Task> referenčním článku.

 **Obor názvů:**<xref:System.Threading.Tasks?displayProperty=fullName>

 **Sestavení:** mscorlib (v *mscorlib.dll*)

 Vzhledem k tomu, že nemůžete získat přístup k těmto interním členům z .NET Framework, je k dispozici následující syntaxe v Common Intermediate Language (CIL).

## <a name="syntax"></a>Syntax

```csharp
.class public auto ansi System.Threading.Tasks.Task
       extends System.Object
       implements System.Threading.IThreadPoolWorkItem,
                  System.IAsyncResult,
                  System.IDisposable,
                  System.Threading.ICancelableOperation
```

## <a name="members"></a>Členové

### <a name="methods"></a>Metody

|Název|Popis|
|----------|-----------------|
|[SetNotificationForWaitCompletion – metoda](../../extensibility/debugger/setnotificationforwaitcompletion-method.md)|Nastaví nebo vymaže bit stavu TASK_STATE_WAIT_COMPLETION_NOTIFICATION.|
|[NotifyDebuggerOfWaitCompletion – metoda](../../extensibility/debugger/notifydebuggerofwaitcompletion-method.md)|Zástupná metoda použitá jako cíl zarážky v ladicím programu.|

### <a name="fields"></a>Pole

|Název|Popis|
|----------|-----------------|
|[m_action](../../extensibility/debugger/m-action-field.md)|Delegát, který představuje kód, který má být spuštěn v <xref:System.Threading.Tasks.Task> objektu.|
|[m_contingentProperties](../../extensibility/debugger/m-contingentproperties-field.md)|Ukládá další vlastnosti <xref:System.Threading.Tasks.Task> objektu.|
|[m_parent](../../extensibility/debugger/m-parent-field.md)|Pole zálohování pro <xref:System.Threading.Tasks.Task?displayProperty=fullName> nadřazenou vlastnost|
|[m_stateFlags](../../extensibility/debugger/m-stateflags-field.md)|Ukládá informace o aktuálním stavu <xref:System.Threading.Tasks.Task> objektu.|
|[m_stateObject](../../extensibility/debugger/m-stateobject-field.md)|Objekt, který představuje data, která bude použita akcí.|
|[m_taskId](../../extensibility/debugger/m-taskid-field.md)|Pole pro zálohování pro <xref:System.Threading.Tasks.Task.Id%2A?displayProperty=fullName> vlastnost.|
|[s_taskIdCounter](../../extensibility/debugger/s-taskidcounter-field.md)|Další dostupný identifikátor <xref:System.Threading.Tasks.Task> objektu.|
|[TASK_STATE_CANCELED](../../extensibility/debugger/task-state-canceled-field.md)|Indikuje, že se úloha zrušila před tím, než se dorazila do běžícího stavu, nebo jestli úloha potvrdila zrušení a dokončení bez výjimky.|
|[TASK_STATE_EXECUTED](../../extensibility/debugger/task-state-executed-field.md)|Indikuje, že je úloha spuštěná.|
|[TASK_STATE_FAULTED](../../extensibility/debugger/task-state-faulted-field.md)|Označuje, že úloha byla dokončena z důvodu neošetřené výjimky.|
|[TASK_STATE_RAN_TO_COMPLETION](../../extensibility/debugger/task-state-ran-to-completion-field.md)|Indikuje, že se úspěšně dokončilo provádění úlohy.|
|[TASK_STATE_WAITING_ON_CHILDREN](../../extensibility/debugger/task-state-waiting-on-children-field.md)|Označuje, že úloha dokončila provádění delegáta a implicitně čeká na dokončení připojených podřízených úloh.|

## <a name="remarks"></a>Poznámky
 Následující interní metody jsou užitečné pro modul ladicího programu, protože označují počátek <xref:System.Threading.Tasks.Task> provádění kódu:

- `Execute`

- `ExecuteEntry`

- `ExecuteWithThreadLocal`

- `Finish`

- `InnerInvoke`

- `InternalWait`

## <a name="see-also"></a>Viz také
- <xref:System.Threading.Tasks.Task?displayProperty=fullName>
- [Vnitřní rozšíření pro .NET Framework](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)
