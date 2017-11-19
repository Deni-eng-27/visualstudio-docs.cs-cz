---
title: -Setup (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setup Devenv switch
- /setup Devenv switch
- Devenv, /setup switch
ms.assetid: 87608b7f-a156-400c-80f5-fc823f843e61
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e63b69c9d97edf5049dfb6e55b8f9d5010984d4d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="setup-devenvexe"></a>/Setup (devenv.exe)
Vynutí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] sloučit prostředků metadata, která popisuje nabídek, panely nástrojů a příkaz skupin, ze všech VSPackages k dispozici.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
devenv /setup  
```  
  
## <a name="remarks"></a>Poznámky  
 Tento přepínač nezadávaly žádné argumenty. `devenv /setup` Příkaz je obvykle zadána jako poslední krok procesu instalace. Použití `/setup` přepínač nespustí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 Je nutné spustit `devenv` jako správce, aby bylo možné používat [/Setup (devenv.exe)](../../ide/reference/setup-devenv-exe.md) a [/installvstemplates (devenv.exe)](../../ide/reference/installvstemplates-devenv-exe.md) přepínače.  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje poslední krok v instalaci verze [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] VSPackages, který obsahuje.  
  
```  
devenv /setup  
```  
  
## <a name="see-also"></a>Viz také  
 [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)