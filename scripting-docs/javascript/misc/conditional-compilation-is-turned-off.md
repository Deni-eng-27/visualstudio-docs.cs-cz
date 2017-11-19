---
title: "Podmíněná kompilace je vypnutá. | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.WebClient.Help.SCRIPT1030
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 59a030b0-a6c6-47f2-b90e-c0ed204d5116
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8f2eabb900e24072c8f390061b5d6081de9bc889
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="conditional-compilation-is-turned-off"></a>Podmíněná kompilace je vypnutá
Jste se pokusili použít proměnné podmíněné kompilace bez první měnící Podmíněná kompilace v. Zapnutí Podmíněná kompilace informuje [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] kompilátoru interpretovat identifikátory počínaje jako proměnné podmíněné kompilace. To provedete od podmíněného kódu s příkazem:  
  
```  
/*@cc_on @*/  
```  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Přidejte následující příkaz na začátek podmíněného kódu:  
  
    ```JavaScript  
    /*@cc_on @*/  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Podmíněná kompilace](../../javascript/advanced/conditional-compilation-javascript.md)   
 [Proměnné podmíněné kompilace](../../javascript/advanced/conditional-compilation-variables-javascript.md)   
 [@cc_onPříkaz](../../javascript/reference/at-cc-on-statement-javascript.md)   
 [@ifPříkaz](../../javascript/reference/at-if-statement-javascript.md)   
 [@setPříkaz](../../javascript/reference/at-set-statement-javascript.md)