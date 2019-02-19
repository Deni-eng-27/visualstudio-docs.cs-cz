---
title: Řešení potíží s fragmenty kódu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: troubleshooting
helpviewer_keywords:
- IntelliSense Code Snippets, troubleshooting
- troubleshooting IntelliSense Code Snippets
- troubleshooting Visual Basic, IntelliSense Code Snippets
ms.assetid: 7b6dd40e-2f78-4b50-8e68-41fac1bcb81e
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7fe80ad6c3983b35f97071093428bf7f356292b0
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2019
ms.locfileid: "54803759"
---
# <a name="troubleshooting-snippets"></a>Řešení potíží s fragmenty kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Problémy s fragmenty kódu technologie IntelliSense jsou obvykle způsobené dva problémy: soubor výstřižku poškozený nebo chybný obsah v souboru fragmentu kódu.  
  
## <a name="common-problems"></a>Běžné problémy  
  
### <a name="the-snippet-cannot-be-dragged-from-file-explorer-to-a-visual-studio-source-file"></a>Fragment kódu je nelze přetáhnout z Průzkumníka souborů na zdrojový soubor Visual Studio  
  
-   Kód XML v souboru fragmentu kódu může být poškozený. **Editoru XML** v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] problémy můžete najít ve struktuře XML.  
  
-   Soubor výstřižku nemusí odpovídat schématu fragmentu kódu. **Editoru XML** v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] problémy můžete najít ve struktuře XML.  
  
### <a name="the-code-has-compiler-errors-that-are-not-highlighted"></a>Kód obsahuje chyby kompilátoru, ne zvýrazněné  
  
-   Pravděpodobně chybí odkaz na projekt. Prozkoumejte dokumentaci o fragmentu kódu. Pokud odkaz nebyl nalezen v počítači, musíte ji nainstalovat. Fragment kódu pro vložení přidejte do projektu všechny odkazy potřebné. Pokud fragmentu kódu chybí odkaz na informace, které jsou hlášeny autora fragmentu kódu za chybu.  
  
-   Proměnná může nedefinovaný. By měl být zvýrazněn nedefinované proměnné v fragment kódu. Pokud ne, který můžete nahlásit tvůrci fragment kódu za chybu.  
  
## <a name="see-also"></a>Viz také  
 [Fragmenty kódu](../ide/code-snippets.md)
