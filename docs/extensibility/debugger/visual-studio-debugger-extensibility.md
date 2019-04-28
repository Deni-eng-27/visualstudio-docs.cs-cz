---
title: Rozšiřitelnost ladicího programu sady Visual Studio | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Visual Studio], Debugging SDK
- Debugging SDK
ms.assetid: c088b6a2-c3ad-446b-830d-9c6f41b2934b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: df9d1bccb2147d8416555099f3493ceac8c21b4b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62912902"
---
# <a name="visual-studio-debugger-extensibility"></a>Rozšiřitelnost ladicího programu Visual Studio
Visual Studio obsahuje ladicí program kód plně interaktivní zdroje, poskytuje efektivní a snadno použitelné nástroje pro sledování chyby v kódu ve svém programu. Ladicí program má úplnou podporu jazyka Visual Basic, C#, C/C++ a JavaScript. Nicméně s [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)], která je k dispozici [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkId=214453), jiných programovacích jazycích může být podporovaný v ladicím programu pomocí stejné bohaté funkce.

 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Ladicí program pro ladění součásti, které se následně specifické pro jazyk, který se právě ladí běžné front-endu (to znamená, uživatelského rozhraní). Pro nové jazyky, všechny, které je nezbytné pro podporu podle [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladicí program je vytvoření potřebné komponenty back-end, jako je například ladicí stroj (DE). Tento bod je tam, kde [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] je k dispozici ve.

 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] Zahrnuje úplný odkaz na všechny [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] prvky potřebný k vytvoření nové DE. Kromě toho existují ukázek a kurzů, které vám pomůžou vám pomůžou začít.

 Úplnou ukázku systému projektu jazyka s podporu ladění, najdete v článku [IronPython ukázka](https://www.microsoft.com/download/details.aspx?id=55984).

 Následující části popisují, jak rozšířit pomocí ladicího programu [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)].

## <a name="in-this-section"></a>V tomto oddílu
 [Začínáme](../../extensibility/debugger/getting-started-with-debugger-extensibility.md) popisuje, co [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění nabídky a způsobu jejich instalace sady SDK.

 [Vytvoření vlastního ladicího stroje](../../extensibility/debugger/creating-a-custom-debug-engine.md) dokumenty vlastní proces DE od přípravy programu pro Německo do odpojení DE.

 [Zápis vyhodnocovací filtr výrazů CLR](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md) vysvětluje, zda je nutné napsat vyhodnocovače výrazů.

 [Volba strategie implementace modulu ladění](../../extensibility/debugger/choosing-a-debug-engine-implementation-strategy.md) popisuje, jak implementovat vaše DE.

 [Referenční dokumentace](../../extensibility/debugger/reference/reference-visual-studio-debugging-apis.md) dokumenty [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění v rozhraní API.

 [Ukázky](../../extensibility/debugger/visual-studio-debugging-samples.md) obsahuje odkazy na ukázky Chyba při vyhodnocování výrazu modulu runtime běžné jazyka a ukázku ladicí stroj.
