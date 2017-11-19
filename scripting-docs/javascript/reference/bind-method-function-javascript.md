---
title: "BIND – metoda (Function) (JavaScript) | Microsoft Docs"
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
helpviewer_keywords:
- parameters [JavaScript], bind method
- arguments [JavaScript], bind method
- bind method [JavaScript]
- this keyword [JavaScript], bind method
ms.assetid: 28946f47-b758-48cf-b508-610a0f2f6e19
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dd7fc752df9bd41f8625ac2cb484486dfd19558d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="bind-method-function-javascript"></a>bind – metoda (Function) (JavaScript)
Vytvoří pro danou funkci vázanou funkci, která má stejné tělo jako původní funkce. Ve funkci vázané `this` přeloží objektu na objekt předaný. Vázaná funkce má určené počáteční parametry.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
function.bind(thisArg[,arg1[,arg2[,argN]]])  
```  
  
#### <a name="parameters"></a>Parametry  
 `function`  
 Požadováno. Objekt funkce.  
  
 `thisArg`  
 Požadováno. Objekt, ke kterému `this` – klíčové slovo najdete v nové funkce.  
  
 `arg1`[,`arg2`[,`argN`]]]  
 Volitelné. Seznam argumentů, které mají být předány do nové funkce.  
  
## <a name="return-value"></a>Návratová hodnota  
 Nové funkce, která je stejná jako `function` funkce, s výjimkou `thisArg` objekt a počáteční argumenty.  
  
## <a name="exceptions"></a>Výjimky  
 Pokud zadaný `function` není funkce, `TypeError` je vyvolána výjimka.  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje způsob použití `bind` metoda.  
  
```JavaScript  
// Define the original function.  
var checkNumericRange = function (value) {  
    if (typeof value !== 'number')  
        return false;  
    else  
        return value >= this.minimum && value <= this.maximum;  
}  
  
// The range object will become the this value in the callback function.  
var range = { minimum: 10, maximum: 20 };  
  
// Bind the checkNumericRange function.  
var boundCheckNumericRange = checkNumericRange.bind(range);  
  
// Use the new function to check whether 12 is in the numeric range.  
var result = boundCheckNumericRange (12);  
document.write(result);  
  
// Output: true  
```  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu `thisArg` objektu se liší od objektu, která obsahuje původní metody.  
  
```JavaScript  
// Create an object that contains the original function.  
var originalObject = {  
    minimum: 50,  
    maximum: 100,  
    checkNumericRange: function (value) {  
        if (typeof value !== 'number')  
            return false;  
        else  
            return value >= this.minimum && value <= this.maximum;  
    }  
}  
  
// Check whether 10 is in the numeric range.  
var result = originalObject.checkNumericRange(10);  
document.write(result + " ");  
// Output: false  
  
// The range object supplies the range for the bound function.  
var range = { minimum: 10, maximum: 20 };  
  
// Create a new version of the checkNumericRange function that uses range.  
var boundObjectWithRange = originalObject.checkNumericRange.bind(range);  
  
// Check whether 10 is in the numeric range.  
var result = boundObjectWithRange(10);  
document.write(result);  
// Output: true  
```  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje způsob použití `arg1[,arg2[,argN]]]` argumenty. Používá funkci vázané parametry zadané v `bind` metoda jako první a druhý parametr. Jakékoli parametry zadané při volání vázané funkce jsou použity jako třetí, čtvrtý (atd.) parametr.  
  
```JavaScript  
// Define the original function with four parameters.  
var displayArgs = function (val1, val2, val3, val4) {  
    document.write(val1 + " " + val2 + " " + val3 + " " + val4);  
}  
  
var emptyObject = {};  
  
// Create a new function that uses the 12 and "a" parameters  
// as the first and second parameters.  
var displayArgs2 = displayArgs.bind(emptyObject, 12, "a");  
  
// Call the new function. The "b" and "c" parameters are used  
// as the third and fourth parameters.  
displayArgs2("b", "c");  
// Output: 12 a b c   
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Function – objekt](../../javascript/reference/function-object-javascript.md)   
 [Filter – metoda (pole)](../../javascript/reference/filter-method-array-javascript.md)   
 [Používání metody bind](../../javascript/advanced/using-the-bind-method-javascript.md)   
 [Hilo JavaScript ukázkovou aplikaci (pro Windows Store)](http://hilojs.codeplex.com/SourceControl/latest)