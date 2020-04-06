---
title: IDebugThread2::CanSetNextStatement | Dokumenty společnosti Microsoft
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugThread2::CanSetNextStatement
helpviewer_keywords:
- IDebugThread2::CanSetNextStatement
ms.assetid: 7014af80-ff4f-4790-a34b-0528918d1fa3
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 4232c25bfe9acd7f17c88c28aa4211a9c62175f8
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/06/2020
ms.locfileid: "80718858"
---
# <a name="idebugthread2cansetnextstatement"></a>IDebugThread2::CanSetNextStatement
Určuje, zda lze aktuální ukazatel instrukce nastavit na daný rámec zásobníku.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT CanSetNextStatement ( 
   IDebugStackFrame2*  pStackFrame,
   IDebugCodeContext2* pCodeContext
);
```

```csharp
int CanSetNextStatement ( 
   IDebugStackFrame2  pStackFrame,
   IDebugCodeContext2 pCodeContext
);
```

## <a name="parameters"></a>Parametry
`pStackFrame`\
Vyhrazeno pro budoucí použití; nastavena na hodnotu null. Pokud se jedná o hodnotu null, použijte aktuální rámec zásobníku.

`pCodeContext`\
[v] Objekt [IDebugCodeContext2,](../../../extensibility/debugger/reference/idebugcodecontext2.md) který popisuje umístění kódu, které má být spuštěno, a jeho kontext.

## <a name="return-value"></a>Návratová hodnota
 V případě `S_OK`úspěchu vrátí ; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Pokud tato `S_OK`metoda vrátí , pak volání [SetNextStatement](../../../extensibility/debugger/reference/idebugthread2-setnextstatement.md) metoda skutečně nastavit další příkaz.

## <a name="see-also"></a>Viz také
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
- [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)
- [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)
- [SetNextStatement](../../../extensibility/debugger/reference/idebugthread2-setnextstatement.md)
