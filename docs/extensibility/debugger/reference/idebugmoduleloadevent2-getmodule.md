---
title: IDebugModuleLoadEvent2::GetModule | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugModuleLoadEvent2::GetModule
helpviewer_keywords:
- IDebugModuleLoadEvent2::GetModule
ms.assetid: c86482bb-9ce5-4e63-bbe0-969b50169424
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 2d6f6672349d6a37d0f7b5e43c9a68d765d3abc7
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66203001"
---
# <a name="idebugmoduleloadevent2getmodule"></a>IDebugModuleLoadEvent2::GetModule
Získá modul, který je načten nebo byla uvolněna.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetModule( 
   IDebugModule2** pModule,
   BSTR*           pbstrDebugMessage,
   BOOL*           pbLoad
);
```

```csharp
int GetModule( 
   out IDebugModule2 pModule,
   ref string        pbstrDebugMessage,
   ref int           pbLoad
);
```

## <a name="parameters"></a>Parametry
`pModule`\
[out] Vrátí [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) objekt, který představuje modul, který je načítání nebo uvolnění.

`pbstrDebugMessage`\
[out v] Vrátí volitelnou zprávu s popisem této události. Pokud je tento parametr hodnotu null, je požadována žádná zpráva.

`pbLoad`\
[out v] Nenulová (`TRUE`) Pokud modul je nula a načítání (`FALSE`) Pokud uvolnění modulu. Pokud je tento parametr hodnotu null, je požadována bez stavu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také:
- [IDebugModuleLoadEvent2](../../../extensibility/debugger/reference/idebugmoduleloadevent2.md)
- [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)