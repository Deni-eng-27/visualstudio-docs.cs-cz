---
title: Plán pro rozšíření ladicího programu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], roadmap
- Debugging SDK, roadmap
ms.assetid: 1f4096a8-f7aa-4dfa-84e1-6d59263e70bb
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 89788f97937d05a3ca4858ed35fd854593ce3357
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66315894"
---
# <a name="roadmap-for-extending-the-debugger"></a>Plán pro rozšíření ladicího programu
Tato dokumentace obsahuje průvodce a referenční informace k rozšíření [!INCLUDE[vs_current_short](../../code-quality/includes/vs_current_short_md.md)] ladicí program se [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)].

 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění dokumentace obsahuje ukázky, komplexní referenční informace a několik reprezentativní scénářů, které ukazují obvyklé způsoby přizpůsobení ladicí program.

 Kompilátor a její výstup zjistit, co je potřeba k nastavení ladění produktu. Pokud váš kompilátor:

- Cílí na nativní operační systém Windows a zapíše *. Soubor PDB* soubor, můžete ladit programy s modul ladění nativního kódu (DE), která je součástí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Není nutné implementovat DE nebo výraz Chyba při vyhodnocování. Chyba při vyhodnocování výrazu je určené pro syntaxi programovací jazyk C++.

- Vytvoří Microsoft intermediate language (MSIL) výstup, můžete ladit programy s modul ladění spravovaného kódu DE, která je také součástí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Proto potřebujete pouze implementace vyhodnocovače výrazů. Vyhodnocovací filtr výrazů ukázka poskytuje za vás. Další informace naleznete v následujících tématech:

   [Vyhodnocení výrazu](../../extensibility/debugger/expression-evaluation-visual-studio-debugging-sdk.md)

   [Vyhodnocování výrazů](../../extensibility/debugger/evaluating-expressions.md)

   [Kontext vyhodnocení výrazu](../../extensibility/debugger/expression-evaluation-context.md)

   [Vyhodnocení výrazu v režimu pozastavení](../../extensibility/debugger/expression-evaluation-in-break-mode.md)

   [Zápis běžné vyhodnocovač výrazů modulu runtime jazyka](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)

- Cíle a nechráněný operačního systému nebo jiné běhové prostředí, budete muset napsat vlastní DE. Kurz, který vytvoří jednoduchý DE pomocí knihovny ATL modelu COM je k dispozici. Další informace naleznete v následujících tématech:

   [Vytvoření vlastního ladicího stroje](../../extensibility/debugger/creating-a-custom-debug-engine.md)

   [Kurz: Sestavení ladicí stroj pomocí knihovny ATL modelu COM](https://msdn.microsoft.com/library/9097b71e-1fe7-48f7-bc00-009e25940c24)

   [Implementace dodavatele portu](../../extensibility/debugger/implementing-a-port-supplier.md)

   [Ukázky](../../extensibility/debugger/visual-studio-debugging-samples.md)

## <a name="see-also"></a>Viz také:
- [Začínáme](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)