---
title: "typeof – operátor (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: typeof_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: typeof operator
ms.assetid: ee8a1036-119f-486f-b034-b07bdba87f0c
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c79c69e6c447b14e61fa67ccb8600d5d83bebd2b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="typeof-operator-javascript"></a>typeof – operátor (JavaScript)
Vrátí řetězec, který určuje datový typ výrazu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
typeof[(]expression[)] ;  
```  
  
## <a name="remarks"></a>Poznámky  
 *Výraz* argument je jakýkoli výraz, který typ informace žádá.  
  
 `typeof` Operátor vrátí informace o typu jako řetězec. Šest možné hodnoty, které jsou `typeof` vrátí: "číslo", "řetězce," ",""objektu boolean," "funkce" a "undefined."  
  
 Jsou volitelné v závorkách `typeof` syntaxe.  
  
## <a name="example"></a>Příklad  
 Následující příklad testy s datovým typem proměnné.  
  
```JavaScript  
var index = 5;  
var result = (typeof index === 'number');  
// Output: true  
  
var description = "abc";  
var result = (typeof description === 'string');  
// Output: true  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad testů pro datový typ `undefined` pro deklarované a nedeklarované proměnné.  
  
```JavaScript  
var declared;  
var result = (declared === undefined);  
// Output: true  
  
var result = (typeof declared === 'undefined');  
// Output: true  
  
var result = (typeof notDeclared === 'undefined')  
// Output: true  
  
var obj = {};  
var result = (typeof obj.propNotDeclared === 'undefined');  
// Output: true  
  
// An undeclared variable cannot be used in a comparison without  
// the typeof operator, so the next line generates an error.  
//  var result = (notDeclared === undefined);  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Array.IsArray – funkce](../../javascript/reference/array-isarray-function-javascript.md)   
 [Object.getprototypeof – funkce](../../javascript/reference/object-getprototypeof-function-javascript.md)   
 [undefined – konstanta](../../javascript/reference/undefined-constant-javascript.md)   
 [Operátory porovnávání](../../javascript/reference/comparison-operators-javascript.md)   
 [Datové typy](../../javascript/data-types-javascript.md)   
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)