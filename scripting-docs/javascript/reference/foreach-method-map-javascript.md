---
title: foreach – metoda (Map) (JavaScript) | Microsoft Docs
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
ms.assetid: 9cdf0adc-77c7-4407-8ba7-ada0fb09e507
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 549d7d625fb4dfe88b2db69e6aa0ff66c7e90f66
ms.sourcegitcommit: 37144589d9f850ff81ec7bfb884429989925a43d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/19/2018
ms.locfileid: "34335798"
---
# <a name="foreach-method-map-javascript"></a>forEach – metoda (Map) (JavaScript)
Provede zadanou akci pro každý prvek v mapování.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
mapObj.forEach(callbackfn[, thisArg])  
```  
  
#### <a name="parameters"></a>Parametry  
 `mapObj`  
 Požadováno. A `Map` objektu.  
  
 `callbackfn`  
 Požadováno. Funkce, `forEach` volá jednou pro každý prvek v mapě. `callbackfn` přijme až tři argumenty. `forEach` volání `callbackfn` funkce jednou pro každý prvek v mapě.  
  
 `thisArg`  
 Volitelné. Objekt, `this` – klíčové slovo najdete v `callbackfn` funkce. Pokud `thisArg` je vynechán, `undefined` slouží jako `this` hodnotu.  
  
## <a name="exceptions"></a>Výjimky  
 Pokud `callbackfn` argument není objekt funkce `TypeError` je vyvolána výjimka.  
  
## <a name="remarks"></a>Poznámky  
 Syntaxe funkce zpětného volání je následující:  
  
 `function callbackfn(value, key, mapObj)`  
  
 Funkce zpětného volání je možné deklarovat pomocí až tři parametry, jak je znázorněno v následující tabulce.  
  
|Argument zpětného volání|Definice|  
|-----------------------|----------------|  
|`value`|Hodnota, obsažené v mapě.|  
|`key`|Klíč obsažené v mapě.|  
|`mapObj`|`Map` Objekt, který chcete procházet.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak načíst členy `Map` pomocí `forEach`.  
  
```JavaScript  
var m = new Map();  
m.set(1, "black");  
m.set(2, "red");  
m.set("colors", 2);  
m.set({x:1}, 3);  
  
m.forEach(function (value, key, mapObj) {  
    document.write(value.toString() + "<br />");  
});  
  
document.write("<br />");  
document.write(m.get(2));  
  
// Output:  
// black  
// red  
// 2  
// 3  
//  
// red  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]
