---
title: Rámců zásobníku | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- stack frames, debugging
- debugging [Debugging SDK], stack frames
- stack frames
ms.assetid: b5e439d4-1e9d-4e13-9cad-bb8b136d4ca8
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: de3a0267d366f926fa5705c7455b237cafe4820a
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66348499"
---
# <a name="stack-frames"></a>Rámce zásobníku
V architektuře ladicího programu *rámec zásobníku*:

- Je abstrakcí zásobníku, která poskytuje kontext spuštění vlákna. Vlákno vždy provede v rámci funkce. Rámec zásobníku obsahuje místní proměnné, funkce a argumenty do něj. Pokud chcete ladit pomocí sady Visual Studio, musí podporovat rámce zásobníku jazyka nebo prostředí, které jsou právě laděny.

- Můžete identifikovat a popsat sám sebe i může vrátit přidružené vlákno. Rámec zásobníku může také vrátit kontext kódu, který představuje aktuální ukazatel příkazu a související dokumentaci a kontext vyhodnocení výrazu.

- Obsahuje vlastnosti, které popisují název, typ a hodnotu místní proměnné a argumenty a které jsou uvedeny v různých ladicích oknech integrovaného vývojového prostředí.

- Je reprezentován [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md) rozhraní, obvykle vytvoří pomocí ladicího stroje (DE) nebo virtuální počítač následkem podproces.

## <a name="see-also"></a>Viz také:
- [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md)
- [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)
- [Ladicí stroj](../../extensibility/debugger/debug-engine.md)
- [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md)