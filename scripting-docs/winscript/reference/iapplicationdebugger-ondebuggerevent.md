---
title: IApplicationDebugger::onDebuggerEvent | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IApplicationDebugger.onDebuggerEvent
apilocation:
- scrobj.dll
helpviewer_keywords:
- IApplicationDebugger::onDebuggerEvent
ms.assetid: 82a5faaa-1222-4bf1-8569-10439dbdf16d
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7dec2cea6cfcf11cc756ef730f98feee9ed9bb0e
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54092674"
---
# <a name="iapplicationdebuggerondebuggerevent"></a>IApplicationDebugger::onDebuggerEvent
Zpracovává událost vlastní aplikace.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT onDebuggerEvent(  
   REFIID     riid,  
   IUnknown*  punk  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `riid`  
 [in] Identifikátor rozhraní objektu.  
  
 `punk`  
 [in] Objekt události, která implementuje rozhraní definované `riid`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`E_NOTIMPL`|Metoda teď není implementovaná.|  
  
## <a name="remarks"></a>Poznámky  
 Sémantika `IUnknown` je zcela definované aplikací/ladicí program.  
  
 Tato metoda umožňuje vlastní rozšíření ladicího programu modelu; teď není implementovaná.  
  
 Tato metoda je volána, když `IDebugApplication::FireDebuggerEvent` je volána.  
  
## <a name="see-also"></a>Viz také  
 [Iapplicationdebugger – rozhraní](../../winscript/reference/iapplicationdebugger-interface.md)   
 [IDebugApplication::FireDebuggerEvent](../../winscript/reference/idebugapplication-firedebuggerevent.md)