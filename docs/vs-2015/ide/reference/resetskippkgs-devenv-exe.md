---
title: -ResetSkipPkgs (devenv.exe) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /ResetSkipPkgs Devenv switch
- Devenv, /ResetSkipPkgs switch
- ResetSkipPkgs switch
ms.assetid: 7ece64f9-cfa4-4b34-b0d9-1c338b9557b3
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 44e2cb42bf6bf8c1a61512713e9fc87cbe8f0901
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59648507"
---
# <a name="resetskippkgs-devenvexe"></a>/ResetSkipPkgs (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vymaže všechny možnosti, chcete-li přeskočit načítání přidané do balíků VSPackages uživatelé chtějí předejít problém rozšíření VSPackages a pak spustí [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Devenv /ResetSkipPkgs  
```  
  
## <a name="remarks"></a>Poznámky  
 Přítomnost značky SkipLoading zakáže načítání VSPackage; vymazává se značka znovu povolí načítání sady VSPackage.  
  
## <a name="example"></a>Příklad  
 Následující příklad odebere všechny značky SkipLoading.  
  
```  
Devenv.exe /ResetSkipPkgs  
```  
  
## <a name="see-also"></a>Viz také  
 [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)
