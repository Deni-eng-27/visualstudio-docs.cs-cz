---
title: -Out (devenv.exe) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- errors [Visual Studio], builds
- Devenv, /out switch
- builds [Visual Studio], logs
- error logs [Visual Studio], command-line build errors
- error logs [Visual Studio]
- /out Devenv switch
- out Devenv switch
- builds [Visual Studio], errors
- output files, build errors
ms.assetid: 9002d8c2-36d4-451c-b489-8f01932f31f7
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: e1f20b446d355ea0cbc6700de5f2e6f79de51d09
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59647058"
---
# <a name="out-devenvexe"></a>/Out (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Určuje soubor k uložení a zobrazení chyb při spuštění, sestavování, znovu sestavit nebo nasadit řešení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
devenv /out FileName  
```  
  
## <a name="arguments"></a>Arguments  
 `FileName`  
 Povinný parametr. Cesta a název souboru, který se zobrazí chyby při vytváření spustitelného souboru.  
  
## <a name="remarks"></a>Poznámky  
 Pokud je zadaný název souboru, který neexistuje, vytvoří se soubor automaticky. Pokud soubor již existuje, výsledky jsou připojena k existující obsah souboru.  
  
 Chyby sestavení příkazového řádku se zobrazují v **příkaz** okno a Tvůrce řešení zobrazení **výstup** okna. Tato možnost je užitečná, pokud jsou spuštěny bezobslužném sestavování a potřebujete pro zobrazení výsledků.  
  
## <a name="example"></a>Příklad  
 Tento příklad se spouští `MySolution` a zapíše chyby do souboru `MyErrorLog.txt`.  
  
```  
devenv /run "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /out "C:\MyErrorLog.txt"  
```  
  
## <a name="see-also"></a>Viz také  
 [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)   
 [Nebo spuštění (devenv.exe)](../../ide/reference/run-devenv-exe.md)   
 [/ Sestavení (devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/ Sestavení (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/ Nasazení (devenv.exe)](../../ide/reference/deploy-devenv-exe.md)
