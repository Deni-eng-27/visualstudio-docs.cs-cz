---
title: Délka pole musí být konečné kladné celé číslo | Dokumentace společnosti Microsoft
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5029
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 1a467040-4702-4178-848f-418a5974e907
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 691f7aff61a8a2bfae6444540afe9a28a200278d
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/26/2019
ms.locfileid: "56840429"
---
# <a name="array-length-must-be-a-finite-positive-integer"></a>Délka pole musí být konečné kladné celé číslo
Při volání **pole** konstruktor s argumentem, který není celé číslo (celá čísla skládá z nula a sadu kladná celá čísla).  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Kladná celá čísla použít jenom při vytváření nového `Array` objektu. Pokud chcete vytvořit pole s jediným elementem, který není celé číslo, postup ve dvou krocích. Nejprve vytvoříte pole s jedním prvkem, pak umístit hodnotu elementu první (array[0]). Následuje příklad, který generuje tuto chybu.  
  
    ```JavaScript  
    var piArray = new Array(3.14159);  
    ```  
  
     Následující příklad ukazuje správný způsob, jak určit pole s jediným elementem číselná.  
  
    ```JavaScript  
    var piArray = new Array(1);  
    piArray [0] = 3.14159;  
    ```  
  
     Neexistuje žádná horní mez pro velikost pole, než je maximální celočíselnou hodnotu (přibližně 4 miliardy).  
  
## <a name="see-also"></a>Viz také  
 [Používání polí](../../javascript/advanced/using-arrays-javascript.md)