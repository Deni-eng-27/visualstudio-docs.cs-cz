---
title: -Resetsettings – (devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Devenv, /ResetSettings switch
- ResetSettings switch
- /ResetSettings Devenv switch
ms.assetid: 1d41021c-6f58-4bd5-b122-d1c995812192
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 22dd925755e996a927664e0a9a5846fc10247882
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="resetsettings-devenvexe"></a>/ResetSettings (devenv.exe)
Obnoví [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] výchozí nastavení a automaticky spouští [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE. Volitelně obnoví nastavení na soubor zadaný .vssettings.  
  
 Určuje výchozí nastavení profilu, který byl vybrán při [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] byl nejprve spustit.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Devenv /ResetSettings SettingsFile  
```  
  
## <a name="arguments"></a>Arguments  
 `SettingsFile`  
 Úplná cesta a název souboru .vssettings použít [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 Chcete-li obnovit profil obecná nastavení pro vývoj, použijte `General`.  
  
## <a name="remarks"></a>Poznámky  
 Pokud žádné `SettingsFile` je zadán, zobrazí se výzva k výběru kolekce výchozí nastavení při dalším spuštění [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="example"></a>Příklad  
 Následující příkazový řádek aplikuje nastavení uložené v souboru `MySettings.vssettings`.  
  
```  
Devenv.exe /ResetSettings "C:\My Files\MySettings.vssettings"  
```  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení sady Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md)   
 [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)