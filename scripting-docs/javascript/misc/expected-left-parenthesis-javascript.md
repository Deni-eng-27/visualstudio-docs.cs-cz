---
title: Byl očekáván '(' (JavaScript) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT1005
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 712315e1-4c68-4f66-84c2-41b83c42d85a
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: baadfed3003f3b54d9d9cd4068b15a818b3858ce
ms.sourcegitcommit: f6dd17b0864419083d0a1bf54910023045526437
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/27/2018
ms.locfileid: "53804705"
---
# <a name="expected--javascript"></a>Byl očekáván znak '(' (JavaScript)
Došlo k pokusu o uzavření výrazu v rámci závorka, ale neobsahuje levou závorku. Některé výrazy musí být uzavřena v rámci otevírací a zavírací závorky. Všimněte si, že použití závorek v následujícím příkladu.  
  
```JavaScript  
for (initialize; test; increment) {  
statement;  
}  
```  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Přidáte levá závorka vyhodnocení výrazu.