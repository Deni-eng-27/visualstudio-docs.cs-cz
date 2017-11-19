---
redirect_url: shell/modifying-the-isolated-shell-by-using-the-dot-pkgundef-file
title: "Úprava izolované prostředí pomocí. Soubor Pkgundef | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio shell, isolated mode, .pkgundef file
ms.assetid: 9cee2a20-f8ac-4d9d-aef9-068fcd9f27a4
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3b4c0f46924c2c828158960a924faa031be0fd14
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="modifying-the-isolated-shell-by-using-the-pkgundef-file"></a>Úprava izolované prostředí pomocí. Soubor Pkgundef
Můžete upravit soubor .pkgundef chcete vyloučit položky registru z aplikace izolované prostředí. Obvykle při prvním spuštění aplikace v počítači, prostředí sady Visual Studio zkopíruje existující položky registru Visual Studio na kořenový klíč registru pro aplikaci. To zahrnuje všechny odkazy na aktuálně nainstalovaná VSPackages.  
  
 Vyloučit konkrétní registru položku z aplikace izolované prostředí, přidejte k souboru aplikace .pkgundef klíč balíček a potom v položce. Klíče a položky jsou reprezentovány jako v případě souboru .pkgdef; To znamená jako [$RootKey$] nebo [$RootKey$\\*podklíč*] a "*položka*" =*hodnotu*, kde *podklíč* je podklíč ovlivnit, *položka* položkou odebrat, a *hodnotu* je buď `""` nebo `dword:00000000`.  
  
 Několik záznamů vyloučit z klíče registru, právě seznamu klíč jednou, a řádek pro každou položku k vyloučení.  
  
 Vyloučit celý klíč z aplikace izolované prostředí, přidejte klíč k .pkgundef souboru aplikace, ale nezadávejte žádné položky registru pro tento klíč.  
  
 Komentáře můžete přidat do souboru .pkgundef. Jeden řádek komentář musí mít dvě lomítka jako první dva znaky.  
  
 Například odebrat **připojit k databázi** a **připojit k používat r** příkazy **nástroje** nabídky, můžete Odkomentujte řádek:  
  
```  
[$RootKey$\Packages\{8D8529D3-625D-4496-8354-3DAD630ECC1B}]  
```  
  
 a přidejte řádek:  
  
```  
[$RootKey$\Packages\{198E76C1-34C0-424D-9957-B3EBD80265FB}]  
```  
  
 do souboru .pkgundef aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Identifikátory GUID balíčku funkce sady Visual Studio](../extensibility/package-guids-of-visual-studio-features.md)   
 [Přizpůsobení izolované prostředí](../extensibility/customizing-the-isolated-shell.md)