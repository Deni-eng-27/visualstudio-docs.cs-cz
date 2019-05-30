---
title: Podpora služby jazyka pro ladění | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugger, language support
- language services, debugging support
ms.assetid: 7a44067f-a410-4a6a-84d2-bda5184140bc
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8d4946c25aeac2d677b7a527a3d2bb338db3aa31
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66333651"
---
# <a name="language-service-support-for-debugging"></a>Podpora služby jazyka pro ladění
Služba jazyka může poskytovat funkce, které podporují ladicí program prostřednictvím <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageDebugInfo> rozhraní. Tyto funkce patří ověřování zarážek a poskytnutí seznam výrazů **automatické hodnoty** okna.

 Musíte však mít vyhodnocovače výrazů pro ladění jazyka. Chyba při vyhodnocování výrazu je zodpovědná za vaše rozhodnutí vyzkoušet výrazy k vytvoření hodnot při ladění. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu:

- [Vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)

- [Ukázka Vyhodnocovač spravovaných výrazů](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)

## <a name="compiler-output"></a>Výstup kompilátoru
 Typ kompilátoru jazyka určuje, co je potřeba provést k implementaci ladění pro váš jazyk. Pokud se kompilátor zaměřuje na operační systém Windows a zapíše soubor PDB, můžete ladit programy s nativním kódem ladicím modulu, který je integrovaný do sady Visual Studio. Pokud váš kompilátor vytvoří jazyk Microsoft intermediate language (MSIL), můžete ladit programy se spravovaným kódem ladění modul, který je také integrované do sady Visual Studio. Pokud se kompilátor zaměřuje na proprietární operačního systému nebo jiné běhové prostředí, budete muset napsat vlastní modulu pro ladění.

 Další informace o implementaci ladění jazyka najdete v tématu [Začínáme](../../extensibility/debugger/getting-started-with-debugger-extensibility.md) v aplikaci Visual Studio SDK ladění.