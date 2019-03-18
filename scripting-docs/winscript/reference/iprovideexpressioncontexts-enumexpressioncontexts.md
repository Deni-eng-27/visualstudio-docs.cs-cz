---
title: IProvideExpressionContexts::EnumExpressionContexts | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IProvideExpressionContexts.EnumExpressionContexts
apilocation:
- jscript.dll
helpviewer_keywords:
- IProvideExpressionContexts::EnumExpressionContexts
ms.assetid: ec5f0065-00df-41e6-b480-4c04ba464872
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d1e4c462780f7026329ff7a5d22c86dbb6058dc5
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58157747"
---
# <a name="iprovideexpressioncontextsenumexpressioncontexts"></a>IProvideExpressionContexts::EnumExpressionContexts
Vrátí enumerátor výraz kontexty platná pro tuto součást.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT EnumExpressionContexts(  
   IEnumDebugExpressionContexts**  ppedec  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppedec`  
 [out] Enumerátor výraz kontexty platná pro tuto součást.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Správce ladění procesu tato metoda používá k nalezení všech kontextech globálního výraz přidružený k dané vlákno.  
  
> [!NOTE]
>  Tato metoda je volána z vlákna, které vás zajímají. Záleží implementátora identifikovat aktuální vlákno a vrátí odpovídající enumerátor.  
  
## <a name="see-also"></a>Viz také  
 [IProvideExpressionContexts – rozhraní](../../winscript/reference/iprovideexpressioncontexts-interface.md)