---
title: Zjistit, jestli Moje ukazatele poškozená adresa paměti | Dokumentace Microsoftu
ms.custom: seodec18
ms.date: 11/04/2016
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ebe87ef6c391f0beae7183c7baa396f5bd95cf02
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2019
ms.locfileid: "59366008"
---
# <a name="how-can-i-find-out-if-my-pointers-corrupt-a-memory-address"></a>Jak zjistím, že moje ukazatele poškodily adresu paměti?
## <a name="problem-description"></a>Popis problému
 Myslím, že jeden z mých ukazatelů může způsobovat poškození paměti na adrese 0x00408000. Jak zjistím, co se děje?

## <a name="solution"></a>Řešení

#### <a name="check-for-heap-corruption"></a>Vyhledejte poškození haldy

-   Většina poškození paměti je vlastně způsobena poškozením haldy. Zkuste použít Global Flags Utility, (gflags.exe) nebo pageheap.exe. Zobrazit [ http://support.microsoft.com/default.aspx?scid=kb; en-us; 286470](http://support.microsoft.com/default.aspx?scid=kb;en-us;286470).

#### <a name="to-find-where-the-memory-address-is-modified"></a>Chcete-li najít, kde byla změněna adresa paměti

1.  Nastavte zarážku data na 0x00408000. Zobrazit [nastavit zarážku změny dat (pouze nativní C++)](../debugger/using-breakpoints.md#BKMK_set_a_data_breakpoint_native_cplusplus).

2.  Až se dostanete k zarážce, použijte **paměti** obsah okna paměti začínající na 0x00408000. Další informace najdete v tématu [paměti Windows](../debugger/memory-windows.md).

## <a name="see-also"></a>Viz také
- [Nejčastější dotazy k ladění nativního kódu](../debugger/debugging-native-code-faqs.md)
- [Ladění nativního kódu](../debugger/debugging-native-code.md)