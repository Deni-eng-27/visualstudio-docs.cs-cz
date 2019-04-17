---
title: -Upravit (devenv.exe) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /edit switch
- /Edit Devenv swtich
ms.assetid: 02b3d6e7-a2b1-4d83-a747-aa8c2fb758b7
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: c4dabbb0c21fd6b4cabb01655485c8158662adb2
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59667272"
---
# <a name="edit-devenvexe"></a>/Edit (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Zadaný soubor se otevře v existující instanci [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Devenv /edit [file1[ file2]]  
```  
  
## <a name="arguments"></a>Arguments  
 `file1`  
 Volitelné. Soubor otevřete v existující instanci [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Pokud žádná instance [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] existuje, se zjednodušeným rozložením okna, je vytvořena nová instance a `file1` se otevře v nové instanci.  
  
 `file2`  
 Volitelné. Nejméně jeden další soubor otevřete v existující instanci systému [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
## <a name="remarks"></a>Poznámky  
 Pokud není určen žádný soubor, a existující instanci [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], existující instanci [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] získá fokus. Pokud není určen žádný soubor a neexistuje žádná existující instance [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], novou instanci třídy [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] vytvoření se zjednodušeným rozložením okna.  
  
 Pokud existující instanci systému [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] je v modálního stavu, například, pokud [dialogové okno Možnosti](../../ide/reference/options-dialog-box-visual-studio.md) je otevřete, bude soubor otevřít v existující instanci, kdy [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ukončí modální stav.  
  
## <a name="example"></a>Příklad  
 Tento příklad otevře soubor `MyFile.cs` v existující instanci [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] nebo otevře soubor v nové instanci [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Pokud ještě neexistuje.  
  
```  
devenv /edit MyFile.cs  
```  
  
## <a name="see-also"></a>Viz také  
 [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)
