---
title: Rozšiřitelnost ladicího programu sady Visual Studio | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Visual Studio], Debugging SDK
- Debugging SDK
ms.assetid: c088b6a2-c3ad-446b-830d-9c6f41b2934b
caps.latest.revision: 33
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 0b8d37954bf238b2ed1323bf021fded94ec0c584
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "73983659"
---
# <a name="visual-studio-debugger-extensibility"></a>Rozšiřitelnost programu Visual Studio Debugger
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Visual Studio obsahuje plně interaktivní ladicí program zdrojového kódu, který poskytuje výkonný a snadno použitelný nástroj pro sledování chyb v programu. Ladicí program dokončí podporu Visual Basic, C#, C/C++ a JavaScriptu. Pomocí nástroje [!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)] , který je k dispozici na webu [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=21835), ale mohou být v ladicím programu podporovány jiné programovací jazyky se stejnými funkcemi.  
  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]Ladicí program je běžný front-end (tj. uživatelské rozhraní) na ladicí komponenty, které jsou následně specifické pro jazyk, který je laděn. Pro nové jazyky, které jsou nezbytné pro podporu [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ladicího programu, je vytvoření nezbytných back-endové komponenty, jako je například ladicí stroj (de). To je místo, kde se nachází [!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)] v.  
  
 [!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)]Obsahuje kompletní odkaz na všechny prvky, které jsou [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] nutné k vytvoření nového elementu de. K dispozici jsou také ukázky a kurzy, které vám pomůžou začít.  
  
 Ucelenou ukázku systému projektů jazyka s podporou ladění najdete v [ukázce ironpythonu](https://msdn.microsoft.com/4c41695c-12c1-4670-b43b-d8d84c9e4089).  
  
 Následující části popisují, jak tento ladicí program rozšíříte pomocí [!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)] .  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Začínáme](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)  
 Popisuje [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] , jaké nabídky ladění a jak nainstalovat sadu SDK.  
  
 [Vytvoření vlastního ladicího stroje](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
 Dokumentuje vlastní DE Process, od přípravy programu až po odpojení od DE.  
  
 [Zápis pro vyhodnocovač výrazů modulu CLR](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)  
 Vysvětluje, zda je nutné napsat vyhodnocovací filtr výrazů.  
  
 [Výběr strategie implementace ladicího stroje](../../extensibility/debugger/choosing-a-debug-engine-implementation-strategy.md)  
 Popisuje, jak implementovat správce DE.  
  
 [Odkaz](../../extensibility/debugger/reference/reference-visual-studio-debugging-apis.md)  
 Dokumentuje [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] rozhraní API pro ladění.  
  
 [ukázky](../../extensibility/debugger/visual-studio-debugging-samples.md)  
 Obsahuje odkazy na ukázku vyhodnocení výrazu společného jazykového modulu runtime a ukázku ladicího stroje.
