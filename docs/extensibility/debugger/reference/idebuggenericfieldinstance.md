---
title: IDebugGenericFieldInstance | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugGenericFieldInstance interface
ms.assetid: f68b4761-be8b-4801-9d4b-cde90e01d95e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b9da35f705f066e32c91a0dfc955d9f98104e8ab
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62919105"
---
# <a name="idebuggenericfieldinstance"></a>IDebugGenericFieldInstance
Představuje instanci pole pro obecný typ spravovaného kódu.

## <a name="syntax"></a>Syntaxe

```
IDebugGenericFieldInstance : IUnknown
```

## <a name="methods"></a>Metody
 Toto rozhraní implementuje následujících metod:

|Metoda|Popis|
|------------|-----------------|
|[GetTypeArguments](../../../extensibility/debugger/reference/idebuggenericfieldinstance-gettypearguments.md)|Načte argumenty parametrů typu pro tuto instanci.|
|[TypeArgumentCount](../../../extensibility/debugger/reference/idebuggenericfieldinstance-typeargumentcount.md)|Vrátí číslo typu parametru argumenty pro tuto instanci.|

## <a name="requirements"></a>Požadavky
 Záhlaví: Sh.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll