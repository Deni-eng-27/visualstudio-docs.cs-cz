---
title: "Postupy: připojení ke skriptu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- script debugging, attaching to script
- script, attaching to
- processes, attaching to script
- remote debugging, attaching to script
ms.assetid: 82013e9a-ef53-4fd2-b451-a6891cdc6307
caps.latest.revision: "23"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 15143ad050997cd92b21bd342f5d821c9514271a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-attach-to-script"></a>Postupy: Připojení ke skriptu
Toto téma vysvětluje, jak ručně připojit ladicí program Visual Studio do souboru skriptu pro ladění.  
  
### <a name="to-attach-to-a-running-process"></a>Pro připojení k spuštěných procesů  
  
1.  Na **ladění** nabídce zvolte **připojit k procesu**. (Pokud je otevřený žádný projekt, vyberte **připojit k procesu** na **nástroje** nabídky.)  
  
2.  V **připojit k procesu** dialogové okno, podívejte se na **dostupné procesy** seznam a najít skript zpracování je chcete agenta připojit. Můžete určit skript procesy podle **typ** sloupce.  
  
    1.  Pokud proces, který chcete ladit běží na jiném počítači, musíte nejdřív vybrat vzdáleného počítače. Další informace najdete v tématu [postup: Vyberte vzdálený počítač](http://msdn.microsoft.com/en-us/4332ba8e-2f0b-4f62-b96a-e762b9f3c3ba).  
  
    2.  Pokud je proces spuštěný v rámci jiného uživatelského účtu, vyberte **Zobrazit procesy od všech uživatelů** zaškrtávací políčko.  
  
    3.  Pokud jste připojení prostřednictvím **připojení ke vzdálené ploše**, vyberte **Zobrazit procesy ve všech relací** zaškrtávací políčko.  
  
3.  Klikněte na tlačítko proces, který chcete přiřadit.  
  
4.  V **připojit k** pole, měli byste vidět **kód skriptu** nebo **automatické: skript kód**. Pokud se zobrazí cokoliv jiného, postupujte takto:  
  
    1.  Klikněte na tlačítko **vyberte**.  
  
    2.  V **vybrat typ kódu** dialogové okno, klikněte na tlačítko **ladění tyto typy kódu** a vyberte **skriptu**.  
  
    3.  Click **OK**.  
  
5.  Klikněte na tlačítko **připojit**.  
  
     Teď může se zobrazit upozornění oznamující, že je zakázáno ladění skriptů v aplikaci Internet Explorer. Pokud k tomu dojde, přečtěte si téma [upozornění: ladění skriptů zakázáno](../debugger/warning-script-debugging-disabled.md).  
  
 **Dostupné procesy** seznamu se zobrazí automaticky při otevření **procesy** dialogové okno. Procesy můžete spustit a zastavit na pozadí při otevřené dialogové okno. Proto obsah nemusí být vždy aktuální. V seznamu můžete obnovit kdykoli chcete zobrazit aktuální seznam procesů, stisknutím klávesy **aktualizovat** tlačítko.  
  
 Můžete se dá připojit k více programy při ladění, ale pouze jeden program je aktivní v ladicím programu kdykoli. Aktivní aplikaci můžete nastavit na panelu nástrojů ladění umístění. Další informace najdete v tématu [postupy: nastavení aktuální proces](http://msdn.microsoft.com/en-us/7e1d7fa5-0e40-44cf-8c41-d3dba31c969e).  
  
 Všechny **ladění** provádění příkazů nabídky vliv na aktivní aplikaci. Žádné program vyladěnou můžete rozdělit z dialogového okna procesy. V tématu [použití zarážek](../debugger/using-breakpoints.md).  
  
> [!NOTE]
>  Pokud se pokusíte připojit k procesu, který je vlastněn nedůvěryhodné uživatelský účet, zobrazí se dialogové okno potvrzení upozornění zabezpečení. Další informace najdete v tématu [upozornění zabezpečení: připojení k procesu vlastněných nedůvěryhodné uživatelem může být nebezpečný. Pokud tyto informace nezdá nebo si nejste jistí, nepřipojujte tohoto procesu](../debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user-can-be-dangerous-if-the-following-information-looks-suspicious-or-you-are-unsure-do-not-attach-to-this-process.md).  
  
 V některých případech při ladění do relace Terminálové služby (Vzdálená plocha), nebude v seznamu dostupných procesy zobrazí všechny dostupné procesy. Na [!INCLUDE[WinXPSvr](../debugger/includes/winxpsvr_md.md)] nebo novější verze, pokud používáte Visual Studio jako uživatel s omezenými oprávněními, k dispozici procesy seznamu nezobrazí procesů spuštěných ve relace 0, které se používá pro služby a jiné procesy serveru, včetně w3wp.exe. Problém můžete vyřešit tak, že spustíte Visual Studio pomocí účtu správce nebo spuštěním sady Visual Studio z konzoly serveru, nikoli relaci Terminálové služby. Pokud ani jedno z těchto řešení je možné, třetí možnost je k připojení do procesu zadáním vsjitdebugger.exe -p ProcessId na příkazovém řádku Windows. Id procesu můžete určit pomocí tlist.exe. Pokud chcete získat tlist.exe, stáhněte a nainstalujte ladicích nástrojů pro systém Windows, k dispozici na [Windows Hardware Developer centrální](http://go.microsoft.com/fwlink/?linkid=1651).  
  
## <a name="see-also"></a>Viz také  
 [Ladění skriptu](../debugger/client-side-script-debugging.md)   
 [Připojení ke spuštěným procesům](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [Upozornění zabezpečení: Připojení k procesu, jehož vlastníkem je nedůvěryhodný uživatel, může být nebezpečné. Pokud tyto informace nezdá nebo si nejste jistí, nepřipojujte tohoto procesu](../debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user-can-be-dangerous-if-the-following-information-looks-suspicious-or-you-are-unsure-do-not-attach-to-this-process.md)   
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)