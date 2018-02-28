---
title: "Odesílání událostí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], sending events
ms.assetid: 064231e7-59b5-4437-8240-a23c0a7ec2a9
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 2bfdefc3202a026516edb3f9221e0626e1a83b4b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="sending-events"></a>Odesílání událostí
Tento mechanismus pro komunikaci mezi ladicího programu a modul ladění (DE) je model událostí podle modelu DCOM. Události se odesílají jako objekty modelu COM a jednotlivých událostí obsahuje parametry, které zadejte následující informace:  
  
-   Německo, která volá událost.  
  
-   Popis co se stalo.  
  
-   Proces, program a vlákno informace, které identifikují kontextu kde k události došlo. Proces se neposílají odeslaný Zavedenými události.  
  
-   Typ události, který určuje, zda je událost synchronní nebo asynchronní.  
  
 Všechny události ladění se posílají pomocí metody [IDebugEventCallback2::Event](../../extensibility/debugger/reference/idebugeventcallback2-event.md).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Zdroje událostí](../../extensibility/debugger/event-sources-visual-studio-sdk.md)  
 Popisuje dva zdroje událostí: ladění modulu (DE) a relace ladění manager (SDM).  
  
 [Podporované typy událostí](../../extensibility/debugger/supported-event-types.md)  
 Popisuje typy aktuálně podporované událostí: asynchronní a synchronní.  
  
 [Popisy událostí](../../extensibility/debugger/event-descriptions.md)  
 Definuje události a důvody pro jejich použití.  
  
## <a name="related-sections"></a>Související oddíly  
 [Vytvoření vlastního ladicího stroje](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
 Popisuje, jak funguje Zavedenými s překladač nebo operačního systému k poskytování ladění služeb.