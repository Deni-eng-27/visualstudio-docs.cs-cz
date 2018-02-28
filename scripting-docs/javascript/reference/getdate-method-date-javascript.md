---
title: "getDate – metoda (Date) (JavaScript) | Microsoft Docs"
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
- getDate
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Date object
- dates, returning day of the month
- getDate method
ms.assetid: 67e7f07c-dd46-4b42-82d6-e53e4bd33703
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bfb3a8ad3ba433dc776f0831d1eac4787b8aea90
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="getdate-method-date-javascript"></a>getDate – metoda (Date) (JavaScript)
Získá den z měsíce, pomocí místního času.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.getDate()   
```  
  
#### <a name="parameters"></a>Parametry  
 Požadované `dateObj` je odkaz `Date` objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Celé číslo od 1 do 31 představující den z měsíce.  
  
## <a name="remarks"></a>Poznámky  
 Den z měsíce pomocí Universal Coordinated Time (UTC), použijte `getUTCDate` metoda.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `getDate` metoda.  
  
```JavaScript  
var date = new Date("Jan 01, 2001");  
var str = "Today's date is: ";  
   str += (date.getMonth() + 1) + "/";  
   str += date.getDate() + "/";  
   str += date.getFullYear();  
document.write(str);  
  
// Output: Today's date is: 1/1/2001  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getUTCDate – metoda (Date)](../../javascript/reference/getutcdate-method-date-javascript.md)   
 [setDate – metoda (Date)](../../javascript/reference/setdate-method-date-javascript.md)   
 [setUTCDate – metoda (Date)](../../javascript/reference/setutcdate-method-date-javascript.md)