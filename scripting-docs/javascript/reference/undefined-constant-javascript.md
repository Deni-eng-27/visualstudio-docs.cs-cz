---
title: "undefined – konstanta (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: undefined
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: undefined property
ms.assetid: 2a689d7d-00b0-48fb-9c95-5c2867bde006
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8ba7fa8b160e4f5d954c8d6545da5fae41c2f74b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="undefined-constant-javascript"></a>undefined – konstanta (JavaScript)
Hodnota, která nikdy byla definována, jako je například proměnné, která nebyla inicializována.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
undefined  
```  
  
## <a name="remarks"></a>Poznámky  
 `undefined` Konstanta, je členem skupiny `Global` objektu a jsou k dispozici po inicializaci skriptovacího stroje. Pokud proměnná byla deklarována, ale nebyla inicializována, jeho hodnota může **nedefinované**.  
  
 Pokud nebyl deklarován proměnné, nelze jej do porovnat `undefined`, ale můžete porovnat typ proměnné řetězec "undefined".  
  
 `undefined` Konstantní je užitečné v případě explicitně testování nebo nastavení proměnné na nedefinovaný.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `undefined` konstantní.  
  
```JavaScript  
// A variable that has not been initialized.  
var declared;  
  
if (declared == undefined)  
    document.write("declared has not been given a value <br/>");  
else  
    document.write("declared has been given a value <br/>");  
  
document.write("typeof declared is " + typeof(declared) + "<br/>");  
  
// An undeclared variable cannot be compared to undefined,  
// so the next line would generate an error.  
// if (notDeclared == undefined);  
  
document.write("typeof notDeclared is " + typeof(notDeclared));  
  
// Output:  
// declared has not been given a value  
// typeof declared is undefined  
// typeof notDeclared is undefined  
```  
  
## <a name="requirements"></a>Požadavky  
 `undefined` Vlastnost byla zavedena v [!INCLUDE[jsv55text](../../javascript/reference/includes/jsv55text-md.md)]a byl učiněn jen pro čtení v [!INCLUDE[jsv9textspecific](../../javascript/reference/includes/jsv9textspecific-md.md)].  
  
 **Platí pro**: [Global – objekt](../../javascript/reference/global-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [typeof – operátor](../../javascript/reference/typeof-operator-decrementjavascript.md)