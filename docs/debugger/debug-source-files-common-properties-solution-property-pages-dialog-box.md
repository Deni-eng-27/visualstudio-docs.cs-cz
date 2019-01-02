---
title: Ladění zdroje souborů, společná nastavení řešení vlastnost dialogového okna stránky | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.debug.options.FindSource
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
helpviewer_keywords:
- Debug Source Files property page
- debugging [Visual Studio], specifying source and symbol files
- source files, specifying in debugger
- debugger, source files
ms.assetid: 0af11464-eeb1-4d0b-87a6-0cc96779afb1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a722422306a16ee7e2dc340448f0e082f8a1f014
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53931905"
---
# <a name="debug-source-files-common-properties-solution-property-pages-dialog-box"></a>Ladění zdrojových souborů, společná nastavení, dialogové okno stránek vlastností řešení
Tuto stránku vlastností určuje, kde ladicí program vyhledá zdrojové soubory při ladění řešení.  
  
 Pro přístup **zdrojové soubory ladění** stránky vlastností, klikněte pravým tlačítkem na řešení v **Průzkumníka řešení** a vyberte **vlastnosti** z místní nabídky. Rozbalte **společné vlastnosti** složky a klikněte na tlačítko **zdrojové soubory ladění** stránky.  
  
 **Adresáře obsahujícího zdrojový kód**  
 Obsahuje seznam adresářů, ve kterých ladicí program vyhledává zdrojové soubory při ladění řešení. Vyhledávají také podadresáře zadaných adresářích.  
  
 **Nelze najít tyto zdrojové soubory**  
 Zadejte názvy všech souborů, které nechcete, aby ladicí program ke čtení. Pokud ladicí program nalezne některý z těchto souborů v jednom z adresářů zadaných výše, se bude ignorovat. Pokud **najít zdroj** dialogové okno se zobrazí při ladění a kliknutí na **zrušit**, tak, aby ladicí program nebude pokračovat ve vyhledávání pro tento soubor získá do tohoto seznamu přidat soubor jste hledali.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Nastavení a příprava ladicího programu](../debugger/debugger-settings-and-preparation.md)