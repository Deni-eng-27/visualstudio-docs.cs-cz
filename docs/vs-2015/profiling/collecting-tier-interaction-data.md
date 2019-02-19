---
title: Shromažďování dat interakce vrstev | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.property.tierinteraction
helpviewer_keywords:
- Profiling Tools,ADO.NET profiling
- tier interaction profiling method
- Profiling Tools,tier-interaction method
- ADO.NET performance profiling
ms.assetid: 47a944c2-3098-497c-8fc7-e1f43d750bbc
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: abe38162f20fb73de04301e97974dc348d704b6f
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2019
ms.locfileid: "54770882"
---
# <a name="collecting-tier-interaction-data"></a>Shromažďování dat interakce vrstev
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Profilování interakce vrstev poskytuje další informace o spuštění s úspěšností funkce víceúrovňových aplikací, které komunikují s databázemi prostřednictvím služeb ADO.NET. Data se shromažďují pouze pro synchronní volání.  
  
 **Visual Studio editions**  
  
 Dat profilace interakce vrstev lze shromažďovat pomocí Visual Studio Ultimate, Visual Studio Premium nebo Visual Studio Professional. Nicméně data profilace interakce vrstev lze zobrazit pouze ve VS Ultimate a VS Premium.  
  
 **Windows 8 a Windows Server 2012**  
  
 Ke shromažďování dat interakce vrstev v aplikacích klasické pracovní plochy systému Windows 8 a Windows Server 2012 aplikace, musíte použít metody instrumentace. Nelze shromažďování dat interakce vrstev pro aplikace Windows Store. Zobrazit [nástroje pro výkon v aplikacích Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md). Dat interakce vrstev můžete zahrnout všechny metody profilování na ostatní podporované verze systému Windows.  
  
 **Průvodce výkonu**  
  
 Z důvodu chyby v Průvodci výkonu je nutné přidat možnost kolekce dat interakce vrstvy do běhu profilování z prohlížeče výkonu. Musíte také přidat projekt, spustitelný soubor nebo web na cílový uzel prohlížeč výkonu.  
  
### <a name="to-add-tier-interaction-data-to-a-profiling-run-by-using-the-performance-session-property-pages"></a>Přidání dat interakce vrstev pro profilování pomocí stránky vlastností relace výkonu  
  
1.  V Průzkumníku výkonu, zvolte **vlastnosti** v místní nabídce.  
  
2.  Vyberte **interakce vrstev** stránce a potom zkontrolujte **povolit profilaci interakce vrstev** zaškrtávací políčko.  
  
3.  V prohlížeči výkonu, vyberte **cíle** uzel a pak zadejte projekt, spustitelný soubor nebo web, který chcete Profilovat.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení interakcí vrstev](../profiling/tier-interactions-view.md)
