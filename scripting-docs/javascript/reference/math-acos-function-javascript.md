---
title: "Math.ACOS – funkce (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- acos
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- acos method
- arcosine method
ms.assetid: 828cb3c3-bdf7-4bb7-97ae-3617ce4b2d62
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 773499287e215fbc161f289954811d3ef62bcba6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="mathacos-function-javascript"></a>Math.acos – funkce (JavaScript)
Vrátí kosinus oblouk (nebo inverzní kosinus) čísla.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Math.acos(number)  
```  
  
#### <a name="parameters"></a>Parametry  
 Požadované `number` argument je číselný výraz.  
  
## <a name="return-value"></a>Návratová hodnota  
 Kosinus oblouk `number` argument, v radiánech.  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje způsob použití `acos` funkce.  
  
```JavaScript  
var v1 = Math.acos(-1.0);  
var v2 = Math.cos(-1.0);  
  
document.write(v1);  
document.write("<br/>");  
document.write(v2);  
  
// Output:  
// 3.141592653589793  
// 0.5403023058681398  
  
```  
  
## <a name="remarks"></a>Poznámky  
 **Platí pro**: [Math – objekt](../../javascript/reference/math-object-javascript.md)  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Math.ASIN – funkce](../../javascript/reference/math-asin-function-javascript.md)   
 [Math.Atan – funkce](../../javascript/reference/math-atan-function-javascript.md)   
 [Math.cos – funkce](../../javascript/reference/math-cos-function-javascript.md)   
 [Math.sin – funkce](../../javascript/reference/math-sin-function-javascript.md)   
 [Math.tan – funkce](../../javascript/reference/math-tan-function-javascript.md)   
 [Math – objekt](../../javascript/reference/math-object-javascript.md)