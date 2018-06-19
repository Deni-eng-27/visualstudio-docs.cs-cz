---
title: Number.isfinite – funkce (Number) (JavaScript) | Microsoft Docs
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
ms.assetid: 41a91408-09d1-49f2-b7a0-6da105e2ed8e
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c23ff1e80ad71fd9d848f7a0e33628131f5d8014
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790950"
---
# <a name="numberisfinite-function-number-javascript"></a>Number.isFinite – funkce (Number) (JavaScript)
Vrátí logickou hodnotu, která určuje, zda je hodnota konečné číslo.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Number.isFinite(numValue)   
```  
  
## <a name="return-value"></a>Návratová hodnota  
 `false`Pokud je hodnota `NaN`, `+∞`, nebo `-∞`jinak `true`.  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="example"></a>Příklad  
  
```JavaScript  
// Returns true  
Number.isFinite(100)  
Number.isFinite(-100)  
Number.isFinite(100 / 3)  
  
// Returns false  
Number.isFinite(Number.NaN)  
Number.isFinite(Infinity)  
Number.isFinite("100")  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
 **Platí pro**: [číslo objektu](../../javascript/reference/number-object-javascript.md)