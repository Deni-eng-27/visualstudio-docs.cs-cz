---
title: Očekává se VBArray | Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: error-reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5013
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: f2998d7d-13a4-4bbe-b872-3ff3316551e4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4b4e6521e5d363c21311b19e2ecc1679981acac3
ms.sourcegitcommit: e38419bb842d587fd9e37c24b6cf3fc5c2e74817
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/09/2020
ms.locfileid: "91862699"
---
# <a name="vbarray-expected"></a>Byl očekáván objekt VBArray
Zadali jste objekt, který nebyl Visual Basic safeArray, pokud byla očekávána jedna.  
  
```js
new VBArray(safeArray);  
```  
  
 VBArrays jsou jen pro čtení a nelze je vytvořit přímo. Argument safeArray je hodnota VBArray a před předáním konstruktoru musí být získána hodnota VBArray `VBArray` . To lze provést pouze načtením hodnoty z existujícího prvku ActiveX nebo jiného objektu.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
- Ujistěte se, že předáte pouze objekty **VBArray** do konstruktoru **VBArray** .  
  
## <a name="see-also"></a>Viz také  
 [Objekt VBArray](https://developer.mozilla.org/docs/Archive/Web/JavaScript/Microsoft_Extensions/VBArray)   
 [Používání polí](https://developer.mozilla.org/docs/Learn/JavaScript/First_steps/Arrays)