---
title: "for... příkazu (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 7872b0b2-5701-4d72-9b52-ed13991542cc
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 47154261fd4817ba95b8884bd6482a87e044a5a4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="forof-statement-javascript"></a>for...of – příkaz (JavaScript)
Provede jeden nebo více příkazů pro každou hodnotu iterovat získané z iterable objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
for (variable of object) {  
    statements   
}  
```  
  
## <a name="parameters"></a>Parametry  
 `variable`  
 Požadováno. Proměnné, která může být libovolná hodnota vlastnosti z `object`.  
  
 `object`  
 Požadováno. Objekt iterable například `Array`, `Map`, `Set`, nebo objekt, který implementuje [iterator rozhraní](http://msdn.microsoft.com/en-us/3692355a-a703-4d43-8fb5-c03b4b7e8db1).  
  
 `statements`  
 Volitelné. Jeden nebo více příkazů do nelze provést pro každou hodnotu `object`. Může být složený příkaz.  
  
## <a name="remarks"></a>Poznámky  
 Na začátku každé iteraci smyčky, hodnota `variable` je další hodnota vlastnosti `object`.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `for...of` příkaz na pole.  
  
```JavaScript  
let arr = [ "fred", "tom", "bob" ];  
  
for (let i of arr) {  
    console.log(i);  
}  
  
// Output:  
// fred  
// tom  
// bob  
  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `for...of` příkaz na `Map` objektu.  
  
```JavaScript  
var m = new Map();  
m.set(1, "black");  
m.set(2, "red");  
  
for (var n of m) {  
  console.log(n);  
}  
  
// Output:  
// 1,black  
// 2,red  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [for... v příkazu](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md)   
 [for – příkaz](../../javascript/reference/for-statement-javascript.md)   
 [while – příkaz](../../javascript/reference/while-statement-javascript.md)