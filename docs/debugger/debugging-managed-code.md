---
title: Ladění spravovaného kódu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging managed code
- debugging ASP.NET Web applications, managed code
- managed code, debugging
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: a5cf348b06bca6127690c7b5a7301881bdf75078
ms.sourcegitcommit: 7eb85d296146186e7a39a17f628866817858ffb0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/11/2019
ms.locfileid: "59504143"
---
# <a name="debugging-managed-code"></a>Ladění spravovaného kódu

Tato část popisuje běžné problémy ladění a techniky pro spravované aplikace nebo aplikace napsané v jazycích, které se zaměřují modul common language runtime, jako je například Visual Basic, C# a C++. Technik popsaných tady jsou základní techniky. [Nejdřív se podívejte na ladicí program](../debugger/debugger-feature-tour.md).

## <a name="in-this-section"></a>V tomto oddílu

[Diagnostické zprávy v okně Výstup](../debugger/diagnostic-messages-in-the-output-window.md)\
Popisuje <xref:System.Diagnostics.Debug> a <xref:System.Diagnostics.Trace> třídy, se kterými můžete napsat zpráv za běhu **výstup** okna. Tyto třídy zahrnují metod výstupu, které umožňují výstup informací bez narušení provádění a informace o výstup, který také přeruší provádění, pokud je zadaná podmínka se nezdaří.

[Kontrolní výrazy ve spravovaném kódu](../debugger/assertions-in-managed-code.md)\
Popisuje kontrolní výrazy ve spravovaném kódu, které testování podmínek, které zadáte jako argumenty `Assert` metody. Kromě toho toto téma obsahuje ukázkový kód, informace o použití <xref:System.Diagnostics.Debug> a <xref:System.Diagnostics.Trace> metody třídy, důležité informace v ladění a vydání verzí kódu, vedlejší účinky vyhodnocení argumenty, přizpůsobení vyhodnocení chování a konfigurační soubory.

[Příkazy Stop v jazyce Visual Basic](../debugger/stop-statements-in-visual-basic.md)\
Popisuje `Stop` příkaz, který poskytuje alternativu k nastavením zarážky. Ukázkový kód je také k dispozici, spolu s porovnání mezi `Stop` příkazu a `End` příkaz, a také mezi `Stop` a `Assert` příkazu.

[Návod: Ladění formuláře systému Windows](../debugger/walkthrough-debugging-a-windows-form.md)\
Poskytuje podrobné pokyny pro vytvoření formuláře Windows a ladění, které tvoří. Formuláře Windows, standardní součástí spravované aplikace pro Windows je jedním z nejběžnějších spravovaných aplikací. Tento návod používá Visual C# a Visual Basic, ale jsou obecně podobné techniky pro vytvoření formuláře Windows pomocí C++.

[Ladění metody OnStart](../debugger/how-to-debug-the-onstart-method.md)\
Poskytuje příklady kódu, aby bylo možné ladit `OnStart` metody spravované služby Windows. Chcete-li ladit `OnStart` metody služby Windows, je nutné přidat pár řádků kódu a simulovat služby.

[Ladění ve smíšeném režimu](../debugger/debugging-mixed-mode-applications.md)\
Tento článek popisuje ladění ve smíšeném režimu aplikací. To znamená, že všechny aplikace, která kombinuje nativní kód se spravovaným kódem.

[Chyba: Ladění není možné, protože v systému je povolen ladicí program protokolu Kernel.](../debugger/error-debugging-isn-t-possible-because-a-kernel-debugger-is-enabled-on-the-system.md)\
Popisuje chybová zpráva, která nastane, pokud se pokusíte ladit spravovaný kód na [!INCLUDE[win7](../debugger/includes/win7_md.md)], [!INCLUDE[wiprlhext](../debugger/includes/wiprlhext_md.md)], [!INCLUDE[winxp](../code-quality/includes/winxp_md.md)], [!INCLUDE[Win2kFamily](../code-quality/includes/win2kfamily_md.md)], nebo systém Windows NT, který se spustil v režimu ladění.

[Optimalizace a ladění JIT](../debugger/jit-optimization-and-debugging.md)\
Popisuje účinky optimalizace JIT pro ladění.

[Ladění LINQ a DLINQ](../debugger/debugging-linq.md)\
Tento článek popisuje techniky ladění dotazů LINQ.

[Návod: Ladění paralelní aplikace](../debugger/walkthrough-debugging-a-parallel-application.md)\
Popisuje způsob použití **paralelní úlohy** a **paralelní zásobníky** nástroje windows pro ladění paralelní aplikace.

## <a name="related-sections"></a>Související oddíly

[IntelliTrace](../debugger/intellitrace.md)\
Najdete chyby rychleji a snadněji pomocí zaznamenávání historie spouštění vaší aplikace pomocí nástroje IntelliTrace. Krokovat zpět a vpřed mezi zaznamenané události a volání prozkoumat stav vaší aplikace na klíčových místech v čase. Ladění kódu bez nastavování velkého počtu zarážek nebo aplikací tak, jak často se restartuje. Vyžaduje Visual Studio Enterprise.

[Trasování a instrumentace aplikací](/dotnet/framework/debug-trace-profile/tracing-and-instrumenting-applications)\
Popisuje trasování, způsob, jak můžete monitorovat provádění aplikace při spuštění a instrumentaci, která zahrnuje umístění příkazů trasování na strategická místa v kódu. Toto téma obsahuje také odkazy na úvod do instrumentace a trasování, přepínače trasování, trasovat naslouchací procesy trasování kódu v aplikaci, přidání příkazů trasování do kódu aplikace a Podmíněná kompilace pomocí <xref:System.Diagnostics.Debug> a <xref:System.Diagnostics.Trace> .

[/ ASSEMBLYDEBUG](/cpp/build/reference/assemblydebug-add-debuggableattribute)\
Popisuje linkeru, která přidá <xref:System.Diagnostics.DebuggableAttribute> kód napsaný v jazyce C++. Tento atribut je potřeba pro použití ladění funkcí, jako připojení v jazyce C++.

[Ladění aplikací služby Windows](/dotnet/framework/windows-services/how-to-debug-windows-service-applications)\
Poskytuje důležité informace týkající se ladění aplikace služby Windows, včetně nastavení, připojování k procesu, ladění kódu v služby `OnStart` metodu a kód v hlavní metodě, nastavovat zarážky a pomocí ovládacího prvku služby Správce spuštění, zastavení, pozastavení a pokračování ve službě.

[Ladění a profilace](/dotnet/framework/debug-trace-profile/index)\
Tento článek popisuje požadavky na konfiguraci a ladění aplikací rozhraní .NET Framework.

[Ladění skriptů a webových aplikací](/visualstudio/debugger/how-to-enable-debugging-for-aspnet-applications)\
Popisuje běžné problémy ladění a postupy, které se můžete setkat při ladění skriptu a webové aplikace.

## <a name="see-also"></a>Viz také:

- [Návod: Ladění ovládacích prvků vlastní Windows Forms v době návrhu](/dotnet/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time)
- [Zabezpečení ladicího programu](../debugger/debugger-security.md)
- [Ladění v sadě Visual Studio](../debugger/index.md)
- [První seznámení s ladicím programem](../debugger/debugger-feature-tour.md)