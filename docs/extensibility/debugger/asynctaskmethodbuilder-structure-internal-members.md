---
title: AsyncTaskMethodBuilder struktura – interní členové | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debug engines, AsyncTaskMethodBuilder structure [.NET Framework]
- AsyncTaskMethodBuilder structure [.NET Framework debug engines]
ms.assetid: f32f5857-7ef8-45fd-8b5a-7f644eb98b11
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c918890551515ab9fadbf329d4c3ee96621c7aae
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80739372"
---
# <a name="asynctaskmethodbuilder-structure---internal-members"></a>AsyncTaskMethodBuilder struktura – interní členové
Toto téma popisuje interní členy <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder> třídy. Obecné informace o této třídě naleznete v <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder> referenčním tématu.

 **Obor názvů:**<xref:System.Runtime.CompilerServices?displayProperty=fullName>

 **Sestavení:** mscorlib (v mscorlib.dll)

 Vzhledem k tomu, že nemůžete získat přístup k těmto interním členům z .NET Framework, je k dispozici následující syntaxe v Common Intermediate Language (CIL).

## <a name="syntax"></a>Syntax

```csharp
.class public sequential ansi sealed beforefieldinit System.Runtime.CompilerServices.AsyncTaskMethodBuilder
       extends System.ValueType
       implements System.Runtime.CompilerServices.IAsyncMethodBuilder
```

## <a name="internal-members"></a>Interní členové

|Název|Popis|
|----------|-----------------|
|[Vlastnost ObjectIdForDebugger –](../../extensibility/debugger/asynctaskmethodbuilder-objectidfordebugger-property.md)|Získává objekt, který lze použít k jednoznačné identifikaci tohoto tvůrce do ladicího programu.|
|[m_builder pole](../../extensibility/debugger/asynctaskmethodbuilder-m-builder-field.md)|Představuje objekt obecného tvůrce, ke kterému nepatří tato neobecná instance.|

## <a name="see-also"></a>Viz také
- <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder>
- [Vnitřní rozšíření pro .NET Framework](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)
