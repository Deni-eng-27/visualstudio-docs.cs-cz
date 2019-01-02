---
title: 'Postupy: Hledání knihovny DLL které Program selhal v | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.dll
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, DLL crashes
- Module List dialog box
- errors [debugger], DLL crashes
- Modules window
- debugging [Visual Studio], DLL crashes
- DLLs, load order of
ms.assetid: ecf62568-8b65-4a41-b8a4-e962ff2dfb71
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7726c7fff2f747fcde3fe62bcdcc0866b375728d
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53879118"
---
# <a name="how-to-find-which-dll-your-program-crashed-in-c-c-visual-basic-f"></a>Postupy: Hledání knihovny DLL které Program selhal v (C#, C++, Visual Basic, F#)
  
 Pokud vaše aplikace dojde k chybě během volání systémové knihovny DLL nebo kód někoho jiného, budete muset najít který byl aktivní knihovny DLL, kdy došlo k selhání. Pokud dojde k chybovému ukončení v knihovně DLL mimo svůj program, můžete určit pomocí umístění **moduly** okna.  
  
### <a name="to-find-where-a-crash-occurred-using-the-modules-window"></a>Najde, pro které selhání došlo k použití okna moduly  
  
1.  Poznamenejte si adresu, kde došlo k selhání.

    Pokud adresa není zobrazený v chybové zprávě, budete muset použít alternativní metody k identifikaci knihovny DLL. Pokud máte podezření na systémové knihovny DLL, můžete si [načíst symboly](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md) ze serverů Microsoft Symbol, při ladění. V opačném případě budete muset [vytvořit soubor s výpisem paměti](../debugger/using-dump-files.md) pomocí haldy informace místo. Různé [nástroje](https://blogs.msdn.microsoft.com/andrehal/2009/12/31/what-is-a-dump-and-how-do-i-create-one/) je možné vytvořit soubory s výpisem paměti.
  
2.  Na **ladění** nabídce zvolte **Windows**a klikněte na tlačítko **moduly**.  
  
3.  V **moduly** okně Najít **adresu** sloupce. Budete muset použít posuvník a prohlédněte si ho.  
  
4.  Klikněte na tlačítko **adresu** tlačítko v horní části Tento sloupec seřadit podle adresy knihovny DLL.  
  
5.  Kontrola seřazeného seznamu k nalezení knihovny DLL, jejichž rozsah adres obsahuje umístění při selhání.  
  
6.  Podívejte se na **název** a **cesta** sloupce, které chcete zobrazit název knihovny DLL a cestu.  
  
## <a name="see-also"></a>Viz také  
 [Ladění projektů knihovny DLL](../debugger/debugging-dll-projects.md)   
 [Postupy: Použití okna moduly](../debugger/how-to-use-the-modules-window.md)