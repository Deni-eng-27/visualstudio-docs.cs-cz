---
title: IScriptNode::Delete | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptNode.Delete
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptNode::Delete
ms.assetid: 6765ff80-a9a8-40a3-a669-7fcc284c87af
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cce802cc1a6d63001cfbed020592b30a9d8dab1b
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094793"
---
# <a name="iscriptnodedelete"></a>IScriptNode::Delete
Odstraní tento strom objektů.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Delete();  
```  
  
#### <a name="parameters"></a>Parametry  
 Metoda nemá žádné parametry.  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Po `Delete` metoda je volána, [IScriptNode::Alive](../../winscript/reference/iscriptnode-alive.md) metoda by měla zobrazovat tento skript uzel není aktivní.  
  
## <a name="see-also"></a>Viz také  
 [IScriptNode – rozhraní](../../winscript/reference/iscriptnode-interface.md)