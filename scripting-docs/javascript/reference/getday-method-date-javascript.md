---
title: "getDay – metoda (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: getDay
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- GetDay method
- Date object
- dates, returning day of the week
ms.assetid: 27be7168-3dce-41c9-ae69-6280b7984c2e
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1749eca5aceee76947a0162f22700f32525fdec0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="getday-method-date-javascript"></a>getDay – metoda (Date) (JavaScript)
Získá den v týdnu, pomocí místního času.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj. getDay()   
```  
  
#### <a name="parameters"></a>Parametry  
 Požadované `dateObj` je odkaz `Date` objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Celé číslo od 0 do 6 představující den v týdnu (neděle je 0, sobota je 6).  
  
## <a name="remarks"></a>Poznámky  
 Den pomocí světového koordinovaného času (UTC), použijte `getUTCDay` metoda.  
  
 Následující příklad ukazuje způsob použití `getDay` metoda.  
  
```JavaScript  
var date = new Date("Saturday, February 9, 2008");  
day = date.getDay();  
document.write(day);  
  
// Output: 6  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getUTCDay – metoda (Date)](../../javascript/reference/getutcday-method-date-javascript.md)