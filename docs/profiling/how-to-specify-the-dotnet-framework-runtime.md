---
title: "Postupy: Zadejte modul Runtime rozhraní .NET Framework | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Profiling Tools, .NET Framework versions
- .NET Framework versions,profililng
ms.assetid: d39f3579-719a-4f47-a97d-5b4232fe4c64
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: a060315c17dfc351aaa3cba5fec52fdcfc3f9b0c
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2018
---
# <a name="how-to-specify-the-net-framework-runtime"></a>Postupy: Zadejte modul Runtime rozhraní .NET Framework

S vydáním [!INCLUDE[net_v40_long](../code-quality/includes/net_v40_long_md.md)], aplikace se může skládat z modulů, které byly vytvořeny pomocí různých verzích [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] spuštění. Ve výchozím nastavení profilu profilace nástroje sady Visual Studio první modul runtime, který je načten aplikací. Můžete zadat běhu profilu při spuštění aplikace s profilerem a při připojení profileru k aplikaci již spuštěné.

## <a name="to-specify-the-net-framework-run-time-to-profile-when-starting-an-application-with-the-profiler"></a>K určení běhu rozhraní .NET Framework profil při spuštění aplikace s profilerem

1. V **prohlížeč výkonu**, klikněte pravým tlačítkem na výkonnostní relace, klikněte na **vlastnosti**a potom klikněte na **Upřesnit**.

     **Cílová verze CLR** seznamu zobrazí pole **automatické** a verze [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] modulu runtime, zda jsou nainstalovány v počítači.

2. Proveďte jeden z následujících kroků:

    - Klikněte na verzi modulu CLR, které chcete profil.

    - Klikněte na tlačítko **automatické** profilu první verze zavedená aplikace.

## <a name="to-specify-the-net-framework-run-time-to-profile-when-attaching-the-profiler-to-an-application"></a>Chcete-li určit běhu rozhraní .NET Framework profil při připojení profileru k aplikaci

1. V nabídce analyzovat přejděte na profileru a pak klikněte na tlačítko Připojit nebo odpojit.

2. Na připojení profileru k procesu – dialogové okno klikněte na proces, který chcete profil.

     **Cílová verze CLR** pole se seznamem s **automatické** a verze [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] modulu runtime, zda jsou nainstalovány v počítači.

3. Proveďte jeden z následujících kroků:

    - Klikněte na verzi modulu CLR, které chcete profil.

    - Klikněte na tlačítko **automatické** profilu na verzi, která se načtou při profileru připojí k aplikaci.