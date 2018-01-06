---
title: "Distribuce aplikací izolované prostředí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c503a985-d67a-4ef8-9123-7744a78f2f17
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 6e9b7ded8d24e4d252d29338d89bd176648511a9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="distributing-isolated-shell-applications"></a>Distribuce aplikací izolované prostředí
Chcete-li vytvořit aplikaci izolované prostředí je třeba nainstalovat Visual Studio a sadu Visual Studio SDK. Pokud chcete distribuovat aplikace na počítače, další uživatelé nebo zákazníci, musí obsahovat speciální redistributable package pro izolované prostředí.  
  
## <a name="prerequisites-for-distributing-isolated-shell-applications"></a>Předpoklady pro distribuci aplikací izolované prostředí  
  
|Název|Popis|  
|----------|-----------------|  
|Visual Studio SDK|Sada SDK, musíte mít pro vývoj a testování rozšíření [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Sady SDK můžete také vytvořit vlastní instanci prostředí sady Visual Studio izolované.<br /><br /> Visual Studio je předpokladem pro sadu SDK.|  
|Izolované prostředí Redistributable sady Microsoft Visual Studio|Redistributable při sestavování prostředí nástroje v sadě Visual Studio zahrnout do instalačního programu izolované prostředí. Izolované prostředí redistribuovatelného balíčku zahrnuje rozhraní .NET Framework 4.5.|  
  
## <a name="creating-an-installation-program-for-the-application"></a>Vytváření instalační Program pro aplikaci  
 Pro aplikace integrované nebo izolované prostředí, je nutné vytvořit speciální instalační program. Další informace najdete v tématu [instalaci izolované aplikace prostředí](installing-an-isolated-shell-application.md).  
  
## <a name="allowing-for-updates-to-your-application"></a>Povolení aktualizací do vaší aplikace  
 Instalační program musíte povolit možnost, že aplikace budou aktualizovány, Microsoft aktualizace nebo aktualizace vaší společnosti. Další informace o aktualizacích naleznete v části [obsluhy pokyny pro izolované prostředí aplikace](servicing-guidelines-for-isolated-shell-applications.md).