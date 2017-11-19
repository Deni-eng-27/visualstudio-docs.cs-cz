---
title: "Vyřešit nejednoznačnosti – dialogové okno | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.Disambig
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Resolve Ambiguity dialog box
- debugger, Resolve Ambiguity dialog box
- debugging [C++], resolving ambiguity
ms.assetid: d9f47455-a116-4c84-8bad-2dfbf4d77f74
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b0050ccdb3a4ccbd2d1d116239ad6fd6aba2032e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="resolve-ambiguity-dialog-box"></a>Dialogové okno Vyřešit nejednoznačnosti
`Resolve Ambiguity` Dialogové okno se zobrazí, když ladicí program nemůže vyberte umístění, k zobrazení. Například pokud používáte šablonami C++, můžete vytvořit víc funkcí z jedné funkce šablony. Pokud ladicí program zastaví v umístění zdroje v šabloně, a vy zvolíte `Go To Disassembly`, má více možností ladicího programu. Jednotlivé funkce z šablony má svou vlastní zpětný překlad kódu a ladicí program nebude vědět, který kód, který chcete zobrazit. `Resolve Ambiguity` Dialogové okno umožňuje vybrat umístění, bude ze seznamu všech odpovídajících umístění.  
  
 `Choose the specific location`  
 Zobrazuje seznam všech umístění odpovídající do příkazu.  
  
 `Address`  
 Zobrazuje adresy paměti pro každou funkci.  
  
 `Function`  
 Zobrazuje název jednotlivé funkce.  
  
 `Module`  
 Zobrazí modul, (EXE nebo DLL) obsahující kód objektu pro tuto funkci.  
  
## <a name="see-also"></a>Viz také  
 [Výrazy v ladicím programu](../debugger/expressions-in-the-debugger.md)