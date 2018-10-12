---
title: Problémy se zabezpečením | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security [Debugging SDK]
- debugging [Debugging SDK], security
ms.assetid: d6ffff0a-afb4-4f38-86d8-476c881c4e4b
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4c20ef751960bed02b6b6b1d393f168a9b8e510f
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49219372"
---
# <a name="security-issues"></a>Problémy se zabezpečením
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Chcete-li ladit aplikaci pomocí sady Visual Studio, jsou pouze potřebná oprávnění stejné těmi, které vývojář potřebuje ke spuštění programu. To zahrnuje, vzdálené ladění pro většinu situací (někdy zahrnující jiných služeb, jako je například Internetová informační služba může vyžadovat vyšší úroveň oprávnění).  
  
 Když je spuštěná sada Visual Studio, sleduje správce ladění procesu (PDM) ladění procesů na místním počítači. Vzdáleně je spuštěn program s názvem msvsmon.exe vývojářem pro zpracování, vzdálené ladění a zpřístupnit PDM. (Všimněte si, že msvsmon.exe není služba a musí být spuštěna ručně povolit vzdálené ladění na tomto počítači.) Pokud sadu Visual Studio (nebo msvsmon.exe) není spuštěna, žádné procesy jsou sledována pro ladění.  
  
 To znamená, že vývojář můžete ladit programy, které uživatel začít žádná zvláštní oprávnění. Vývojář můžete dokonce ladit procesy spuštěné někým jiným, pokud tato osoba je členem stejné skupiny zabezpečení. A pokud chcete povolit vzdálené ladění, je nezbytné pouze ke zkopírování nezbytné soubory do vzdáleného počítače a spuštění msvsmon.exe (naleznete v tématu [nastavit Up the Remote Tools na zařízení](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c) další podrobnosti).  
  
## <a name="see-also"></a>Viz také  
 [Ladění úloh](../../extensibility/debugger/debugging-tasks.md)   
 [Správce ladění procesu](../../extensibility/debugger/process-debug-manager.md)   
 [Nastavení nástroje Remote Tools na zařízení](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)

