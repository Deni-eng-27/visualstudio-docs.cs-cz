---
title: Kombinovaný režim ladění pro x64 procesy se podporuje jenom při použití Microsoft.NET Framework 4 nebo vyšší | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.interop_unsupported_x64
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: b7495655-54c0-4315-8422-43bf63b8c22e
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0297d9bcfb380261d2ad2e73853ded70285f1b35
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666512"
---
# <a name="mixed-mode-debugging-for-x64-processes-is-only-supported-when-using-microsoftnet-framework-4-or-greater"></a>Ladění ve smíšeném režimu pro procesy x64 je podporováno, pouze pokud používáte rozhraní Microsoft .NET Framework 4 nebo vyšší
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [kombinovaný režim ladění pro x64 procesy se podporuje jenom při použití Microsoft.NET Framework 4 nebo vyšší](https://docs.microsoft.com/visualstudio/debugger/mixed-mode-debugging-for-x64-processes-is-only-supported-when-using-microsoft-dotnet-framework-4-or-greater).  
  
Rozhraní .NET Framework verze nižší než 4 se neposkytuje podporu pro ladění ve smíšeném režimu x64 zpracovává. To znamená, že nelze krokovat ze spravovaného kódu do nativního kódu nebo z nativního kódu pro spravovaný kód při ladění.  
  
### <a name="workarounds"></a>Alternativní řešení  
  
-   Aktualizujte projekt pro použití rozhraní Microsoft .NET Framework 4 nebo novější.  
  
     – nebo –  
  
     Ladění spravovaného a nativního kódu v samostatné relace ladění.  
  
     – nebo –  
  
     Ladit smíšený kód jako 32bitový proces, jak je popsáno v následujících postupech.  
  
### <a name="to-change-the-platform-to-32-bit-visual-basic-or-c"></a>Chcete-li změnit platformu na 32 bitů (Visual Basic nebo C#)  
  
1.  V **Průzkumníka řešení**, klikněte pravým tlačítkem na projekt a potom klikněte na tlačítko **vlastnosti**.  
  
2.  Na stránkách vlastností, klikněte na tlačítko **kompilaci** nebo **ladění** kartu.  
  
3.  Klikněte na tlačítko **platformy** a vyberte x86 ze seznamu platformy.  
  
     Ve výchozím nastavení výchozí kompilátory jazyka Visual Basic a C# vytvářet kód pro spuštění na jakýkoli procesor. Na 64bitovém počítači spusťte tyto binární soubory jako 64bitové procesy. Ke spuštění na 32bitový proces, musíte zvolit **Win32**, nikoli **AnyCPU**.  
  
### <a name="to-change-the-platform-to-32-bit-cc"></a>Chcete-li změnit platformu na 32 bitů (C/C++)  
  
1.  V **Průzkumníka řešení**, klikněte pravým tlačítkem na projekt a pak klikněte na tlačítko **vlastnosti**.  
  
2.  Na stránkách vlastností, klikněte na tlačítko **platformy** a vyberte ze seznamu platformy Win32.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Zobrazit [nastavení ladění SQL](http://msdn.microsoft.com/en-us/3db09e68-edcc-42de-9c22-4e97cfd55ab3).  
  
## <a name="see-also"></a>Viz také  
 [Ladění 64bitové aplikace](../debugger/debug-64-bit-applications.md)



