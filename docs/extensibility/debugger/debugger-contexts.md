---
title: Kontexty ladicího programu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], contexts
ms.assetid: 79808036-b680-4e4c-9c61-4ed43aa11323
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3fc77e24a1a9ca72d6f689247f0de6a9e0bf26cc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62889984"
---
# <a name="debugger-contexts"></a>Kontexty ladicího programu
V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění, ladicí stroj (DE) pracuje současně v rámci několika různých kontextech, následujícím způsobem:

- Kontext kódu, která popisuje aktuální umístění v datovém proudu provádění programu.

- Dokumentace ke službě kontext nebo umístění, která popisuje aktuální pozici ve zdrojovém dokumentu.

- Kontext vyhodnocení výrazu, popisující kontext, ve výrazu, který bude vyhodnocení proběhnout.

## <a name="in-this-section"></a>V tomto oddílu
 [Kontext kódu](../../extensibility/debugger/code-context.md) popisuje kontext kódu jako adresa ve službě stream instrukce programu v dnešní za běhu architektury oproti netradičních jazyky, ve kterém kód nemusí reprezentovat pokyny, ale jiným způsobem.

 [Pozice dokumentu](../../extensibility/debugger/document-position.md) definuje pozice dokumentu v ladění sady Visual Studio prostřednictvím abstrakce pozice ve zdrojovém souboru, protože ví, rozhraní IDE.

 [Kontext dokumentu](../../extensibility/debugger/document-context.md) popisuje, jaké kontext dokumentu představuje v ladění sady Visual Studio ve vztahu k zdrojový soubor. Popisuje také způsob mapování obslužné rutiny symbolů kontext kódu do kontextu dokumentace ke službě.

 [Kontext vyhodnocení výrazu](../../extensibility/debugger/expression-evaluation-context.md) obsahuje informace kontextu vyhodnocení výrazu v sadě Visual Studio. Třeba kontextu vyhodnocení výrazu přidružený blok zásobníku poskytuje kontext za vaše rozhodnutí vyzkoušet lokální proměnné, parametry metody a členy třídy.

## <a name="related-sections"></a>Související oddíly
 [Ladění koncepty](../../extensibility/debugger/debugger-concepts.md) popisuje hlavní koncepty ladění architektury.

 [Ladění komponenty](../../extensibility/debugger/debugger-components.md) obsahuje základní informace o ladění komponenty, které zahrnují ladicího stroje (DE), Chyba při vyhodnocování výrazu (EE) a obslužné rutiny symbolů (SH) sady Visual Studio.

 [Ladění úlohy](../../extensibility/debugger/debugging-tasks.md) obsahuje odkazy na různé úlohy ladění, například spuštění programu a vyhodnocení výrazů.