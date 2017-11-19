---
title: "getHours – metoda (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: getHours
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Date object
- GetHours method
- Hours method
ms.assetid: c3936496-a213-4d15-b308-d53926ed310c
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 87170f96ee6ae6b4a825436717a94749cc336ee0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="gethours-method-date-javascript"></a>getHours – metoda (Date) (JavaScript)
Získá čas, datum, pomocí místního času.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.getHours()   
```  
  
#### <a name="parameters"></a>Parametry  
 Požadované `dateObj` je odkaz `Date` objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Celé číslo mezi 0 a 23, která určuje počet hodin od půlnoci. Pokud je doba před 1:00:00 am, bude vrácena nula. Pokud `Date` objekt byl vytvořen bez zadání čas, ve výchozím nastavení hodinu je 0.  
  
## <a name="remarks"></a>Poznámky  
 Hodnota hodiny pomocí světového koordinovaného času (UTC), použijte `getUTCHours` metoda.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `getHours` metoda.  
  
```JavaScript  
var date = new Date("1/1/2001");  
document.write(date.getHours());  
document.write("<br/>");  
  
date.setTime(50000000);  
document.write(date.getHours());  
  
// Output:  
// 0   
// 5  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getUTCHours – metoda (Date)](../../javascript/reference/getutchours-method-date-javascript.md)   
 [setHours – metoda (Date)](../../javascript/reference/sethours-method-date-javascript.md)   
 [setUTCHours – metoda (Date)](../../javascript/reference/setutchours-method-date-javascript.md)