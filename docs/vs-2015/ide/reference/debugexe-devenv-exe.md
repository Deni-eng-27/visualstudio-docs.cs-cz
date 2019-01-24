---
title: -DebugExe (devenv.exe) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /DebugExe switch
- DebugExe switch
- /DebugExe [devenv.exe]
ms.assetid: cd700006-1648-418f-924b-4b1e5c1412ab
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 1edbcddd27f2c3637e0e56dd9b4841e17ace16af
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54767560"
---
# <a name="debugexe-devenvexe"></a>/DebugExe (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Otevře zadaný spustitelný soubor k ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Devenv /debugexe ExecutableFile  
```  
  
## <a name="arguments"></a>Arguments  
 `ExecutableFile`  
 Povinný parametr. Název a cesta k souboru .exe.  
  
 Pokud soubor .exe se nenašel nebo neexistuje, je zobrazovat žádná upozornění ani chyby a [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] spustí běžným způsobem.  
  
## <a name="remarks"></a>Poznámky  
 Všechny řetězce po `ExecutableFile` parametru jsou předány do tohoto souboru jako argumenty.  
  
## <a name="example"></a>Příklad  
 Následující příklad otevře soubor `MyApplication.exe` pro ladění.  
  
```  
Devenv.exe /debugexe MyApplication.exe  
```  
  
## <a name="see-also"></a>Viz také  
 [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)
