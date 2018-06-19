---
title: IDebugEngine2::CreatePendingBreakpoint | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngine2::CreatePendingBreakpoint
helpviewer_keywords:
- IDebugEngine2::CreatePendingBreakpoint
ms.assetid: 92e85b90-a931-48d9-89a7-a6edcb83ae5a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6a0813e077d8bdc2ba024dc932a6cb571b1b2fed
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31107774"
---
# <a name="idebugengine2creatependingbreakpoint"></a>IDebugEngine2::CreatePendingBreakpoint
Vytvoří čekající zarážek v modulu ladění (DE).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT CreatePendingBreakpoint(   
   IDebugBreakpointRequest2*  pBPRequest,  
   IDebugPendingBreakpoint2** ppPendingBP  
);  
```  
  
```csharp  
int CreatePendingBreakpoint(   
   IDebugBreakpointRequest2     pBPRequest,  
   out IDebugPendingBreakpoint2 ppPendingBP  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pBPRequest`  
 [v] [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md) objekt, který popisuje čekající zarážek vytvořit.  
  
 `ppPendingBP`  
 [out] Vrátí [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) objekt, který reprezentuje čekající zarážek.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby. Obvykle vrátí `E_FAIL` Pokud `pBPRequest` parametr neodpovídá žádný jazyk podporuje DE, pokud `pBPRequest` parametru je neplatná nebo nekompletní.  
  
## <a name="remarks"></a>Poznámky  
 Čekající zarážek je kolekce všechny informace potřebné k vytvoření vazby zarážku kódu. Čekající zarážek tato metoda vrátí není vázán na kód, dokud [vazby](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md) metoda je volána.  
  
 Pro každou čekající na vyřízení zarážek sady uživatele správce ladicí relace (SDM) volá tuto metodu v každé připojené DE. Je DE k ověřte, zda je platný pro aplikace spuštěné v této DE zarážku.  
  
 Pokud uživatel nastaví zarážku na řádek kódu, DE je zdarma vytvořit vazbu zarážek na nejbližší řádek v dokumentu, který odpovídá tento kód. To umožňuje uživatelům nastavit bod přerušení na první řádek Víceřádkový příkazu, ale vazbu na posledním řádku (kde všechny kód je nastavený atribut v informace o ladění).  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak implementovat tuto metodu pro jednoduchou `CProgram` objektu. Implementace je DE `IDebugEngine2::CreatePendingBreakpoint` pak může předávat všechna volání Tato implementace metody v každém programu.  
  
```  
HRESULT CProgram::CreatePendingBreakpoint(IDebugBreakpointRequest2* pBPRequest, IDebugPendingBreakpoint2** ppPendingBP)     
{    
  
   // Create and initialize the CPendingBreakpoint object.  
   CComObject<CPendingBreakpoint> *pPending;    
   CComObject<CPendingBreakpoint>::CreateInstance(&pPending);    
   pPending->Initialize(pBPRequest, m_pInterp, m_pCallback, m_pEngine);    
   return pPending->QueryInterface(ppPendingBP);    
}    
```  
  
## <a name="see-also"></a>Viz také  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [Vazby](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)   
 [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)   
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)