---
title: Aplikace serveru SDI | Microsoft Docs
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
- SDI server applications
- SDI server applications, debugging
ms.assetid: 09713718-1376-4753-b119-26f36639693e
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: feec570217240c7b7dd7d71b7f40987b756869de
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="sdi-server-applications"></a>Aplikace serveru SDI
Pokud ladíte aplikace serveru SDI, je nutné zadat `/Embedding` nebo `/Automation` v **argumenty příkazového řádku** vlastnost *projektu* dialogové okno stránky vlastností pro C/C++, C#, nebo Projekty Visual Basic.  
  
 S těmito argumenty příkazového řádku můžete ladicí program spustit serverové aplikace, jako by se měla spustit z kontejneru. Kontejner od programu Správce nebo správce souborového způsobí kontejneru pro použití instance serveru spuštěna v ladicím programu.  
  
## <a name="finding-the-command-line-arguments-property"></a>Hledání vlastnost argumenty příkazového řádku  
 Abyste měli přístup *projektu* dialogové okno stránky vlastností, klikněte pravým tlačítkem na projekt v Průzkumníku řešení a potom v místní nabídce vyberte možnost Vlastnosti. Chcete-li najít vlastnost argumenty příkazového řádku, rozbalte kategorii vlastnosti konfigurace a klikněte na stránce ladění.  
  
## <a name="see-also"></a>Viz také  
 [COM a prvků ActiveX ladění](../debugger/com-and-activex-debugging.md)   
 [Postupy: ladění serverů modelu COM](../debugger/how-to-debug-com-servers.md)