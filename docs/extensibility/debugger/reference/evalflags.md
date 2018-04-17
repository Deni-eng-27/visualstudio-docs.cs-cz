---
title: EVALFLAGS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- EVALFLAGS
helpviewer_keywords:
- EVALFLAGS enumeration
ms.assetid: 7b2cb14a-511a-4fef-9e4f-308139719fba
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7c718414749bb6c748f25fb90837644fe984a274
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="evalflags"></a>EVALFLAGS
Určuje příznaky, které řídí vyhodnocení výrazu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_EVALFLAGS {  
   EVAL_RETURNVALUE = 0x0002,  
   EVAL_NOSIDEEFFECTS = 0x0004,  
   EVAL_ALLOWBPS = 0x0008,  
   EVAL_ALLOWERRORREPORT = 0x0010,  
   EVAL_FUNCTION_AS_ADDRESS = 0x0040,  
   EVAL_NOFUNCEVAL = 0x0080,  
   EVAL_NOEVENTS = 0x1000  
};  
typedef DWORD EVALFLAGS;  
```  
  
```csharp  
public enum enum_EVALFLAGS {  
   EVAL_RETURNVALUE = 0x0002,  
   EVAL_NOSIDEEFFECTS = 0x0004,  
   EVAL_ALLOWBPS = 0x0008,  
   EVAL_ALLOWERRORREPORT = 0x0010,  
   EVAL_FUNCTION_AS_ADDRESS = 0x0040,  
   EVAL_NOFUNCEVAL = 0x0080,  
   EVAL_NOEVENTS = 0x1000  
}  
```  
  
## <a name="members"></a>Členové  
 EVAL_RETURNVALUE  
 Určuje, že návratovou hodnotu, pokud existuje, vyhodnotí.  
  
 EVAL_NOSIDEEFFECTS  
 Určuje, že nebyla povolen vedlejší účinky.  
  
 EVAL_ALLOWBPS  
 Určuje zastavení zarážky.  
  
 EVAL_ALLOWERRORREPORT  
 Určuje zpráv o chybách k hostiteli mají být povolena. Používá se především pro vyhodnocení výrazu ve skriptu v aplikaci Internet Explorer.  
  
 EVAL_FUNCTION_AS_ADDRESS  
 Vynutí funkce, který se má vyhodnotit jako adresy místo vyvolání funkce.  
  
 EVAL_NOFUNCEVAL  
 Zabrání vyhodnocovaný funkce. Představte si třeba `int` tokenu ve výrazu `myExpression(int) + 10`. Tuto funkci lze správně vyhodnotit jako adresu, ale ne jako hodnotu.  
  
 EVAL_NOEVENTS  
 Příznak, který označuje, že by se neměly posílat události, které nastaly během vyhodnocování výrazu, správce ladicí relace (SDM) nebo rozhraní IDE.  
  
## <a name="remarks"></a>Poznámky  
 Tyto příznaky jsou předávány jako argument pro [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) a [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) metody.  
  
 Tyto příznaky může být kombinován s bitové operace OR.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)