---
title: Ladění nativního kódu | Dokumentace Microsoftu
ms.date: 04/11/2017
ms.topic: conceptual
f1_keywords:
- vs.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging native code
- debugging [C++], native code
- debugging [Visual Studio], native code
- native code, debugging
ms.assetid: d94eee90-7e0d-4cac-88c1-9831030daa5e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 872b0e55bb34d7fe0bfa27335ca71165985af1ae
ms.sourcegitcommit: 38db86369af19e174b0aba59ba1918a5c4fe4a61
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/14/2019
ms.locfileid: "54269512"
---
# <a name="debugging-native-code"></a>Ladění nativního kódu
Část popisuje některé běžné problémy ladění a techniky pro nativní aplikace. Techniky popsané v této části jsou techniky vysoké úrovně. Mechanismy pomocí ladicího programu sady Visual Studio, naleznete v tématu [nejdřív se podívejte na ladicí program](../debugger/debugger-feature-tour.md)).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Postupy: Ladění optimalizovaného kódu](../debugger/how-to-debug-optimized-code.md)  
 Poskytuje tipy k ladění optimalizovaného kódu, konkrétně, proč by měl ladit neoptimalizované verzi vašeho programu, výchozí nastavení optimalizace pro konfigurace Debug a Release a tipy pro hledání chyb, které se zobrazí pouze v optimalizovaném kódu (zapnutí Optimalizace v konfiguraci sestavení ladění).  
  
 [DebugBreak a __debugbreak](../debugger/debugbreak-and-debugbreak.md)  
 Popisuje Win32 `DebugBreak` fungovat a získáte odkaz na jeho referenční téma v sadě SDK platformy. Také popisuje `__debugbreak` vnitřní.  
  
 [Kontrolní výrazy jazyka C/C++](../debugger/c-cpp-assertions.md)  
 Tento článek popisuje příkazy kontrolního výrazu, jak fungují, výhody používání jejich (zachycení logických chyb, Kontrola výsledků operace a testování chybové stavy), jejich interakce s `_DEBUG`a různým druhům kontrolní výrazy, které jsou podporovány v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
 [Postupy: Ladění vloženého kódu sestavení](../debugger/how-to-debug-inline-assembly-code.md)  
 Poskytuje obsah krátké pokyny týkající se použití okna zpětného překladu zobrazíte pokyny k sestavení a okno registrů, chcete-li zobrazit registru a obsahuje odkazy na témata týkající se těchto systému windows.  
  
 [Techniky ladění MFC](../debugger/mfc-debugging-techniques.md)  
 Odkazy na postupy pro programy MFC, včetně ladění: nevracení afxdebugbreak – makro trasování, zjišťování paměti v knihovně MFC, knihovny MFC kontrolní výrazy a nezmenšit velikost této knihovny MFC ladění sestavení.  
  
 [Techniky ladění CRT](../debugger/crt-debugging-techniques.md)  
 Halda ladění odkazy k ladění techniky pro knihovny Run-Time jazyka C, včetně použití ladění knihovny CRT, makra pro vytváření sestav, rozdíly mezi malloc a _malloc_dbg, zápis funkce háku a CRT ladění.  
  
 [Nejčastější dotazy k ladění nativního kódu](../debugger/debugging-native-code-faqs.md)  
 Poskytuje odpovědi na nejčastější dotazy týkající se ladění programy v jazyce Visual C++  
  
 [Ladění modelů COM a prvků ActiveX](../debugger/com-and-activex-debugging.md)  
 Obsahuje informace o ladění aplikace modelu COM a ActiveX, včetně nástroje, které můžete použít pro model COM a ActiveX ladění.  
  
 [Postupy: Ladění vloženého kódu](../debugger/how-to-debug-injected-code.md)  
 Obsahuje pokyny k ladění kódu, který používá atributy. Pokyny zahrnují zapnutí zdrojové poznámky, jak zobrazit vloženého kódu a jak zobrazit zpětný překlad kódu v aktuální bod provádění.  
  
 [Návod: Ladění paralelní aplikace](../debugger/walkthrough-debugging-a-parallel-application.md)  
 Popisuje způsob použití **paralelní úlohy** a **paralelní zásobníky** nástroje windows pro ladění paralelní aplikace.  
  
## <a name="related-sections"></a>Související oddíly  
 [Typy projektů Visual C++](../debugger/debugging-preparation-visual-cpp-project-types.md)  
 Obsahuje odkazy na témata, která popisují, jak ladit nativní projekt typy vytvořené šablony projektů Visual C++.  

 [Ladění projektů knihovny DLL](../debugger/debugging-dll-projects.md) poskytuje informace o tom, jak ladit nativní a spravované knihovny DLL.
  
 [První seznámení s ladicím programem](../debugger/debugger-feature-tour.md)  
 Obsahuje odkazy na větší části dokumentace ladění. Obsahuje informace, co je nového v ladicím programu, nastavení a příprava, zarážky, zpracování výjimek, upravit a pokračovat, ladění spravovaného kódu, ladění nativního kódu, ladění SQL a odkazy na uživatelské rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)  
 [Ladění v sadě Visual Studio](../debugger/index.md) 