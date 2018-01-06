---
title: IDebugCanStopEvent2::GetDocumentContext | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugCanStopEvent2::GetDocumentContext
helpviewer_keywords: IDebugCanStopEvent2::GetDocumentContext
ms.assetid: 936a6c4e-30c5-4c7e-9ad5-910cc605a4b5
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 9d3f906c1dc1c019040f314204d3a4a423e1b8bf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcanstopevent2getdocumentcontext"></a>IDebugCanStopEvent2::GetDocumentContext
Získá kontext dokumentu, který popisuje umístění této události.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetDocumentContext (   
   IDebugDocumentContext2** ppDocCxt  
);  
```  
  
```csharp  
int GetDocumentContext (   
   out IDebugDocumentContext2 ppDocCxt  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppDocCxt`  
 [out] Vrátí [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) rozhraní, které představuje pozici ve zdrojovém dokumentu soubor odpovídající aktuální umístění kódu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Obecně platí kontext dokumentu lze považovat za pozici ve zdrojovém souboru.  
  
 Chcete-li získat kontext kód, který je zaměřen na kód pokyny, zavolejte [GetCodeContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getcodecontext.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)   
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [GetCodeContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getcodecontext.md)