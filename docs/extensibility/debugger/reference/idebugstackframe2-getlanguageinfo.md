---
title: IDebugStackFrame2::GetLanguageInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugStackFrame2::GetLanguageInfo
helpviewer_keywords:
- IDebugStackFrame2::GetLanguageInfo
ms.assetid: 0e12fd92-f155-46a7-8272-cda279388cfb
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 12e27e744d13ce24f90a4c97ea242cecf8a843d5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugstackframe2getlanguageinfo"></a>IDebugStackFrame2::GetLanguageInfo
Získá jazyk přidružené k této rámce zásobníku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetLanguageInfo (   
   BSTR* pbstrLanguage,  
   GUID* pguidLanguage  
);  
```  
  
```csharp  
int GetLanguageInfo (   
   ref string pbstrLanguage,  
   ref Guid   pguidLanguage  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pbstrLanguage`  
 [out] Vrátí název jazyka, který implementuje metodu spojenou s Tento rámce zásobníku.  
  
 `pguidLanguage`  
 [out] Vrátí `GUID` jazyka. Pro [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] jazyky, například následující mohou být vráceny:  
  
-   `guidVBScriptLang`  
  
-   `guidJScriptLang`  
  
-   `guidCPPLang`  
  
-   `guidVBLang`  
  
-   `guidSQLLang`  
  
-   `guidScriptLang`  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)