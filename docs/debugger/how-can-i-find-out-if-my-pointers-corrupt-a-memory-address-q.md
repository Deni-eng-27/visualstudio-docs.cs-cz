---
title: Jak zjistím, že moje ukazatele poškodily adresu paměti? | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- addresses, pointers corrupting memory address
- memory, corruption
- pointers, corrupting memory addresses
- memory address corruption by pointers
- debugging [C++], memory corruption
- corrupted memory address
ms.assetid: a147c939-4fb1-415c-8410-cf303781e9e8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8965ec268e5d236b9a33e5c3e8acfa35e51dcdb3
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31479309"
---
# <a name="how-can-i-find-out-if-my-pointers-corrupt-a-memory-address"></a>Jak zjistím, že moje ukazatele poškodily adresu paměti?
## <a name="problem-description"></a>Popis problému  
 Myslím, že jeden z mých ukazatelů může být poškozování paměti na adrese 0x00408000. Jak můžete najít na co se děje existuje?  
  
## <a name="solution"></a>Řešení  
  
#### <a name="check-for-heap-corruption"></a>Zkontrolujte poškození haldy  
  
-   Většina poškození paměti je ve skutečnosti kvůli poškození haldy. Zkuste použít globální příznaky nástroj, (gflags.exe) nebo pageheap.exe. V tématu [ http://support.microsoft.com/default.aspx?scid=kb; en-us; 286470](http://support.microsoft.com/default.aspx?scid=kb;en-us;286470).  
  
#### <a name="to-find-where-the-memory-address-is-modified"></a>Pokud chcete najít, kde je adresa paměti změnit  
  
1.  Nastavte zarážky data na 0x00408000. V tématu [zarážku změn dat (pouze nativní C++)](../debugger/using-breakpoints.md#BKMK_set_a_data_breakpoint_native_cplusplus_only).  
  
2.  Při kliknutí na zarážce, použijte **paměti** okno zobrazení paměti obsah počínaje 0x00408000. Další informace najdete v tématu [paměti Windows](../debugger/memory-windows.md).  
  
## <a name="see-also"></a>Viz také  
 [Nativní kód nejčastější dotazy k ladění](../debugger/debugging-native-code-faqs.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)