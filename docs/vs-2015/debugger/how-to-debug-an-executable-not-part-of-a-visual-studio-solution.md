---
title: 'Postupy: ladění spustitelného souboru není součástí řešení sady Visual Studio | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], executables
- executable files, importing
- executable files, debugging outside of projects
ms.assetid: 3ea176e8-1ce5-42c4-b7a2-abe3a2765033
caps.latest.revision: 26
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 36acf39ce892afb2a2601b3149987aa8d7e9f4ab
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675062"
---
# <a name="how-to-debug-an-executable-not-part-of-a-visual-studio-solution"></a>Postupy: Ladění spustitelného souboru, který není součástí řešení sady Visual Studio.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: ladění spustitelný soubor není součástí řešení sady Visual Studio](https://docs.microsoft.com/visualstudio/debugger/how-to-debug-an-executable-not-part-of-a-visual-studio-solution).  
  
V některých případech můžete chtít ladit spustitelný soubor, který není součástí [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] projektu. To může být spustitelný soubor vytvořený mimo sadu [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] nebo spustitelný soubor obdrželi od někoho jiného.  
  
 Obvyklá odpověď na tento problém je spuštění spustitelného souboru mimo sadu Visual Studio a připojit se k němu pomocí [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ladicího programu. Další informace najdete v tématu[připojení k běžící procesy](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
 Připojení k aplikaci vyžaduje určité ruční kroky, což trvá několik sekund. Toto mírné zpoždění znamená, že připojení nepomůže, pokud se pokoušíte ladit problém, ke které dojde během spouštění. Kromě toho Pokud ladíte program, který nečeká na vstup uživatele a rychle skončí, pravděpodobně nemáte čas připojit se k němu. Pokud máte [!INCLUDE[vcprvc](../includes/vcprvc-md.md)] nainstalované, můžete vytvořit projekt EXE pro takový program.  
  
### <a name="to-create-an-exe-project-for-an-existing-executable"></a>Chcete-li vytvořit projekt EXE pro stávající spustitelný soubor  
  
1.  Na **souboru** nabídky, klikněte na tlačítko **otevřít** a vyberte **projektu**.  
  
2.  V **otevřít projekt** dialogové okno, klikněte rozevírací seznam vedle **název_souboru** a vyberte **všechny soubory projektu**.  
  
3.  Vyhledejte spustitelný soubor a klikněte na tlačítko **OK**.  
  
     Tím se vytvoří dočasné řešení, která obsahuje spustitelný soubor.  
  
### <a name="to-import-an-executable-into-a-visual-studio-solution"></a>Import spustitelného souboru do řešení sady Visual Studio  
  
1.  Na **souboru** nabídky, přejděte k **přidat projekt**a potom klikněte na tlačítko **existující projekt**.  
  
2.  V **přidat existující projekt** dialogové okno, klikněte rozevírací seznam vedle **název_souboru** a vyberte **všechny soubory projektu**.  
  
3.  Vyhledejte a vyberte spustitelný soubor.  
  
4.  Klikněte na tlačítko **OK**.  
  
5.  Spusťte spustitelný soubor výběrem příkazu ke spuštění, například **Start**, z **ladění** nabídky.  
  
    > [!NOTE]
    >  Ne všechny programovací jazyky podporují projekty EXE. Nainstalujte [!INCLUDE[vcprvc](../includes/vcprvc-md.md)] Pokud chcete tuto funkci používat.  
  
     Jestliže ladíte spustitelný soubor bez zdrojového kódu, je k dispozici funkce ladění jsou omezeny, ať už jste připojení ke spuštěnému spustitelnému souboru nebo přidat spustitelného souboru k [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] řešení. Pokud spustitelný soubor byl vytvořen bez ladicích informací v kompatibilním formátu, je k dispozici funkce jsou dále omezená. Pokud máte zdrojový kód, nejlepším řešením je import zdrojového kódu do [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] a vytvoření ladicího sestavení spustitelného souboru v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
## <a name="see-also"></a>Viz také  
 [Nastavení ladicího programu a příprava](../debugger/debugger-settings-and-preparation.md)   
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Soubory DBG](http://msdn.microsoft.com/en-us/91e449e9-8b65-4123-960f-2107cd1f1cfd)



