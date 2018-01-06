---
title: "Vytváření vlastní ladění modul | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debug engines, implementing
- debug engines, custom
- debugging [Debugging SDK], custom debug engines
ms.assetid: 52794238-6fae-451c-bf1c-99f344c6f173
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 0edee6528919cfe28c542be850b9a104188ce403
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="creating-a-custom-debug-engine"></a>Vytváření vlastních ladění modulu
Modul ladění (DE) je komponenta umožňující ladění konkrétní běhu architektury. Je obvykle pouze jeden implementace DE za běhu prostředí.  
  
> [!NOTE]
>  Existují samostatné implementace DE Transact-SQL a JScript a VBScript, JScript sdílet jeden DE.  
  
 Zavedenými pracuje s překladač nebo operace systému k poskytování těchto ladění služeb jako zkušební spuštění řízení, zarážky a výraz. Tyto služby jsou implementovány pomocí rozhraní DE a může způsobit ladicí program na přechod mezi různé režimy provozu. Další informace najdete v tématu [provozní režimy](../../extensibility/debugger/operational-modes.md).  
  
 Vytvoření Zavedenými se skládá z následujících kroků:  
  
1.  Registrace Zavedenými pomocí sady Visual Studio  
  
2.  Povolení program chcete ladit  
  
3.  Provádění řízení a stav vyhodnocení  
  
4.  Odesílání událostí  
  
5.  Ukončení a odpojení  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Registrace vlastního ladicího stroje](../../extensibility/debugger/registering-a-custom-debug-engine.md)  
 Popisuje kroky potřebné k registraci modul ladění pomocí sady Visual Studio, takže lze jej použít.  
  
 [Povolení ladění programu](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)  
 Vysvětluje, že před vaší DE můžete ladit program, musí nejprve spuštění DE nebo připojení k existující aplikaci.  
  
 [Řízení provádění a vyhodnocení stavu](../../extensibility/debugger/execution-control-and-state-evaluation.md)  
 Popisuje, proč ladění aplikace vyžaduje implementace funkce řízení provádění.  
  
 [Odesílání událostí](../../extensibility/debugger/sending-events.md)  
 Popisuje komunikaci mezi ladicího programu a je DE jako model událostí podle modelu DCOM.  
  
 [Ukončení a odpojení](../../extensibility/debugger/termination-and-detaching.md)  
 Vysvětluje, jak zajistit normální ukončení, což znamená, že neexistují žádné zarážky, výjimky, chyby nebo nekonečné smyčky v aplikaci chcete ladit.  
  
 [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md)  
 Dokumenty volání pořadí událostí, ke kterým dochází v relaci ladění.  
  
 [Postupy: Ladění vlastního ladicího stroje](../../extensibility/debugger/how-to-debug-a-custom-debug-engine.md)  
 Vysvětluje, jak ladit vlastní DE.  
  
## <a name="see-also"></a>Viz také  
 [Rozšiřitelnost programu Visual Studio Debugger](../../extensibility/debugger/visual-studio-debugger-extensibility.md)