---
title: delete – metoda (Set) (JavaScript) | Microsoft Docs
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
ms.assetid: 052c409e-10c9-49f2-955d-5ad7e31c14f3
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 72762b93c6996fd72bd035c5d653f0e85f4ffd33
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790335"
---
# <a name="delete-method-set-javascript"></a>delete – metoda (Set) (JavaScript)
Odebere zadaný element ze sady.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
setObj.delete(value)  
```  
  
#### <a name="parameters"></a>Parametry  
 `setObj`  
 Požadováno. A `Set` objektu.  
  
 `value`  
 Požadováno. Elementu, který chcete odebrat.  
  
## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota  
 `true`Pokud element byla odebrána.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak přidávat členy do `Set` a pak odstraňte jednu z nich.  
  
```JavaScript  
var s = new Set();  
s.add("Thomas Jefferson");  
s.add(1776);  
s.add("founding father");  
s.delete("founding father");  
  
s.forEach(function (item) {  
    document.write(item.toString() + ", ");  
});  
  
// Output:  
// Thomas Jefferson, 1776,  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]