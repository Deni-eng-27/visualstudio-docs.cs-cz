---
title: IApplicationDebuggerUI::BringDocumentContextToTop | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IApplicationDebuggerUI.BringDocumentContextToTop
apilocation:
- scrobj.dll
helpviewer_keywords:
- IApplicationDebuggerUI::BringDocumentContextToTop
ms.assetid: 7844217d-658b-42af-8d10-2714f4eded20
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 890cc1b6c38f44c4140274dcaa19deff1fd276e2
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095508"
---
# <a name="iapplicationdebuggeruibringdocumentcontexttotop"></a>IApplicationDebuggerUI::BringDocumentContextToTop
Zobrazí se okno obsahující daný dokument kontext do horní části v uživatelském rozhraní ladicího programu a posune okno kontextu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT BringDocumentContextToTop(  
   IDebugDocumentContext*  pddc  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pddc`  
 [in] Kontext dokumentu, aby si přenesli do horní části v uživatelském rozhraní ladicího programu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`E_INVALIDARG`|Kontext určeného `pddc` není znám.|  
  
## <a name="remarks"></a>Poznámky  
 Tuto metodu, zobrazí se okno obsahující daný dokument kontext do horní části v uživatelském rozhraní ladicího programu a posune okno kontextu.  
  
## <a name="see-also"></a>Viz také  
 [IApplicationDebuggerUI – rozhraní](../../winscript/reference/iapplicationdebuggerui-interface.md)