---
title: "Zápis funkce háku ladění | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.hooks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], CRT debug support
- debug hook functions
- hooks, debug
- hooks
- debugging [CRT], debug hook functions
ms.assetid: 5510635f-cf69-4907-b72d-ae27af1f19af
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 30d645042908a7ff307017d090c2789b9d40b99a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="debug-hook-function-writing"></a>Zápis funkce háku ladění
Tato část popisuje několik funkce háku vlastní ladění, můžete napsat a které vám umožní vložení kódu do některé předdefinované body v normálním zpracování ladicího programu.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Funkce háku bloku klienta](../debugger/client-block-hook-functions.md)  
 Poskytuje pokyny a prototypu pro zápis funkce, které sestavy obsah data uložená v blocích _client_block – nebo ověření.  
  
 [Funkce háku přidělení](../debugger/allocation-hook-functions.md)  
 Definuje funkce háku přidělení, jsou zde popsány různé používá, body se omezení a poskytuje prototypu.  
  
 [Háky přidělení a přidělení paměti CRT](../debugger/allocation-hooks-and-c-run-time-memory-allocations.md)  
 Popisuje omezení na funkce háku přidělení explicitně ignorování `_CRT_BLOCK` blokuje Pokud udělají jakékoli volání funkce běhové knihovny jazyka C, které přidělují interní paměť. Toto téma rovněž uvádí možné důsledky, pokud vaše háku přidělení neignoruje `_CRT_BLOCK` bloky (s příklady) a jak změnit výchozí přidělení napojit funkce, **CrtDefaultAllocHook**.  
  
 [Funkce háku sestavy](../debugger/report-hook-functions.md)  
 Popisuje `_CrtSetReportHook`, který můžete použít k filtrování sestavy a zaměřit se na konkrétní typy přidělení. Toto téma obsahuje také prototypu.  
  
## <a name="related-sections"></a>Související oddíly  
 [Techniky ladění CRT](../debugger/crt-debugging-techniques.md)  
 Odkazy na ladění techniky pro běhové knihovny jazyka C pomocí ladění knihovny CRT, makra pro vytváření sestav, včetně rozdíly mezi `malloc` a `_malloc_dbg`, zápis funkce háku ladění a haldy ladění CRT.