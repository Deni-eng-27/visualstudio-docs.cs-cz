---
title: IDebugProgram2::Execute | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::Execute
helpviewer_keywords:
- IDebugProgram2::Execute
ms.assetid: f7205ce8-0ac6-4fcd-b6ec-b720b4fcaccf
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 29839e2f2adb4a0e560b5b58d4226fd61596128c
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63412847"
---
# <a name="idebugprogram2execute"></a>IDebugProgram2::Execute
Dál spuštěním tohoto programu v zastaveném stavu. Vymazat všechny předchozí stav provádění (například krok), a program začne provádět znovu.

> [!NOTE]
> Tato metoda je zastaralá. Použití [Execute](../../../extensibility/debugger/reference/idebugprocess3-execute.md) metoda místo.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Execute(
   void
);
```

```csharp
int Execute();
```

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Když uživatel spustí provádění z zastaven jiným programem vlákno, tato metoda je volána v této aplikaci. Tato metoda je volána, i když uživatel vybere **Start** příkaz **ladění** nabídky v integrovaném vývojovém prostředí. Implementace této metody může být stejně jednoduché jako volání funkce [Resume](../../../extensibility/debugger/reference/idebugthread2-resume.md) metodu na aktuální vlákno v aplikaci.

> [!WARNING]
> Neodesílat událostí ukončení nebo okamžité (synchronní) události, která [události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) při zpracování tohoto volání; v opačném případě ladicí program může přestat reagovat.

## <a name="see-also"></a>Viz také
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)
- [Resume](../../../extensibility/debugger/reference/idebugthread2-resume.md)