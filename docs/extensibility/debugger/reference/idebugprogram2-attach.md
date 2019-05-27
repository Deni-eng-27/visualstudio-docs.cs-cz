---
title: IDebugProgram2::Attach | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::Attach
helpviewer_keywords:
- IDebugProgram2::Attach
ms.assetid: de069fbf-a565-4905-b102-f5658c55aacd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: c5e6debcc761872295e21dd17023d24429870e02
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66200436"
---
# <a name="idebugprogram2attach"></a>IDebugProgram2::Attach
Připojí se k programu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Attach( 
   IDebugEventCallback2* pCallback
);
```

```csharp
int Attach( 
   IDebugEventCallback2 pCallback
);
```

## <a name="parameters"></a>Parametry
`pCallback`\
[in] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) objektu použitého pro oznamování událostí ladění.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. V následující tabulce jsou uvedeny některé možné kódy chyb.

|Value|Popis|
|-----------|-----------------|
|`E_ATTACH_DEBUGGER_ALREADY_ATTACHED`|Zadaný program je již připojen k ladicímu programu.|
|`E_ATTACH_DEBUGGEE_PROCESS_SECURITY_VIOLATION`|Během procesu připojení došlo k porušení zabezpečení.|
|`E_ATTACH_CANNOT_ATTACH_TO_DESKTOP`|Desktopovému programu nelze připojit k ladicímu programu.|

## <a name="remarks"></a>Poznámky
 Ladicí stroj (DE) nikdy volá tuto metodu za účelem připojení k programu. Pokud DE běží v adresním prostoru programu, [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) metoda je volána. Pokud testy DE na správce ladění relace (SDM) adresní prostor, [připojit](../../../extensibility/debugger/reference/idebugengine2-attach.md) metoda je volána.

## <a name="see-also"></a>Viz také:
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)
- [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)
- [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)