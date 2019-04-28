---
title: IDebugHelper::CreatePropertyBrowserEx | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugHelper.CreatePropertyBrowserEx
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugHelper::CreatePropertyBrowserEx
ms.assetid: 87ad322f-09da-4ce8-bb68-0b0bbeec645b
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 01e63d1588fd1e25f3415f22450ed5145752d711
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62979198"
---
# <a name="idebughelpercreatepropertybrowserex"></a>IDebugHelper::CreatePropertyBrowserEx
Vrátí prohlížeč vlastnost, která obtéká hodnotu typu VARIANT a umožňuje vlastní převod hodnot typu VARIANT nebo typy VARTYPE na řetězce.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT CreatePropertyBrowserEx(  
   VARIANT*                  pvar,  
   LPCOLESTR                 bstrName,  
   IDebugApplicationThread*  pdat,  
   IDebugFormatter*          pdf,  
   IDebugProperty**          ppdob  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pvar`  
 [in] Kořenový typ variant Procházet.  
  
 `bstrName`  
 [in] Název kořenové.  
  
 `pdat`  
 [in] Vlákno, na kterém chcete požadovat vlastnosti. Pokud tento parametr hodnotu NULL, se neprovádí žádné zařazení.  
  
 `pdf`  
 [in] Objekt, který poskytuje vlastní formátování pro varianty.  
  
 `ppdob`  
 [out] Prohlížeč vlastností.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vrátí prohlížeč vlastnost, která obtéká hodnotu typu VARIANT a umožňuje vlastní převod hodnot typu VARIANT nebo typy VARTYPE na řetězce.  
  
## <a name="see-also"></a>Viz také  
 [IDebugHelper::CreatePropertyBrowser](../../winscript/reference/idebughelper-createpropertybrowser.md)   
 [Idebughelper – rozhraní](../../winscript/reference/idebughelper-interface.md)   
 [IDebugProperty – rozhraní](../../winscript/reference/idebugproperty-interface.md)