---
title: Cyklický odkaz v argumentu hodnoty není podporován | Dokumentace Microsoftu
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5034
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 5d06f0fa-86f5-49d1-8d50-af1759990f43
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a31b56b4b2d568b3bc3fd59f876f5052b9f6faff
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60063995"
---
# <a name="circular-reference-in-value-argument-not-supported"></a>Cyklický odkaz v argumentu hodnoty není podporován
Byl proveden pokus o vyvolání `JSON.stringify` s hodnotou, která není platná. `value` Argument, pole nebo objekt, obsahuje cyklický odkaz.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
- Odeberte cyklický odkaz v argumentu.  
  
## <a name="example"></a>Příklad  
 Kód v tomto příkladu způsobí chybu modulu runtime, protože `john` obsahuje odkaz na `mary` a `mary` obsahuje odkaz na `john`. odebrat cyklický odkaz, buď odeberte nebo nenastavené vlastnosti `brother` z `mary` objektu nebo `sister` vlastnost z `john` objektu.  
  
```JavaScript  
var john = new Object();  
var mary = new Object();  
john.sister = mary;  
mary.brother = john;  
  
// This line causes a runtime error.  
var error = JSON.stringify(john);  
```  
  
## <a name="see-also"></a>Viz také  
 [JSON – objekt](../../javascript/reference/json-object-javascript.md)   
 [JSON.parse – funkce](../../javascript/reference/json-parse-function-javascript.md)   
 [JavaScript – chyby za běhu](../../javascript/reference/javascript-run-time-errors.md)