---
title: IDebugCanStopEvent2::CanStop | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCanStopEvent2::CanStop
helpviewer_keywords:
- IDebugCanStopEvent2::CanStop
ms.assetid: 7d61adbe-6b3d-41f3-86a1-45d9cc01a7f8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 307b6d25f2e45276ead7c4b360ae191a01059104
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56716555"
---
# <a name="idebugcanstopevent2canstop"></a>IDebugCanStopEvent2::CanStop
Upozorní ladicího stroje (DE), jestli se mají zastavit na aktuální umístění v kódu nebo jenom pokračovat v provádění.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT CanStop ( 
   BOOL fCanStop
);
```

```csharp
int CanStop ( 
   int fCanStop
);
```

#### <a name="parameters"></a>Parametry
 `fCanStop`

 [in] Nenulová (`TRUE`), pokud by se měla zastavit DE do aktuálního umístění kódu; v opačném případě hodnotu (`FALSE`).

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Příjemce této události obvykle volá [getreason –](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md) metodu a zjistěte jeho důvod DE chce zastavit a pak zavolá `IDebugCanStopEvent2::CanStop` metodu s odpovídající odpověď.

 Pokud je DE zastaví, odešle událost, která popisuje důvody, proč zastavení. Obvykle existují dvě události, které jsou odeslány, uživatele nebo signál přerušení reprezentována [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md) rozhraní a reprezentována událost zarážky [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md) rozhraní.

## <a name="see-also"></a>Viz také
- [IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)
- [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)
- [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)
- [GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)