---
title: IDebugStackFrame3::InterceptCurrentException | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugStackFrame3::InterceptCurrentException
helpviewer_keywords: IDebugStackFrame3::InterceptCurrentException
ms.assetid: 116c7324-7645-4c15-b484-7a5cdd065ef5
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9631f2206705ef6daf36b355aa6cb1d5be6458d4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugstackframe3interceptcurrentexception"></a>IDebugStackFrame3::InterceptCurrentException
Voláno rozhraním ladicí program na aktuální rámec zásobníku, když chce intercept aktuální výjimku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT InterceptCurrentException(  
   INTERCEPT_EXCEPTION_ACTION dwFlags,  
   UINT64*                    pqwCookie  
);  
```  
  
```csharp  
int InterceptCurrentException(  
   uint dwFlags,   
   out  ulong pqwCookie  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwFlags`  
 [v] Určuje různé akce. V současné době pouze [INTERCEPT_EXCEPTION_ACTION](../../../extensibility/debugger/reference/intercept-exception-action.md) hodnota `IEA_INTERCEPT` je podporována a musí být zadán.  
  
 `pqwCookie`  
 [out] Identifikace konkrétní výjimka jedinečnou hodnotu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby.  
  
 Níže jsou uvedeny nejčastější vrátí chyba.  
  
|Chyba|Popis|  
|-----------|-----------------|  
|`E_EXCEPTION_CANNOT_BE_INTERCEPTED`|Nemůže být zachyceny aktuální výjimku.|  
|`E_EXCEPTION_CANNOT_UNWIND_ABOVE_CALLBACK`|Aktuální rámec provádění ještě nebyl byla prohledána pro obslužnou rutinu.|  
|`E_INTERCEPT_CURRENT_EXCEPTION_NOT_SUPPORTED`|Tato metoda není podporovaná pro tento snímek.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud je vyvolána výjimka, ladicí program získá kontrolu z čas spuštění na klíčové body během zpracování procesu výjimek. Během těchto klíčů situacích ladicího programu požádejte aktuální rámec zásobníku Pokud rámečku chce zachytávat výjimky. Tímto způsobem zachycené výjimky je v podstatě na průběžně obslužné rutiny výjimek pro rámce zásobníku, i v případě, že rámce zásobníku nemá obslužné rutiny výjimek (například bloku try/catch v kódu programu).  
  
 Po ladicího programu chce vědět, pokud by měl být zachyceny výjimku, zavolá tato metoda u aktuálního objektu rámce zásobníku. Tato metoda je zodpovědná za zpracování všech podrobností o výjimky. Pokud [IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md) rozhraní není implementováno nebo `InterceptStackException` metoda vrátí všechny chyby, bude ladicího programu pokračovat zpracování výjimky normálně.  
  
> [!NOTE]
>  Výjimky mohou být zachyceny jenom ve spravovaném kódu, který je při spuštění programu laděné v rozhraní .NET čas spuštění. Samozřejmě můžete implementovat třetích stran jazyk implementátory `InterceptStackException` ve vlastní moduly ladění, pokud se tak rozhodne.  
  
 Po dokončení zachycení [IDebugInterceptExceptionCompleteEvent2](../../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2.md) signalizace.  
  
## <a name="see-also"></a>Viz také  
 [IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md)   
 [INTERCEPT_EXCEPTION_ACTION](../../../extensibility/debugger/reference/intercept-exception-action.md)   
 [IDebugInterceptExceptionCompleteEvent2](../../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2.md)