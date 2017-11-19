---
title: "Ladění ve smíšeném režimu je podporována pouze při použití rozhraní Microsoft .NET Framework 2.0 nebo 3.0. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.interop_unsupported_to_old
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: f607af6f-57fe-472a-a32e-b6202067aa96
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dd022d8f0a0e38ffbd7402c69f622df74e24bc30
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="mixed-mode-debugging-is-only-supported-when-using-microsoft-net-framework-20-or-30"></a>Ladění ve smíšeném režimu je podporováno, pouze pokud používáte rozhraní Microsoft .NET Framework 2.0 nebo 3.0.
Verze rozhraní Microsoft .NET Framework starší než 2.0 neposkytují podpora ladění ve smíšeném režimu 64bitové procesy. To znamená, že jste nelze krok ze spravovaného kódu do nativního kódu nebo z nativního kódu do spravovaného kódu, při ladění.  
  
 Chcete-li tento problém obejít, můžete:  
  
-   Aktualizujte projektu pro použití buď rozhraní Microsoft .NET Framework 2.0 nebo 3.0.  
  
-   Ladění nativního a spravovaného kódu v samostatných relace ladění.  
  
-   Ladit smíšený kód jako 32bitový proces, jak je popsáno v následujících postupech.  
  
### <a name="to-change-the-operating-system-to-32-bit-visual-basic-or-c"></a>Chcete-li změnit operační systém na 32-bit (Visual Basic a C#)  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt a pak klikněte na tlačítko **vlastnosti** v místní nabídce.  
  
2.  Na stránkách vlastností klikněte **zkompilovat** nebo **ladění** kartě.  
  
3.  Klikněte na tlačítko **platformy**a potom vyberte **x86** ze seznamu platformy.  
  
     Ve výchozím nastavení kompilátory jazyka Visual Basic a C# vytvořit kód pro spuštění na libovolném procesoru. Na 64bitovém počítači spusťte tyto binární soubory jako 64bitové procesy. Pokud chcete spustit u 32-bit procesu, je nutné vybrat **Win32**, nikoli **AnyCPU**.  
  
### <a name="to-change-the-operating-system-to-32-bit-cc"></a>Chcete-li změnit operační systém na 32-bit (C/C++)  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt a pak klikněte na tlačítko **vlastnosti** v místní nabídce.  
  
     Na stránkách vlastností klikněte na tlačítko **platformy**a potom vyberte **Win32** ze seznamu platformy.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   V tématu [nastavení ladění SQL](http://msdn.microsoft.com/en-us/3db09e68-edcc-42de-9c22-4e97cfd55ab3).  
  
## <a name="see-also"></a>Viz také  
 [Ladění 64bitových aplikací](../debugger/debug-64-bit-applications.md)