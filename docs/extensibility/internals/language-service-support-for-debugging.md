---
title: Podpora služby jazyka pro ladění | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugger, language support
- language services, debugging support
ms.assetid: 7a44067f-a410-4a6a-84d2-bda5184140bc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7ebb0293e17fe022fc04c9e4e6724fa49a8c3056
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54994222"
---
# <a name="language-service-support-for-debugging"></a>Podpora služby jazyka pro ladění
Služba jazyka může poskytovat funkce, které podporují ladicí program prostřednictvím <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageDebugInfo> rozhraní. Tyto funkce patří ověřování zarážek a poskytnutí seznam výrazů **automatické hodnoty** okna.  
  
 Musíte však mít vyhodnocovače výrazů pro ladění jazyka. Chyba při vyhodnocování výrazu je zodpovědná za vaše rozhodnutí vyzkoušet výrazy k vytvoření hodnot při ladění. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu:  
  
-   [Vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)  
  
-   [Ukázka Vyhodnocovač spravovaných výrazů](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)  
  
## <a name="compiler-output"></a>Výstup kompilátoru  
 Typ kompilátoru jazyka určuje, co je potřeba provést k implementaci ladění pro váš jazyk. Pokud se kompilátor zaměřuje na operační systém Windows a zapíše soubor PDB, můžete ladit programy s nativním kódem ladicím modulu, který je integrovaný do sady Visual Studio. Pokud váš kompilátor vytvoří jazyk Microsoft intermediate language (MSIL), můžete ladit programy se spravovaným kódem ladění modul, který je také integrované do sady Visual Studio. Pokud se kompilátor zaměřuje na proprietární operačního systému nebo jiné běhové prostředí, budete muset napsat vlastní modulu pro ladění.  
  
 Další informace o implementaci ladění jazyka najdete v tématu [Začínáme](../../extensibility/debugger/getting-started-with-debugger-extensibility.md) v aplikaci Visual Studio SDK ladění.