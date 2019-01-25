---
title: IDebugThread2::SetNextStatement | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugThread2::SetNextStatement
helpviewer_keywords:
- IDebugThread2::SetNextStatement
ms.assetid: 9e2834dd-4ecf-45af-8e6c-f9318ebdac06
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 755044ec1d713075c1c1fd3165254ba192943288
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54789441"
---
# <a name="idebugthread2setnextstatement"></a>IDebugThread2::SetNextStatement
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nastaví aktuální ukazatel příkazu v kontextu daného kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
  
#### <a name="parameters"></a>Parametry  
 `pStackFrame`  
 Vyhrazeno pro budoucí použití; Nastavte na hodnotu null.  
  
 `pCodeContext`  
 [in] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) objekt, který popisuje umístění se pokračovalo v kódu a jeho kontext.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. V následující tabulce jsou uvedeny další možné hodnoty.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|E_CANNOT_SET_NEXT_STATEMENT_ON_NONLEAF_FRAME|Následující příkaz nelze v zásobníku hlouběji v zásobníku rámce.|  
|E_CANNOT_SETIP_TO_DIFFERENT_FUNCTION|Další příkaz není přidružené žádné rámce v zásobníku.|  
|E_CANNOT_SET_NEXT_STATEMENT_ON_EXCEPTION|Některé ladicí stroj nelze nastavit další příkaz po výjimce.|  
  
## <a name="remarks"></a>Poznámky  
 Ukazatele na instrukci označuje další instrukci nebo příkaz ke spuštění. Tato metoda se používá, zkuste řádek zdrojového kódu nebo vynutit spuštění, abyste mohli pokračovat v jiné funkci, třeba.  
  
## <a name="see-also"></a>Viz také  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)
