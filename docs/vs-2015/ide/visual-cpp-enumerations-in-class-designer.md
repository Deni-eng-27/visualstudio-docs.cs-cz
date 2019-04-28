---
title: Výčty jazyka Visual C++ v Návrháři tříd | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Class Designer [Visual Studio], enumerations
ms.assetid: 11e90ba1-18cd-44f8-9e26-e3746a7a19d1
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 209f56d8222d4cc446d15f8eedd4d89b08993c5a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62548580"
---
# <a name="visual-c-enumerations-in-class-designer"></a>Výčty jazyka Visual C++ v návrháři tříd
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Návrhář tříd podporuje C++ `enum` a s vymezeným oborem `enum class` typy. Tady je příklad:  
  
```  
enum CardSuit {  
   Diamonds = 1,  
   Hearts = 2,  
   Clubs = 3,  
   Spades = 4  
};  
  
// or...  
enum class CardSuit {  
   Diamonds = 1,  
   Hearts = 2,  
   Clubs = 3,  
   Spades = 4  
};  
  
```  
  
 Tvar výčtu C++ v diagramu třídy vypadá a funguje jako tvar struktury, s tím rozdílem, že načte popisek **výčtu** nebo **Enum class**, je růžový místo modrý a má barevné ohraničení na levém a horním okraje. Obrazce výčtu i obrazce struktury mají hranaté rohy.  
  
 Další informace o používání `enum` zadejte naleznete v tématu [výčty](http://msdn.microsoft.com/library/081829db-5dca-411e-a53c-bffef315bcb3).  
  
## <a name="see-also"></a>Viz také  
 [Práce s kódem jazyka Visual C++ (návrhář tříd)](../ide/working-with-visual-cpp-code-class-designer.md)   
 [Výčty](http://msdn.microsoft.com/library/081829db-5dca-411e-a53c-bffef315bcb3)
