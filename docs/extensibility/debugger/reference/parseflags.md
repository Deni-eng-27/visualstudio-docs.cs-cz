---
title: PARSEFLAGS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PARSEFLAGS
helpviewer_keywords: PARSEFLAGS enumeration
ms.assetid: 47943f0a-54cb-4493-a62e-5dba97bd4c35
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9c96eb60c397093fb5ec3291a0b02ee7cbd07e34
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="parseflags"></a>PARSEFLAGS
Určuje, jak analyzovat výraz.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_PARSEFLAGS {   
   PARSE_EXPRESSION            = 0x0001,  
   PARSE_FUNCTION_AS_ADDRESS   = 0x0002,  
   PARSE_DESIGN_TIME_EXPR_EVAL = 0x1000  
};  
typedef DWORD PARSEFLAGS;  
```  
  
```csharp  
public enum enum_PARSEFLAGS {   
   PARSE_EXPRESSION            = 0x0001,  
   PARSE_FUNCTION_AS_ADDRESS   = 0x0002,  
   PARSE_DESIGN_TIME_EXPR_EVAL = 0x1000  
};  
```  
  
## <a name="members"></a>Členové  
 PARSE_EXPRESSION  
 Označuje, že výraz není příkaz.  
  
 PARSE_FUNCTION_AS_ADDRESS  
 Označuje, že výraz je možné analyzovat (a později vyhodnotit) jako adresa.  
  
 PARSE_DESIGN_TIME_EXPR_EVAL  
 Určuje, zda výraz analyzuje během doby návrhu (to znamená, když je návrháře otevřít).  
  
## <a name="remarks"></a>Poznámky  
 Předá jako parametr, který se [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) a [analyzovat](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) metody.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)   
 [Analyzovat](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md)