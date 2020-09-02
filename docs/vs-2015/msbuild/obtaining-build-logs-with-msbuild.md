---
title: Získání protokolů sestavení pomocí nástroje MSBuild | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, logging
- logging [MSBuild]
ms.assetid: 6ba9a754-9cc0-4fed-9fc8-4dcd3926a031
caps.latest.revision: 30
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c88288a7bed453ca14e9c14fd43706b97be04044
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "64789471"
---
# <a name="obtaining-build-logs-with-msbuild"></a>Získávání protokolů o sestavení pomocí nástroje MSBuild
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pomocí přepínačů s nástrojem MSBuild můžete určit, kolik dat sestavení chcete zkontrolovat a zda chcete uložit data sestavení do jednoho nebo více souborů. Můžete také zadat vlastní protokolovací nástroj pro shromažďování dat buildu. Informace o přepínačích příkazového řádku MSBuild, které toto téma popisuje, najdete v tématu [Reference k příkazovému řádku](../msbuild/msbuild-command-line-reference.md).  
  
> [!NOTE]
> Pokud vytváříte projekty pomocí integrovaného vývojového prostředí (IDE) sady Visual Studio, můžete tyto sestavení řešit pomocí kontroly protokolů sestavení. Další informace najdete v tématu [Postup: zobrazení, uložení a konfigurace souborů protokolu sestavení](../ide/how-to-view-save-and-configure-build-log-files.md).  
  
## <a name="setting-the-level-of-detail"></a>Nastavení úrovně podrobností  
 Při sestavování projektu pomocí nástroje MSBuild bez zadání úrovně podrobností se v protokolu výstupu zobrazí následující informace:  
  
- Chyby, varování a zprávy, které jsou zařazeny do kategorie jako vysoce důležité.  
  
- Některé události stavu.  
  
- Souhrn sestavení.  
  
  Pomocí přepínače **/Verbosity** (**/v**) můžete určit, kolik dat se zobrazí ve výstupním protokolu. Pro řešení potíží použijte úroveň podrobností pro `detailed` ( `d` ) nebo `diagnostic` ( `diag` ), která poskytuje nejvíc informací.  
  
  Proces sestavení může být pomalejší, pokud nastavíte **/Verbosity** na `detailed` a ještě pomalejší, pokud nastavíte **/Verbosity** na `diagnostic` .  
  
```  
msbuild MyProject.proj /t:go /v:diag  
```  
  
## <a name="saving-the-build-log-to-a-file"></a>Uložení protokolu sestavení do souboru  
 Pomocí přepínače **/FileLogger** (**FL**) můžete ukládat data sestavení do souboru. Následující příklad uloží data sestavení do souboru s názvem `msbuild.log` .  
  
```  
msbuild MyProject.proj /t:go /fileLogger  
```  
  
 V následujícím příkladu je soubor protokolu pojmenován `MyProjectOutput.log` a podrobnosti výstupu protokolu jsou nastaveny na `diagnostic` . Tato dvě nastavení zadáte pomocí přepínače **/filelogparameters** ( `flp` ).  
  
```  
msbuild MyProject.proj /t:go /fl /flp:logfile=MyProjectOutput.log;verbosity=diagnostic  
```  
  
 Další informace najdete v tématu [Reference k příkazovému řádku](../msbuild/msbuild-command-line-reference.md).  
  
## <a name="saving-the-log-output-to-multiple-files"></a>Uložení výstupu protokolování do více souborů  
 Následující příklad uloží celý protokol do `msbuild1.log` , pouze chyby do a `JustErrors.log` pouze upozornění na `JustWarnings.log` . Příklad používá čísla souborů pro každý ze tří souborů. Čísla souborů jsou uvedena hned za přepínači **/FL** a **/FLP** (například `/fl1` a `/flp1` ).  
  
 Přepínače **/filelogparameters** ( `flp` ) pro soubory 2 a 3 určují, co má každý soubor pojmenovat a co se má zahrnout do každého souboru. Pro soubor 1 není zadán žádný název, proto je použit výchozí název `msbuild1.log` .  
  
```  
msbuild MyProject.proj /t:go /fl1 /fl2 /fl3 /flp2:logfile=JustErrors.log;errorsonly /flp3:logfile=JustWarnings.log;warningsonly  
  
```  
  
 Další informace najdete v tématu [Reference k příkazovému řádku](../msbuild/msbuild-command-line-reference.md).  
  
## <a name="using-a-custom-logger"></a>Používání vlastního protokolovacího nástroje  
 Vlastní protokolovací nástroj můžete napsat vytvářením spravovaného typu, který implementuje <xref:Microsoft.Build.Framework.ILogger> rozhraní. Pomocí vlastního protokolovacího nástroje můžete například odesílat chyby sestavení v e-mailu, přihlašovat je do databáze nebo do souboru XML. Další informace najdete v tématu [protokolovací nástroje sestavení](../msbuild/build-loggers.md).  
  
 V příkazovém řádku MSBuild zadáte vlastní protokolovací nástroj pomocí přepínače **/Logger** . Pomocí přepínače **/noconsolelogger** můžete také zakázat výchozí protokolovací nástroj konzoly.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.Build.Framework.LoggerVerbosity>   
 [Protokolovací nástroje sestavení](../msbuild/build-loggers.md)   
 [Protokolování v prostředí s více procesory](../msbuild/logging-in-a-multi-processor-environment.md)   
 [Vytváření protokolovacích nástrojů pro předávání](../msbuild/creating-forwarding-loggers.md)   
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)
