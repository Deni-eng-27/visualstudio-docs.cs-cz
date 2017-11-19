---
title: IDebugProgramPublisher2::PublishProgram | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramPublisher2::PublishProgram
helpviewer_keywords: IDebugProgramPublisher2::PublishProgram
ms.assetid: 92ff63f0-e869-4040-b3ae-b2c899e708ff
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9bcf9ee09a05e2de89a57670969325a8105fa014
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprogrampublisher2publishprogram"></a>IDebugProgramPublisher2::PublishProgram
Tato metoda umožňuje program, který je k dispozici pro ladění moduly (DEs) a správce ladicí relace.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT PublishProgram(  
   CONST_GUID_ARRAY Engines,  
   LPCOLESTR        szFriendlyName,  
   IUnknown*        pDebuggeeInterface  
);  
```  
  
```csharp  
int PublishProgram(  
   CONST_GUID_ARRAY Engines,  
   string           szFriendlyName,  
   object           pDebuggeeInterface  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `Engines`  
 [v] Pole identifikátory GUID pro DEs, které můžete spouštět nebo připojení k tomuto programu.  
  
 `szFriendlyName`  
 [v] Popisný název pro program (tím se zobrazí v nabídkách nebo dialogová okna uživateli).  
  
 `pDebuggeeInterface`  
 [v] `IUnknown` rozhraní programu (Tato hodnota se používá jako soubor cookie k jednoznačné identifikaci program; tento stejnou hodnotu slouží k "zrušit" programu)  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Chcete-li program již k dispozici pro ladění, volání [UnpublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogram.md).  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md)   
 [UnpublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogram.md)