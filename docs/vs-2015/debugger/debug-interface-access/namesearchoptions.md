---
title: Namesearchoptions – | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- NameSearchOptions enumeration
ms.assetid: 67dfbede-2678-47df-b664-5c49841d0b9b
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 64f74880fe27cc71634508cbb6b272aea16517d4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42671176"
---
# <a name="namesearchoptions"></a>NameSearchOptions
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [namesearchoptions –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/namesearchoptions).  
  
Určuje možnosti hledání symbolů a názvy souborů.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum NameSearchOptions {   
   nsNone,  
   nsfCaseSensitive     = 0x1,  
   nsfCaseInsensitive   = 0x2,  
   nsfFNameExt          = 0x4,  
   nsfRegularExpression = 0x8,  
   nsfUndecoratedName   = 0x10,  
  
// For backward compatibility:  
   nsCaseSensitive           = nsfCaseSensitive,  
   nsCaseInsensitive         = nsfCaseInsensitive,  
   nsFNameExt                = nsfCaseInsensitive | nsfFNameExt,  
   nsRegularExpression       = nsfRegularExpression | nsfCaseSensitive,  
   nsCaseInRegularExpression = nsfRegularExpression | nsfCaseInsensitive  
};  
```  
  
## <a name="elements"></a>Elementy  
 `nsNone`  
 Nejsou zadány žádné parametry.  
  
 `nsfCaseSensitive`  
 Platí shoda názvu malá a velká písmena.  
  
 `nsfCaseInsensitive`  
 Platí shoda nerozlišuje velikost písmen názvů.  
  
 `nsfFNameExt`  
 Názvy považuje za cesty a použije shodného názvu název_souboru.přípona.  
  
 `nsfRegularExpression`  
 Platí shoda názvu malá a velká písmena pomocí hvězdičky (*) a otazník (?) jako zástupné znaky.  
  
 `nsfUndecoratedName`  
 Platí jenom pro symboly, které mají nedekorovaných i dekorované názvy.  
  
## <a name="remarks"></a>Poznámky  
 Hodnoty z tento výčet se předají do následujících metod:  
  
-   [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)  
  
-   [IDiaSession::findFile](../../debugger/debug-interface-access/idiasession-findfile.md)  
  
-   [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: dia2.h  
  
## <a name="see-also"></a>Viz také  
 [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Idiasession::findchildren –](../../debugger/debug-interface-access/idiasession-findchildren.md)   
 [Idiasession::FindFile –](../../debugger/debug-interface-access/idiasession-findfile.md)   
 [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)



