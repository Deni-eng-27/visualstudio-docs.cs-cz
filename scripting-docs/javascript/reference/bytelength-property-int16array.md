---
title: bytelength – vlastnost (Int16Array) | Microsoft Docs
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
ms.assetid: f6ccad69-b175-478a-b881-df63152a5361
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2c71d058cd08a6d7d6a61cc82a1ca9b71a9f6f71
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789057"
---
# <a name="bytelength-property-int16array"></a>byteLength – vlastnost (Int16Array)
Jen pro čtení. Délka tohoto pole od začátku jeho ArrayBuffer v bajtech, jak je stanoveno v době konstrukce.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
var arrayByteLength = int16Array.byteLength;  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak nastavit délku pole.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var intArr = new Int16Array(buffer.byteLength / 2);  
            alert(intArr.byteLength);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]