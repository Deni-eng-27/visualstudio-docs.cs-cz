---
title: getMinutes – metoda (Date) (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- getMinutes
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- GetMinutes method
- minutes method
ms.assetid: d4139b5d-04e1-474c-9a83-e9d40597243a
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ff08fd84345c9ceb816444a1b44643a8353b60b1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790539"
---
# <a name="getminutes-method-date-javascript"></a>getMinutes – metoda (Date) (JavaScript)
Získá dobu, po které `Date` objektu pomocí místního času.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.getMinutes()   
```  
  
#### <a name="parameters"></a>Parametry  
 Požadované `dateObj` je odkaz `Date` objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí celé číslo mezi 0 a 59. Čas je méně než minutu po hodině, bude vrácena nula. Pokud `Date` objekt byl vytvořen bez zadání čas, ve výchozím nastavení minut hodnota je 0.  
  
## <a name="remarks"></a>Poznámky  
 Hodnota minuty pomocí světového koordinovaného času (UTC), použijte `getUTCMinutes` metoda.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje postup `getMinutes` metoda.  
  
```JavaScript  
var date = new Date("1/1/2001");  
document.write(date.getMinutes());  
document.write("<br/>");  
  
date.setMinutes(5);  
document.write(date.getMinutes());  
  
// Output:  
// 0  
// 5  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getUTCMinutes – metoda (Date)](../../javascript/reference/getutcminutes-method-date-javascript.md)   
 [setMinutes – metoda (Date)](../../javascript/reference/setminutes-method-date-javascript.md)   
 [setUTCMinutes – metoda (Date)](../../javascript/reference/setutcminutes-method-date-javascript.md)