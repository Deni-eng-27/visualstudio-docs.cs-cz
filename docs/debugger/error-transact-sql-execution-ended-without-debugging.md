---
title: "Chyba: Spuštění Transact-SQL skončilo bez ladění. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.sqlde_sql_executed_but_not_debugged
dev_langs:
- CSharp
- VB
- FSharp
- C++
- SQL
ms.assetid: 7a4d4999-3973-4339-ba6a-f0d19bcb1d4a
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: db04460c57dd4ade94154fa1a884477452ee4108
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="error-transact-sql-execution-ended-without-debugging"></a>Chyba: Spuštění Transact-SQL skončilo bez ladění.
K této chybě dojde, když se pokoušíte ladění jazyka Transact-SQL nebo SQLCLR postupu a ladicí program nepřijímá zprávy ladění z SQL serveru.  
  
 Může to být kvůli problémům v síti nebo na problémy na serveru SQL Server, ale nejpravděpodobnější příčinou je problém oprávnění.  
  
 Existují dva účty související se situací:  
  
-   Účet aplikací je uživatelský účet, který [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] běží jako.  
  
-   Účet připojení je identita použitá k připojení k systému SQL Server. Nejedná se nutně stejné jako identity, která Visual Studio je spuštěna jako v případě, že připojení je pomocí ověřování SQL.  
  
 Ladění SQL vyžaduje, aby účet aplikací musí odpovídat účtu připojení nebo sysadmin.  
  
 Pokud používáte přihlašovací jméno SQL jako sa, účet aplikace musí být instalační program systému SQL Server jako správce systému. Ve výchozím nastavení, správci systému SQL server počítač běží na jsou sysadmins systému SQL Server.  
  
 Chcete-li tuto chybu můžete potřebovat k:  
  
-   Ověřte nastavení oprávnění. Další informace najdete v tématu [postupy: nastavení SQL serveru oprávnění pro ladění](http://msdn.microsoft.com/en-us/84e088d0-0409-41d4-841b-f5d4b0fda414).  
  
-   Ujistěte se, že pokud ladění SQL správně nastavené.  
  
-   Podívejte se na správce sítě nebo databáze.  
  
## <a name="see-also"></a>Viz také  
 [Nastavení SQL ladění](http://msdn.microsoft.com/en-us/3db09e68-edcc-42de-9c22-4e97cfd55ab3)   
 [Postupy: nastavení oprávnění serveru SQL pro ladění](http://msdn.microsoft.com/en-us/84e088d0-0409-41d4-841b-f5d4b0fda414)   
 [Nastavení ladicího programu a příprava](../debugger/debugger-settings-and-preparation.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)