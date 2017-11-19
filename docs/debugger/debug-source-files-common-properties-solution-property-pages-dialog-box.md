---
title: "Ladění zdrojové soubory, běžné vlastnosti řešení stránky dialogové okno vlastností | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.options.FindSource
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
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 96ca9ef63a3823b942a6d7a160c31473f5db8962
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="debug-source-files-common-properties-solution-property-pages-dialog-box"></a>Ladění zdrojových souborů, společná nastavení, dialogové okno stránek vlastností řešení
Tato stránka vlastností určuje, kde ladicí program bude hledat zdrojových souborů při ladění řešení.  
  
 Pro přístup k **zdrojové soubory ladění** stránka vlastností, klikněte pravým tlačítkem na řešení v **Průzkumníku řešení** a vyberte **vlastnosti** z místní nabídky. Rozbalte **společných vlastností** složky a klikněte na **zdrojové soubory ladění** stránky.  
  
 **Adresáře, který obsahuje zdrojový kód**  
 Obsahuje seznam adresáře, ve kterých ladicí program vyhledává zdrojových souborů při ladění řešení. Prohledají se také podadresáře zadaných adresářích.  
  
 **Nebude provedeno hledání tyto zdrojové soubory**  
 Zadejte názvy všechny soubory, které nechcete, aby ladicí program ke čtení. Ladicí program vyhledá jeden z těchto souborů v jednom adresáři uvedeným výše, se budou ignorovat. Pokud **najít zdroj** dialogové okno se zobrazí při ladění a, kliknutí na tlačítko **zrušit**, soubor, který jste hledali získá přidané do tohoto seznamu tak, aby ladicí program nebude pokračovat ve vyhledávání pro tento soubor.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Nastavení ladicího programu a příprava](../debugger/debugger-settings-and-preparation.md)