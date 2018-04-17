---
title: 'Postupy: shromažďovat trasování událostí pro Windows (ETW) Data | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.property.events
helpviewer_keywords:
- event trace providers, performance tools
- profiling tools, event trace providers
- performance tools, enabling event trace providers
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8001f62a7fdc85a251e33eb03765d620d3bb87d2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-collect-event-tracing-for-windows-etw-data"></a>Postupy: Shromažďování dat Trasování událostí pro Windows

Události trasování událostí pro Windows (ETW) je zařízení efektivní jádra úroveň trasování, které umožňuje jádra protokolu profileru nebo události definované aplikací. Data, která se shromažďují ze zprostředkovatele událostí lze zobrazit pouze pomocí /**souhrn: ETW** možnost [vsperfreport –](../profiling/vsperfreport.md) nástroj příkazového řádku. Tato sestava slouží k určení, kde dojde k problémům s výkonem v aplikaci.

> [!NOTE]
> Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

## <a name="to-enable-event-trace-providers"></a>Chcete-li povolit zprostředkovatelé trasování událostí

1. V **prohlížeč výkonu**, klikněte pravým tlačítkem na výkonnostní relace a pak klikněte na tlačítko **vlastnosti**.

2. V **stránky vlastností**, klikněte **události systému Windows** vlastnosti.

3. V **zprostředkovatel trasování událostí vyberte ke shromažďování dat z** vyberte zprostředkovatelů událostí, které chcete použít pro profil aplikace.

## <a name="see-also"></a>Viz také

[Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)