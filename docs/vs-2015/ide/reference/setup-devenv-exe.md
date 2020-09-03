---
title: -Setup (devenv.exe) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- setup Devenv switch
- /setup Devenv switch
- Devenv, /setup switch
ms.assetid: 87608b7f-a156-400c-80f5-fc823f843e61
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: a923d1f3532548ebc6ed651a0739e0e5792f7967
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "72663538"
---
# <a name="setup-devenvexe"></a>/Setup (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vynutí [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] sloučení metadat prostředků, která popisují nabídky, panely nástrojů a skupiny příkazů, ze všech dostupných VSPackage.

## <a name="syntax"></a>Syntax

```
devenv /setup
```

## <a name="remarks"></a>Poznámky
 Tento přepínač nepřijímá žádné argumenty. `devenv /setup`Příkaz se obvykle předává jako poslední krok instalačního procesu. Použití přepínače se `/setup` nespustí [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] .

 `devenv`Aby bylo možné používat přepínače [/setup (devenv.exe)](../../ide/reference/setup-devenv-exe.md) a [/installvstemplates (devenv.exe)](../../ide/reference/installvstemplates-devenv-exe.md) , musíte spustit jako správce.

## <a name="example"></a>Příklad
 Tento příklad ukazuje poslední krok instalace verze nástroje [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] , která obsahuje sady VSPackage.

```
devenv /setup
```

## <a name="see-also"></a>Viz také
 [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)
