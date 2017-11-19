---
title: "getUTCHours – metoda (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: getUTCHours
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- hours
- UTC times, returning
- getUTCHours method
ms.assetid: 7c9825dd-4b3a-4614-8e09-f40df123b630
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 34a07f9f63fe22d3101cc748e9dde978385a71ab
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="getutchours-method-date-javascript"></a>getUTCHours – metoda (Date) (JavaScript)
Získá hodnotu hodiny v `Date` pomocí světového koordinovaného času (UTC).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.getUTCHours()   
```  
  
#### <a name="parameters"></a>Parametry  
 Požadované `dateObj` je odkaz `Date` objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí celé číslo mezi 0 a 23 určující počet hodin od půlnoci. Pokud je doba před 1:00:00 am, bude vrácena nula. Pokud `Date` objekt byl vytvořen bez zadání čas, hodiny ve výchozím nastavení je 0 v čase UTC. Tento čas může být nula v jiných časových pásmech.  
  
## <a name="remarks"></a>Poznámky  
 Chcete-li získat počet hodin uběhlých od půlnoci pomocí místního času, použijte `getHours` metoda.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `getUTCHours` metoda.  
  
```JavaScript  
var date = new Date("1/1/2001");  
document.write(date.getUTCHours());  
document.write("<br/>");  
  
var date2 = new Date("1/1/2001 11:22:33");  
document.write(datee.getUTCHours());  
  
// Output (in the PST time zone):  
// 8  
// 19  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getHours – metoda (Date)](../../javascript/reference/gethours-method-date-javascript.md)   
 [setHours – metoda (Date)](../../javascript/reference/sethours-method-date-javascript.md)   
 [setUTCHours – metoda (Date)](../../javascript/reference/setutchours-method-date-javascript.md)