---
title: "Úlohy nástroje MSBuild specifické pro Visual C++ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords: MSBuild, tasks specific to Visual C++
ms.assetid: 05410f0c-7356-4692-bc00-20664421c9ff
caps.latest.revision: "7"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1e725bc94a159ea5295341021f60ee1183a8982e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="msbuild-tasks-specific-to-visual-c"></a>Úlohy nástroje MSBuild specifické pro Visual C++
Úlohy zadejte kód, který spouští během procesu sestavení. Při instalaci Visual C++ následující úlohy jsou k dispozici, kromě těch, které jsou nainstalované s [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. Další informace najdete v tématu [přehled nástroje MSBuild (Visual C++)](/cpp/build/msbuild-visual-cpp-overview).  
  
 Kromě parametrů pro každý úkol má každý úkol, také následující parametry.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`Condition`|Volitelné `String` parametr.<br /><br /> A `Boolean` výrazu, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] modul se používá k určení, zda tato úloha bude provádět. Informace o podmínkách, které jsou podporovány [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)], najdete v části [podmínky](../msbuild/msbuild-conditions.md).|  
|`ContinueOnError`|Volitelný parametr. Může obsahovat jednu z následujících hodnot:<br /><br /> -   **WarnAndContinue** nebo **true**. Pokud úloha selže, úlohy v [cíl](../msbuild/target-element-msbuild.md) elementu a sestavení dále provést, a všechny chyby z úlohy se považují za upozornění<br />-   **ErrorAndContinue**. Pokud úloha selže, úlohy v `Target` elementu a sestavení dále provést, a všechny chyby z úlohy se považují za chyby.<br />-   **ErrorAndStop** nebo **false** (výchozí). Pokud úloha selže, ve zbývajících úkolech v`Target` elementu a sestavení nebudou provedeny a celý `Target` elementu a sestavení jsou považovány za za neúspěšný.<br /><br /> Verze rozhraní .NET Framework před 4.5 podporovaná jenom `true` a `false` hodnoty.<br /><br /> Další informace najdete v tématu [postupy: ignorování chyb v úlohách](../msbuild/how-to-ignore-errors-in-tasks.md).|  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[BscMake – úloha](../msbuild/bscmake-task.md)|Zabalí nástroj Microsoft procházet údržby nástroje pro konfiguraci (bscmake.exe).|  
|[CL – úloha](../msbuild/cl-task.md)|Zabalí nástroj kompilátoru Visual C++ (cl.exe).|  
|[CPPClean – úloha](../msbuild/cppclean-task.md)|Odstraní dočasné soubory, které MSBuild vytvoří při sestavení projektu Visual C++.|  
|[LIB – úloha](../msbuild/lib-task.md)|Zabalí nástroj Microsoft 32bitový Správce knihovny (lib.exe).|  
|[Odkaz – úloha](../msbuild/link-task.md)|Zabalí nástroj linkeru jazyka Visual C++ (link.exe).|  
|[MIDL – úloha](../msbuild/midl-task.md)|Zabalí nástroj kompilátoru Microsoft rozhraní Definition Language (MIDL) (midl.exe).|  
|[MT – úloha](../msbuild/mt-task.md)|Zabalí nástroj Microsoft Manifest (mt.exe).|  
|[RC – úloha](../msbuild/rc-task.md)|Zabalí nástroj Microsoft kompilátor prostředků Windows (rc.exe).|  
|[SetEnv – úloha](../msbuild/setenv-task.md)|Nastaví nebo odstraní hodnotu proměnné zadaného prostředí.|  
|[VCMessage – úloha](../msbuild/vcmessage-task.md)|Protokoly upozornění a chybové zprávy během sestavení.|  
|[XDCMake – úloha](../msbuild/xdcmake-task.md)|Zabalí nástroj dokumentace XML (xdcmake.exe), která sloučí soubory komentář (projektový) dokumentu XML do souboru .xml.|  
|[XSD – úloha](../msbuild/xsd-task.md)|Zabalí nástroj definice schématu XML (xsd.exe), který generuje schématu nebo třída soubory ze zdroje.|  
|[Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)|Popisuje elementy MSBuild systému.|  
|[Úlohy](../msbuild/msbuild-tasks.md)|Popisuje úlohy, jako jsou jednotky kód, který mohou být kombinovány k vytvoření sestavení.|  
|[Zápis úloh](../msbuild/task-writing.md)|Popisuje postup vytvoření úlohy.|