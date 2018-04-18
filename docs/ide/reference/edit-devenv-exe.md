---
title: -Upravit (devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Devenv, /edit switch
- /Edit Devenv swtich
ms.assetid: 02b3d6e7-a2b1-4d83-a747-aa8c2fb758b7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 47db943d60abc23447aa579e85377a00cf551cae
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="edit-devenvexe"></a>/Edit (devenv.exe)
Zadaný soubor se otevře v existující instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Devenv /edit [file1[ file2]]  
```  
  
## <a name="arguments"></a>Arguments  
 `file1`  
 Volitelné. Soubor otevřete v existující instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Pokud není žádná instance [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] existuje, zjednodušené okno rozložení a je vytvořena nová instance a `file1` je otevřen v nové instance.  
  
 `file2`  
 Volitelné. Jeden nebo více dalších souborů, otevřete v existující instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="remarks"></a>Poznámky  
 Pokud není zadán žádný soubor a je existující instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], existující instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] obdrží fokus. Pokud není zadán žádný soubor a neexistuje žádná existující instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], novou instanci třídy [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] je vytvořena s rozložení zjednodušené okna.  
  
 Pokud existující instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] je v modální stavu, například, pokud [dialogové okno Možnosti](../../ide/reference/options-dialog-box-visual-studio.md) otevřete, bude soubor otevřete v existující instanci, kdy [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ukončí modální stavu.  
  
## <a name="example"></a>Příklad  
 Tento příklad otevře soubor `MyFile.cs` v existující instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] nebo soubor se otevře v nové instanci [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Pokud ještě neexistuje.  
  
```  
devenv /edit MyFile.cs  
```  
  
## <a name="see-also"></a>Viz také  
 [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)