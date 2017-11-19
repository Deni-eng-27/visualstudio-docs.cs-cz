---
title: "Elementy izolované prostředí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio shell, isolated mode
ms.assetid: f8d68c3d-9134-4a8f-b566-485956cd321e
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 32ca2aa4c3c37a4ff407ec06031ec8db16b54ea7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="elements-of-the-isolated-shell"></a>Elementy izolované prostředí
Můžete upravit nastavení registru, nastavení času spuštění a vstupní bod aplikace aplikace izolované prostředí a jeho .vsct, .pkgdef, and.pkgundef soubory.  
  
## <a name="registry-settings"></a>Nastavení registru  
 .pkgdef i soubory .pkgundef upravit nastavení registru pro izolované prostředí aplikace. Při spuštění aplikace, nastavení registru jsou definovány v tomto pořadí:  
  
 Při spuštění aplikace, nastavení registru jsou definovány v tomto pořadí:  
  
1.  Vytvoří se klíč registru pro aplikaci.  
  
2.  Ze souboru .pkgdef aplikace aktualizovat registr tak, že definujete zadaného klíče a položky.  
  
3.  Pro každý balíček, který je součástí aplikace je aktualizovat registr ze souboru .pkgdef tohoto balíčku. Každý balíček je definován v souboru .pkgdef aplikace $RootKey$ \Packages\\{*vsPackageGuid*} klíče pro balíček.  
  
4.  Registru je aktualizována z AppEnvConfig.pkgdef a BaseConfig.pkgdef v *cesta instalace Visual Studio SDK*\Common7\IDE\ShellExtensions\Platform adresáře. Tyto soubory jsou součástí sady Visual Studio a také součástí redistribuovatelný balíček Visual Studio Shell (izolovaný režim).  
  
5.  Registru je aktualizována z soubor .pkgundef aplikace odebráním zadaného klíče a položky.  
  
## <a name="run-time-settings"></a>Run-Time nastavení  
 Když uživatel spustí aplikaci, která izolované prostředí, zavolá vstupní bod spuštění z prostředí sady Visual Studio. Nastavení aplikace jsou definovány, když se aplikace spustí, následujícím způsobem:  
  
1.  Prostředí sady Visual Studio kontroluje aplikace registru pro konkrétní klíče. Pokud je nastavení pro klíč zadané v volání počáteční vstupní bod, tato hodnota přepíše hodnotu v registru.  
  
2.  Pokud registru ani položku bodu parametr určuje hodnotu nastavení a potom je použita výchozí hodnota pro nastavení.  
  
 Když uživatel spustí aplikaci z příkazového řádku, jsou předány prostředí sady Visual Studio, který pracuje s nimi stejným způsobem, který nemá Devenv všechny přepínače příkazového řádku. Další informace o přepínačích Devenv najdete v tématu [příkazového řádku DEVENV](../../ide/reference/devenv-command-line-switches.md) a [Devenv přepínače příkazového řádku pro vývoj VSPackage](../devenv-command-line-switches-for-vspackage-development.md). Další informace o tom, jak balíček zaregistruje spínačů příkazového řádku najdete v tématu [přidání přepínače příkazového řádku](../adding-command-line-switches.md).  
  
## <a name="the-start-entry-point"></a>Vstupní bod spuštění  
 Soubor Appenvstub.dll obsahuje vstupní body pro přístup k izolované prostředí. Při spuštění aplikace volá vstupní bod Appenvstub.dll Start.  
  
 Chování aplikace můžete změnit změnou hodnoty poslední parametr, který je předán do počáteční vstupní bod. Další informace najdete v tématu [izolované prostředí vstupní bod parametrů (C++)](isolated-shell-entry-point-parameters-cpp.md).  
  
## <a name="the-vsct-file"></a>Na. Soubor Vsct  
 Soubor .vsct umožňuje určit, které standardní prvky uživatelského rozhraní Visual Studio jsou k dispozici v aplikaci. Další informace najdete v tématu [. Soubory Vsct](modifying-the-isolated-shell-by-using-the-dot-vsct-file.md).  
  
## <a name="the-pkgundef-file"></a>Na. Soubor Pkgundef  
 Když je aplikace nainstalována na počítači, na kterém je již nainstalován Visual Studio, kopie položky registru Visual Studio se provádí pro aplikaci. Ve výchozím nastavení používá aplikace VSPackages, které jsou již nainstalovány v počítači. Soubor .pkgundef umožňuje vyloučit položky registru, aby bylo možné odebrat konkrétní prvky prostředí sady Visual Studio nebo rozšíření z aplikace. Další informace najdete v tématu [. Soubory Pkgundef](modifying-the-isolated-shell-by-using-the-dot-pkgundef-file.md).  
  
 Soubor .pkgundef umožňuje vyloučit položky registru, aby bylo možné odebrat konkrétní prvky prostředí sady Visual Studio nebo rozšíření z aplikace. Další informace najdete v tématu [. Soubory Pkgundef](modifying-the-isolated-shell-by-using-the-dot-pkgundef-file.md).  
  
 Sada balíček identifikátory GUID, které můžete vyloučit jsou uvedeny v [identifikátory GUID nástroje Visual Studio funkce balíčků](package-guids-of-visual-studio-features.md).  
  
## <a name="the-pkgdef-file"></a>Na. Soubor Pkgdef  
 Soubor .pkgdef umožňuje definovat položky registru pro aplikace, které jsou nastaveny při instalaci aplikace. Popis souboru .pkgdef a seznam položky registru, které používá prostředí sady Visual Studio najdete v tématu [. Soubory Pkgdef](modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md).  
  
## <a name="substitution-strings"></a>Náhradní řetězce  
 Náhradní řetězce používají v souborech .pkgdef a .pkgundef jsou uvedeny v [náhradní řetězce používány. Pkgdef a. Soubory Pkgundef](substitution-strings-used-in-dot-pkgdef-and-dot-pkgundef-files.md).  
  
## <a name="other-settings"></a>Další nastavení  
 Pokud aplikace izolované prostředí závisí na Microsoft.VisualStudio.GraphModel.dll, budete muset přidat následující přesměrování vazby do souboru .config aplikace izolované prostředí:  
  
```  
<dependentAssembly>  
    <assemblyIdentity name="Microsoft.VisualStudio.GraphModel" publicKeyToken="b03f5f7f11d50a3a" culture="neutral" />  
    <bindingRedirect oldVersion="11.0.0.0" newVersion="12.0.0.0"/>  
</dependentAssembly>  
  
```