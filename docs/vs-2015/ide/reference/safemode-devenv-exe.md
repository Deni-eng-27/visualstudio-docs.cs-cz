---
title: -Nouzový režim (devenv.exe) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /SafeMode Devenv switch
- Devenv, /SafeMode switch
- SafeMode switch
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 4c1cd4b15c3ce3462d6d49eca39fedbc64c744c7
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2019
ms.locfileid: "54767299"
---
# <a name="safemode-devenvexe"></a>/SafeMode (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Spustí [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] v nouzovém režimu, načítání výchozí prostředí a služeb.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
devenv /SafeMode   
```  
  
## <a name="remarks"></a>Poznámky  
 Při načítání rozšíření VSPackages všechny třetích stran zabraňuje tento přepínač [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] se spustí, čímž zajišťuje stabilní spuštění.  
  
## <a name="description"></a>Popis  
 Následující příklad spustí [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] v nouzovém režimu.  
  
## <a name="code"></a>Kód  
  
```  
Devenv.exe /SafeMode  
```  
  
## <a name="see-also"></a>Viz také  
 [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)
