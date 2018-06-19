---
title: Referenční dokumentace úlohy nástroje MSBuild grafického subsystému WPF | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- WPF MSBuild task reference [WPF MSBuild], term/definition table
- build tasks [WPF MSBuild], Microsoft build engine
- build tasks using the Microsoft build engine [WPF MSBuild], compile markup and process resources
- WPF MSBuild task reference [WPF MSBuild]
ms.assetid: 96df0370-e50f-4ffc-9771-b12fb8721143
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 30acdaddc132a40c37bc489b07ae3b7f2843b215
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31573135"
---
# <a name="wpf-msbuild-task-reference"></a>WPF MSBuild – referenční dokumentace úlohy
Proces sestavení Windows Presentation Foundation (WPF) rozšiřuje stroje Microsoft build engine (MSBuild) o další sadu sestavení úlohy, včetně úlohy kompilace kódu a zdroje procesu.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [FileClassifier](../msbuild/fileclassifier-task.md)  
 Klasifikuje sadu zdroje prostředků jako ty, které budou vloženy do sestavení. Pokud prostředek není lokalizovatelný, se vloží do hlavní aplikace sestavení; jinak je integrovaný do satelitní sestavení.  
  
 [GenerateTemporaryTargetAssembly](../msbuild/generatetemporarytargetassembly-task.md)  
 Generuje sestavení, pokud alespoň jeden [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] stránky v projektu odkazuje na typ, který je deklarován místně v tomto projektu. Po dokončení procesu sestavení, nebo pokud proces sestavení selže, odeberou se vygenerované sestavení.  
  
 [GetWinFXPath](../msbuild/getwinfxpath-task.md)  
 Vrátí adresáře aktuální [!INCLUDE[TLA#tla_winfx](../msbuild/includes/tlasharptla_winfx_md.md)] modulu runtime.  
  
 [MarkupCompilePass1](../msbuild/markupcompilepass1-task.md)  
 Převede nepřekládá [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] soubory do kompilovaného binárního formátu projektu.  
  
 [MarkupCompilePass2](../msbuild/markupcompilepass2-task.md)  
 Provádí značek druhého průchodu kompilace [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] soubory, které odkazují na typy ve stejném projektu.  
  
 [Mergelocalizationdirectives –](../msbuild/mergelocalizationdirectives-task.md)  
 Sloučí atributů lokalizace a komentáře jednoho nebo více [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] binární formát souborů do jediného souboru pro celou sestavení.  
  
 [ResourcesGenerator](../msbuild/resourcesgenerator-task.md)  
 Vloží jednu nebo více prostředků (.ico, který JPG, BMP, [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] v binárním formátu a jinými typy rozšíření) do souboru .resources.  
  
 [Uidmanager –](../msbuild/uidmanager-task.md)  
 Kontroluje, aktualizuje nebo odebere jedinečné identifikátory (UID), aby bylo možné lokalizovat všechny [!INCLUDE[TLA#tla_xaml](../msbuild/includes/tlasharptla_xaml_md.md)] elementy, které jsou zahrnuté ve zdroji [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] soubory.  
  
 [UpdateManifestForBrowserApplication](../msbuild/updatemanifestforbrowserapplication-task.md)  
 Přidá  **\<hostinbrowser – / >** element manifest aplikace (*projectname*. exe.manifest) při [!INCLUDE[TLA#tla_xbap](../msbuild/includes/tlasharptla_xbap_md.md)] sestavení projektu.  
  
## <a name="see-also"></a>Viz také  
 [MSBuild](../msbuild/msbuild.md)