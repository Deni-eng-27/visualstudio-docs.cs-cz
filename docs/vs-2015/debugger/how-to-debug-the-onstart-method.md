---
title: 'Postupy: Ladění metody OnStart | Dokumentace Microsoftu'
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
- OnStart method
- debugging [Visual Studio], Windows services
- debugging managed code, OnStart method
- debugging Windows Services applications, OnStart method
- Windows Service applications, debugging
ms.assetid: b06b5d65-424b-490f-bf58-97583cd7006a
caps.latest.revision: 19
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d77d06e720ebe9146f907d8868c46c94addd5d99
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54776609"
---
# <a name="how-to-debug-the-onstart-method"></a>Postupy: Ladění metody OnStart
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Služba Windows můžete ladit spuštění služby a připojování ladicího programu k procesu služby. Další informace najdete v tématu [jak: Ladění aplikace služby Windows](http://msdn.microsoft.com/library/63ab0800-0f05-4f1e-88e6-94c73fd920a2). Ale chcete-li ladit <xref:System.ServiceProcess.ServiceBase.OnStart%2A?displayProperty=fullName> metody služby Windows, musíte spustit ladicí program z uvnitř metody.  
  
1.  Přidejte volání do <xref:System.Diagnostics.Debugger.Launch%2A> na začátku `OnStart()`metody.  
  
    ```csharp  
    protected override void OnStart(string[] args)  
    {  
        System.Diagnostics.Debugger.Launch();  
     }  
    ```  
  
2.  Spusťte službu (můžete použít `net start`, nebo jej spustit v **služby** okno).  
  
     Zobrazí se dialogové okno vypadat asi takto:  
  
     ![OnStartDebug](../debugger/media/onstartdebug.png "OnStartDebug")  
  
3.  Vyberte **Ano, ladit \<název služby >.**  
  
4.  V okně ladicího programu za běhu vyberte verzi sady Visual Studio, kterou chcete použít pro ladění.  
  
     ![JustInTimeDebugger](../debugger/media/justintimedebugger.png "JustInTimeDebugger")  
  
5.  Novou instanci třídy spustí aplikace Visual Studio a provedení je zastaveno `Debugger.Launch()` metody.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)
