---
title: THREADPROPERTY_FIELDS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- THREADPROPERTY_FIELDS
helpviewer_keywords:
- THREADPROPERTY_FIELDS enumeration
ms.assetid: 5b88acb9-03ea-4c29-a788-f0087dccbe23
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 9da7b995826b905af7faf6cac3fa0fc3d5ceba5e
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66316204"
---
# <a name="threadpropertyfields"></a>THREADPROPERTY_FIELDS
Určuje, jaké informace o vlákno má být načtena.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_THREADPROPERTY_FIELDS { 
   TPF_ID           = 0x0001,
   TPF_SUSPENDCOUNT = 0x0002,
   TPF_STATE        = 0x0004,
   TPF_PRIORITY     = 0x0008,
   TPF_NAME         = 0x0010,
   TPF_LOCATION     = 0x0020,
   TPF_ALLFIELDS    = 0xffffffff
};
typedef DWORD THREADPROPERTY_FIELDS;
```

```csharp
public enum enum_THREADPROPERTY_FIELDS { 
   TPF_ID           = 0x0001,
   TPF_SUSPENDCOUNT = 0x0002,
   TPF_STATE        = 0x0004,
   TPF_PRIORITY     = 0x0008,
   TPF_NAME         = 0x0010,
   TPF_LOCATION     = 0x0020,
   TPF_ALLFIELDS    = 0xffffffff
};
```

## <a name="fields"></a>Pole
 `TPF_ID`\
 Inicializace/použít `dwThreadId` pole [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md) struktury.

 `TPF_SUSPENDCOUNT`\
 Inicializace/použít `dwSuspendCount` pole `THREADPROPERTIE`struktura.

 `TPF_STATE`\
 Inicializace/použít `dwThreadState` pole `THREADPROPERTIE`struktura.

 `TPF_PRIORITY`\
 Inicializace/použít `bstrPriority` pole `THREADPROPERTIE`struktura.

 `TPF_NAME`\
 Inicializace/použít `bstrName` pole `THREADPROPERTIE`struktura.

 `TPF_LOCATION`\
 Inicializace/použít `bstrLocation` pole `THREADPROPERTIE`struktura.

 `TPF_ALLFIELDS`\
 Určuje všechna pole.

## <a name="remarks"></a>Poznámky
 Tyto hodnoty jsou předány jako argument [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md) indikace které pole [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md) struktury mají být inicializovány.

 Tyto hodnoty jsou také používány v `dwFields` člena `THREADPROPERTIES` struktury k označení pole, která se používá a je platný.

 Tyto příznaky lze kombinovat pomocí logické bitové `OR`.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)
- [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md)