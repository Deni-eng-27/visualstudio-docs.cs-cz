---
title: IDebugThread2::SetNextStatement | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugThread2::SetNextStatement
helpviewer_keywords:
- IDebugThread2::SetNextStatement
ms.assetid: 9e2834dd-4ecf-45af-8e6c-f9318ebdac06
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 0b6aca1ef95a8ae88301181955828f08c7c38bed
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2019
ms.locfileid: "65226703"
---
# <a name="idebugthread2setnextstatement"></a>IDebugThread2::SetNextStatement
Nastaví aktuální ukazatel příkazu v kontextu daného kódu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT SetNextStatement ( 
   IDebugStackFrame2*  pStackFrame,
   IDebugCodeContext2* pCodeContext
);
```

```csharp
int SetNextStatement ( 
   IDebugStackFrame2  pStackFrame,
   IDebugCodeContext2 pCodeContext
);
```

## <a name="parameters"></a>Parametry
 `pStackFrame`\
 Vyhrazeno pro budoucí použití; Nastavte na hodnotu null.

 `pCodeContext`\

 [in] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) objekt, který popisuje umístění se pokračovalo v kódu a jeho kontext.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. V následující tabulce jsou uvedeny další možné hodnoty.

|Value|Popis|
|-----------|-----------------|
|E_CANNOT_SET_NEXT_STATEMENT_ON_NONLEAF_FRAME|Následující příkaz nelze v zásobníku hlouběji v zásobníku rámce.|
|E_CANNOT_SETIP_TO_DIFFERENT_FUNCTION|Další příkaz není přidružené žádné rámce v zásobníku.|
|E_CANNOT_SET_NEXT_STATEMENT_ON_EXCEPTION|Některé ladicí stroj nelze nastavit další příkaz po výjimce.|

## <a name="remarks"></a>Poznámky
 Ukazatele na instrukci označuje další instrukci nebo příkaz ke spuštění. Tato metoda se používá, zkuste řádek zdrojového kódu nebo vynutit spuštění, abyste mohli pokračovat v jiné funkci, třeba.

## <a name="see-also"></a>Viz také:
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
- [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)
- [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)