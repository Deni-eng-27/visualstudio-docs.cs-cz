---
title: prototype – vlastnost (Intl.Collator) | Microsoft Docs
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
ms.assetid: c1bbb523-fb55-4395-b357-34d91cf5bba0
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 696535afde8c497bc98fc2c81a03854d66add6f4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791244"
---
# <a name="prototype-property-intlcollator"></a>prototype – vlastnost (Intl.Collator)
Vrátí odkaz na prototypu pro kompletování.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
collator.prototype  
```  
  
## <a name="remarks"></a>Poznámky  
 `collator` Argument je název kompletování.  
  
 Použití `prototype` vlastnost poskytnout základní sadu funkcí, které třídu objektů. Nové instance objektu "Zdědit" chování prototypu přiřazen tento objekt.  
  
 Například přidejte metodu k `Intl.Collator` objektu, který vrátí hodnotu největší prvku sady, deklarovat funkci, přidejte ho do `Intl.Collator.prototype`a pak jeho pomocí.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]