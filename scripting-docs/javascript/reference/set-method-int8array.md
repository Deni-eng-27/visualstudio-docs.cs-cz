---
title: set – metoda (Int8Array) | Microsoft Docs
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
ms.assetid: 4beae82e-8556-48aa-86c6-18c8859d913e
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bfa9c319caf448e20888aeefa2f29aaade9aa364
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791451"
---
# <a name="set-method-int8array"></a>set – metoda (Int8Array)
Nastaví hodnotu nebo pole hodnot.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
int8Array.set(index, value);  
int8Array.set(array, offset);  
  
```  
  
## <a name="parameters"></a>Parametry  
 `index`  
 Index umístění, které chcete nastavit.  
  
 `value`  
 Hodnota k nastavení.  
  
 `array`  
 Pole hodnot k nastavení s typem nebo bez typu.  
  
 `offset`  
 Index v aktuálním poli, do kterého se mají hodnoty zapsat.  
  
## <a name="remarks"></a>Poznámky  
 Pokud je vstupní pole TypedArray, dvě pole mohou používat stejný podkladový ArrayBuffer. V tomto případě k nastavení hodnot dochází stejně, jako by všechna data byla nejprve zkopírována do dočasné vyrovnávací paměti, která nepřekrývá žádné z polí, a poté zkopírována z dočasné vyrovnávací paměti do aktuálního pole.  
  
 Je-li součet posunu a délky mimo rozsah aktuálního pole TypedArray, je vyvolána výjimka.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak nastavit první prvek pole.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var intArr = new Int8Array(buffer.byteLength);  
            intArr.set(0, 9);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]