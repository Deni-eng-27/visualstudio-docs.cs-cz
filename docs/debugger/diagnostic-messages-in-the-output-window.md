---
title: "Odeslat diagnostické zprávy do okna výstupu | Microsoft Docs"
ms.custom: 
ms.date: 04/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- diagnostic messages [C#]
- System.Diagnostics.Debug class, Output window
- messages, diagnostic
- Debug.Print replacements
- diagnosis
- Output window, diagnostic messages
- System.Diagnostics.Trace class, Output window
- Trace class, diagnostic messages
- diagnostics
- debugger, Output window
- debugging [Visual Studio], diagnostic messages in Output window
- Debug class
ms.assetid: 386e9524-be17-4573-83fb-4f7c5cae0be0
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f2b898921b022dde9a666a42725bf63c0bb9e6ef
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="send-diagnostic-messages-to-the-output-window"></a>Odeslat diagnostické zprávy v okně Výstup
Můžete napsat běhu zprávy a pokuste se **výstup** pomocí okna `Debug` – třída nebo `Trace` třídy, které jsou součástí z <xref:System.Diagnostics> knihovny tříd. Použití třídy ladění, pokud pouze výstup v ladicí verze vašeho programu. Používejte třídu trasování, pokud chcete, aby výstupu v ladění i vydání verze.  
  
## <a name="output-methods"></a>Výstup metody  
 <xref:System.Diagnostics.Trace> a <xref:System.Diagnostics.Debug> tříd poskytuje následující metody výstup:  
  
-   Různé `Write` metody, které výstupem informací bez pozastavení provádění. Tyto metody nahradit `Debug.Print` metodu použitou v předchozích verzích jazyka Visual Basic.  
  
-   <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>a <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName> metody, které rozdělit informace o provádění a výstupy, pokud je zadaná podmínka selže. Ve výchozím nastavení `Assert` metoda zobrazí informace v dialogovém okně. Další informace najdete v tématu [kontrolní výrazy ve spravovaného kódu](../debugger/assertions-in-managed-code.md).  
  
-   <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=fullName> a <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=fullName> metody, které vždy dělí provádění a výstupy informace. Ve výchozím nastavení `Fail` metody zobrazení informací v dialogovém okně.  
  
 Kromě program se z vaší aplikace **výstup** okno může zobrazit informace o:  
  
-   Moduly ladicí program má načten nebo odpojeno.  
  
-   Výjimky, které jsou vyvolány.  
  
-   Procesy, které ukončete.  
  
-   Vláken, která ukončete.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Výstup – okno](../ide/reference/output-window.md)   
 [Trasování a instrumentace aplikací](/dotnet/framework/debug-trace-profile/tracing-and-instrumenting-applications)  
 [C#, F # a typy projektů jazyka Visual Basic](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)