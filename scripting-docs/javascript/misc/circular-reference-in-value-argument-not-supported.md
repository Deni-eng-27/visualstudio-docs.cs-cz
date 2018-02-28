---
title: "Cyklický odkaz v argumentu hodnoty není podporován | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT5034
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 5d06f0fa-86f5-49d1-8d50-af1759990f43
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d25489065ceece41108a75c9d3763a95e4adb924
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="circular-reference-in-value-argument-not-supported"></a>Cyklický odkaz v argumentu hodnoty není podporován
Byl proveden pokus o vyvolání `JSON.stringify` s hodnotou, který není platný. `value` Argument, pole nebo objekt, obsahuje cyklický odkaz.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Odeberte cyklický odkaz v argumentu.  
  
## <a name="example"></a>Příklad  
 Kód v tomto příkladu způsobí chyba za běhu, protože `john` obsahuje odkaz na `mary` a `mary` obsahuje odkaz na `john`. Chcete-li odebrat cyklický odkaz, buď odeberte nebo nenastavené vlastnost `brother` z `mary` objekt nebo `sister` vlastnost z `john` objektu.  
  
```JavaScript  
var john = new Object();  
var mary = new Object();  
john.sister = mary;  
mary.brother = john;  
  
// This line causes a runtime error.  
var error = JSON.stringify(john);  
```  
  
## <a name="see-also"></a>Viz také  
 [Objekt JSON](../../javascript/reference/json-object-javascript.md)   
 [JSON.Parse – funkce](../../javascript/reference/json-parse-function-javascript.md)   
 [JavaScript – chyby za běhu](../../javascript/reference/javascript-run-time-errors.md)