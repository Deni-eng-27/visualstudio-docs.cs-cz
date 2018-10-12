---
title: Spustitelný pro ladění, dialogové okno relace | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.exefordebug
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- executable files, specifying when debugging
- DLLs, debugging
- debugger, Executable for Debugging Session dialog box
- Executable for Debugging Session dialog box
ms.assetid: c0ddbe32-b99f-4425-acf1-f48842804f56
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2d1279ba5b3ed79c4115143a72e4543bbd6c123d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49189823"
---
# <a name="executable-for-debugging-session-dialog-box"></a>Dialogové okno Spustitelný soubor pro relaci ladění
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Toto dialogové okno se zobrazí při pokusu o ladění knihovny DLL pro kterou žádná spustitelný soubor je určen. Visual Studio nelze spustit knihovnu DLL přímo. Místo toho spustí zadaný spustitelný soubor. Když je volána metodou spustitelný soubor můžete ladit knihovnu DLL.  
  
 **Název spustitelného souboru**  
 Zadejte název cesty do spustitelného souboru, který volá knihovnu DLL, který ladíte.  
  
 **Adresa URL, kde projektu lze získat přístup (pouze Server ATL)**  
 Pokud ladíte knihovnu ATL DLL serveru, zadejte adresu URL, kde lze nalézt projektu.  
  
 Po zadání, tato nastavení jsou uložena v projektu stránky vlastností, takže nebude nutné zadávat znovu při další relace ladění. Pokud potřebujete změnit nastavení, můžete otevřít stránky vlastností a změňte hodnoty. Další informace o zadání spustitelný soubor pro relaci ladění, naleznete v tématu [ladění knihoven DLL](../debugger/how-to-debug-native-dlls.md).  
  
## <a name="see-also"></a>Viz také  
 [Ladění v sadě Visual Studio](../debugger/debugging-in-visual-studio.md)



