---
title: Plán pro rozšíření ladicího programu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], roadmap
- Debugging SDK, roadmap
ms.assetid: 1f4096a8-f7aa-4dfa-84e1-6d59263e70bb
caps.latest.revision: 17
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 59e12a90d241bf07a53cc98c91eef4cfc6d7d063
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60050982"
---
# <a name="roadmap-for-extending-the-debugger"></a>Plán pro rozšíření ladicího programu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Tato dokumentace obsahuje průvodce a referenční informace k rozšíření [!INCLUDE[vs_current_short](../../includes/vs-current-short-md.md)] ladicí program se [!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)].  
  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ladění dokumentace obsahuje ukázky, komplexní referenční informace a několik reprezentativní scénářů, které ukazují obvyklé způsoby přizpůsobení ladicí program.  
  
 Kompilátor a její výstup zjistit, co je potřeba provést k implementaci ladění produktu. Pokud váš kompilátor:  
  
- Cílí na nativní operační systém Windows a zapíše. Soubor PDB, můžete ladit programy s modul ladění nativního kódu (DE), která je součástí [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Nemusíte implementovat DE nebo výraz Chyba při vyhodnocování. Chyba při vyhodnocování výrazu je určené pro syntaxi programovací jazyk C++.  
  
- Vytvoří Microsoft intermediate language (MSIL) výstup, můžete ladit programy s modul ladění spravovaného kódu DE, která je také součástí [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Proto potřebujete pouze implementace vyhodnocovače výrazů. Vyhodnocovací filtr výrazů ukázka poskytuje za vás. Další informace naleznete v následujících tématech:  
  
     [Vyhodnocení výrazu](../../extensibility/debugger/expression-evaluation-visual-studio-debugging-sdk.md)  
  
     [Vyhodnocování výrazů](../../extensibility/debugger/evaluating-expressions.md)  
  
     [Kontext vyhodnocení výrazu](../../extensibility/debugger/expression-evaluation-context.md)  
  
     [Vyhodnocení výrazu v režimu přerušení](../../extensibility/debugger/expression-evaluation-in-break-mode.md)  
  
     [Zápis vyhodnocovače výrazů modulu CLR](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)  
  
- Cíle a nechráněný operačního systému nebo jiné běhové prostředí, budete muset napsat vlastní DE. Kurz, který vytvoří jednoduchý DE pomocí knihovny ATL modelu COM je k dispozici. Další informace naleznete v následujících tématech:  
  
     [Vytvoření vlastního ladicího stroje](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
  
     [Kurz: Vytváření ladicího stroje pomocí knihovny ATL modelu COM](http://msdn.microsoft.com/9097b71e-1fe7-48f7-bc00-009e25940c24)  
  
     [Implementace dodavatele portu](../../extensibility/debugger/implementing-a-port-supplier.md)  
  
     [Ukázky](../../extensibility/debugger/visual-studio-debugging-samples.md)  
  
## <a name="see-also"></a>Viz také  
 [Začínáme](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)
