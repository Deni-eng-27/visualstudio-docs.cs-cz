---
title: Zjistit, jestli moje ukazatele poškodily adresu paměti | Microsoft Docs
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
ms.openlocfilehash: 516b04bb625ad2546c4c8f3d3e7d7d4ba9419094
ms.sourcegitcommit: 49ebf69986713e440fd138fb949f1c0f47223f23
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/03/2019
ms.locfileid: "74705841"
---
# <a name="how-can-i-find-out-if-my-pointers-corrupt-a-memory-address"></a>Jak zjistím, že moje ukazatele poškodily adresu paměti?
## <a name="problem-description"></a>Popis problému
 Myslím, že jeden z mých ukazatelů může poškodit paměť na adrese 0x00408000. Jak můžu zjistit, co se děje?

## <a name="solution"></a>Řešení

#### <a name="check-for-heap-corruption"></a>Kontrolovat poškození haldy

- Většina poškození paměti je způsobená poškozením haldy. Zkuste použít nástroj Global Flags Utility (Gflags. exe) nebo Pageheap. exe. Viz [https://docs.microsoft.com/windows-hardware/drivers/debugger/gflags-and-pageheap](/windows-hardware/drivers/debugger/gflags-and-pageheap).

#### <a name="to-find-where-the-memory-address-is-modified"></a>Zjištění, kde je adresa paměti upravena

1. Nastavte zarážku dat na 0x00408000. Viz [Nastavení zarážky změny dat (pouze C++ nativní)](../debugger/using-breakpoints.md#BKMK_set_a_data_breakpoint_native_cplusplus).

2. Při dosažení zarážky použijte okno **paměť** k zobrazení obsahu paměti od 0x00408000. Další informace najdete v tématu [paměťová okna](../debugger/memory-windows.md).

## <a name="see-also"></a>Viz také:
- [Nejčastější dotazy k ladění nativního kódu](../debugger/debugging-native-code-faqs.md)
- [Ladění nativního kódu](../debugger/debugging-native-code.md)
