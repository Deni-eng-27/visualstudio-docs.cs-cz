---
title: Fill – metoda (pole) (JavaScript) | Microsoft Docs
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
ms.assetid: 11526627-c0bb-4157-a8c4-0a039079b4a1
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4546bafb3fa3a8c242b8b7ef4ef2863ea86bf179
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790449"
---
# <a name="fill-method-array-javascript"></a>fill – metoda (Pole) (JavaScript)
Naplní pole se zadanou hodnotou.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
arrayObj.fill(value [ , start [ , end ] ]);  
```  
  
#### <a name="parameters"></a>Parametry  
 `arrayObj`  
 Požadováno. Objekt array.  
  
 `value`  
 Požadováno. Hodnota určená k vyplnění pole.  
  
 `start`  
 Volitelné. Počáteční index, naplní hodnoty pole. Výchozí hodnota je 0.  
  
 `end`  
 Volitelné. Koncová index, naplní hodnoty pole. Výchozí hodnota je vlastnost délka `this` objektu.  
  
## <a name="remarks"></a>Poznámky  
 Pokud `start` záporné, `start` je považován za `length` + `start`, kde `length` je délka pole. Pokud `end` záporné, `end` je považován za `length` + `end`.  
  
## <a name="example"></a>Příklad  
 Následující příklady kódu naplnit pole s hodnotami.  
  
```JavaScript  
[0, 0, 0].fill(7, 1);  
// Array contains [0,7,7]  
  
[0, 0, 0].fill(7);  
// Array contains [7,7,7]  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]