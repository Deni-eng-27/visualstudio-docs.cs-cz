---
title: set – metoda (WeakMap) (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 29fc72b1-224f-4f19-8c06-5d926d695b03
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c916bda13c7bd973b37c4e4cb6b81e327ee5de54
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791388"
---
# <a name="set-method-weakmap-javascript"></a>set – metoda (WeakMap) (JavaScript)
Přidá nového elementu `WeakMap` objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
weakmapObj.set(key, value)  
```  
  
#### <a name="parameters"></a>Parametry  
 `weakmapObj`  
 Požadováno. A `WeakMap` objektu.  
  
 `key`  
 Požadováno. Objekt představující klíč elementu, který chcete přidat. Toto musí být odkaz na objekt.  
  
 `value`  
 Požadováno. Hodnota elementu, který chcete přidat.  
  
## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota  
 Vrátí `WeakMap` objekt, který obsahuje nový pár klíč/hodnota.  
  
## <a name="remarks"></a>Poznámky  
 Pokud přidáte do kolekce pomocí existujícího klíče hodnotu, nová hodnota nahradí původní hodnoty.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak přidávat členy do `WeakMap` objektu.  
  
```JavaScript  
var dog = {  
    breed: "yorkie"  
}  
  
var cat = {  
    breed: "burmese"  
}  
  
var wm = new WeakMap();  
wm.set(dog, "fido");  
wm.set(cat, "pepper");  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]