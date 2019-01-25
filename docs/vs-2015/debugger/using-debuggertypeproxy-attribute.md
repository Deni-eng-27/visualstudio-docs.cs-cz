---
title: Používání atributu DebuggerTypeProxy | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- attributes [C#], debugger
- DebuggerTypeProxyAttribute class
- DebuggerTypeProxy attribute
ms.assetid: 943f3bb1-993e-4800-a47e-0af78b063014
caps.latest.revision: 27
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ca1b84990ed2747e530a1a83a17e17b99f36b116
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54777852"
---
# <a name="using-debuggertypeproxy-attribute"></a>Používání atributu DebuggerTypeProxy
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Debuggertypeproxyattribute –] (assetId:///T:System.Diagnostics.DebuggerTypeProxyAttribute?qualifyHint=False & autoUpgrade = True) určuje proxy server nebo stand-in pro typ a změny tak, jak typ se zobrazí v oknech ladicího programu. Pokud zobrazíte proměnnou, která má proxy server, proxy zastupuje původní typ v **zobrazit**. V okně proměnné ladicího programu se zobrazí pouze veřejné členy typu proxy. Soukromé členy nejsou zobrazeny.  
  
 Tento atribut lze použít pro:  
  
- Struktury  
  
- Třídy  
  
- Sestavení  
  
  Typ třídy proxy server musí mít konstruktor, který přebírá argument typu, který nahradí proxy serveru. Ladicí program vytvoří novou instanci třídy proxy pokaždé, když je potřeba zobrazení proměnné cílového typu. To může mít vliv na výkon. V důsledku toho by neměla provést žádné další práci v konstruktoru, než je nezbytně nutné.  
  
  Chcete-li minimalizovat snížení výkonu, vyhodnocovací filtr výrazů nezkoumá atributy u proxy zobrazení typu Pokud typ rozbalen uživatel kliknutím + symbol v okně ladicího programu, nebo pomocí <xref:System.Diagnostics.DebuggerBrowsableAttribute>. Proto by neměl umístit atributy na samotném zobrazení typu. Atributy lze a by měl být použit v těle typu zobrazení.  
  
  Je vhodné pro proxy server typů být privátní vnořené třídy v rámci třídy, které cíle atributů. To umožňuje snadno získat přístup vnitřní členy.  
  
  Pokud <xref:System.Diagnostics.DebuggerTypeProxyAttribute> se používá na úrovni sestavení `Target` parametr určuje typ, který nahradí proxy serveru.  
  
  Příklad, jak používat tento atribut spolu s <xref:System.Diagnostics.DebuggerDisplayAttribute> a <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, naleznete v tématu[pomocí atributu DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md).  
  
## <a name="using-generics-with-debuggertypeproxy"></a>Použití obecných typů pomocí DebuggerTypeProxy  
 Podpora je omezená. Pro jazyk C# `DebuggerTypeProxy` typů podporuje pouze otevřít. Otevřený typ, zkratka typu unconstructed je obecného typu, která nebyla vytvořena instance s argumenty pro svoje parametry typu. Uzavřené typy zkratka sestavené typy nejsou podporované.  
  
 Syntaxe pro otevřený typ. vypadá takto:  
  
 `Namespace.TypeName<,>`  
  
 Pokud jako cíl v použití obecného typu `DebuggerTypeProxy`, je nutné použít tuto syntaxi. `DebuggerTypeProxy` Mechanismus parametry typu odvodí z nich za vás.  
  
 Další informace o typech otevřené a uzavřené v jazyce C# najdete v článku [specifikace jazyka C#](http://msdn.microsoft.com/library/e5d5a5cc-636b-4bff-b9c8-a8edc6207c22), otevřete část 20.5.2 a uzavření typů.  
  
 Visual Basic nemá otevřeného typu syntaxe proto nelze provést totéž v jazyce Visual Basic. Místo toho musíte použít řetězec představující název otevřeného typu.  
  
 `"Namespace.TypeName'2"`  
  
## <a name="see-also"></a>Viz také  
 [Používání atributu DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md)   
  [Rozšíření ladění pomocí atributů zobrazení ladicího programu](http://msdn.microsoft.com/library/72bb7aa9-459b-42c4-9163-9312fab4c410)
