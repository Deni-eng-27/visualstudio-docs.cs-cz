---
title: "Nápověda správce obsahu přepsání | Microsoft Docs"
ms.custom: 
ms.date: 11/01/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-help-viewer
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95fe6396-276b-4ee5-b03d-faacec42765f
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 35bc6ae23fdbc89f6bdeaa57bd37d5d961d87286
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="help-content-manager-overrides"></a>Přepsání voleb aplikace Help Content Manager
Můžete změnit výchozí chování Prohlížeč nápovědy a souvisejících s funkcí v prostředí Visual Studio IDE. Některé možnosti jsou určené vytváření [.pkgdef](https://blogs.msdn.microsoft.com/visualstudio/2009/12/18/whats-a-pkgdef-and-why/) souboru nastavit různé hodnoty klíčů registru. Ostatní se nastavují přímo v registru.

## <a name="how-to-control-help-viewer-behavior-by-using-a-pkgdef-file"></a>Tom, jak řídit pomocí souboru .pkgdef chování Help Viewer

1. Vytvořte soubor .pkgdef první řádek jako `[$RootKey$\Help]`.

2. Přidat některé nebo všechny hodnoty klíče registru popsané v následující tabulce na samostatné řádky, například `“UseOnlineHelp”=dword:00000001`.

3. Zkopírujte soubor do % ProgramFiles (x86) %\Microsoft Visual Studio\2017\\< edice\>\Common7\IDE\CommonExtensions.

4. Spustit `devenv /updateconfiguration` v příkazovém řádku vývojáře.

### <a name="registry-key-values"></a>Hodnoty klíčů registru
|Hodnota klíče registru|Typ|Data|Popis|  
|------------------|----|----|-----------|  
|NewContentAndUpdateService|odkazy řetězců|\<Adresa URL protokolu HTTP pro koncový bod služby\>|Definovat koncový bod jedinečné služby|
|UseOnlineHelp|DWORD|`0`Chcete-li určit místní Nápověda `1` k určení online nápovědy|Definujte výchozího nápovědy online nebo offline.|
|OnlineBaseUrl|odkazy řetězců|\<Adresa URL protokolu HTTP pro koncový bod služby\>|Definovat koncový bod jedinečný F1|
|OnlineHelpPreferenceDisabled|DWORD|`0`Chcete-li povolit nebo `1` zakázat možnost předvoleb online nápovědy|Zakázat možnost předvoleb online nápovědy|
|DisableManageContent|DWORD|`0`Chcete-li povolit nebo `1` zakázat **spravovat obsah** ve Help Viewer|Zakažte na kartě Správa obsahu|
|DisableFirstRunHelpSelection|DWORD|`0`Chcete-li povolit nebo `1` zakázání funkce nápovědy, které jsou nakonfigurované při prvním spuštění sady Visual Studio|Zakázat instalace obsahu na první spuštění sady Visual Studio|

### <a name="example-pkgdef-file-contents"></a>Obsah souboru .pkgdef příklad
```
[$RootKey$\Help]
“NewContentAndUpdateService”=”https://some.service.endpoint”
“UseOnlineHelp”=dword:00000001
“OnlineBaseUrl”=”https://some.service.endpoint”
“OnlineHelpPreferenceDisabled”=dword:00000000
“DisableManageContent”=dword:00000000
“DisableFirstRunHelpSelection”=dword:00000001
```

## <a name="using-registry-editor-to-change-help-viewer-behavior"></a>Pomocí Editoru registru změnit chování Help Viewer
Následující dva chování lze řídit nastavením hodnoty klíčů registru v editoru registru.  
  
|Úloha|Klíč registru|Hodnota|Data|  
|----------|-----|------|----|
|Přepsání priority úloh služby BITS|HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node (na 64-bit machine)\Microsoft\Help\v2.3|BITSPriority|**popředí**, **vysokou**, **normální**, nebo **nízkou**|
|Přejděte na místní ukládání obsahu ve sdílené síťové složce|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Help\v2.3\Catalogs\VisualStudio15|LocationPath|"*ContentStoreNetworkShare*"|
  
## <a name="see-also"></a>Viz také
[Příručka správce Help Vieweru](../ide/help-viewer-administrator-guide.md)  
[Argumenty příkazového řádku pro Help Content Manager](../ide/command-line-arguments-for-the-help-content-manager.md)  
[Microsoft Help Viewer 2.2](../ide/microsoft-help-viewer.md)  
[Úprava izolované prostředí pomocí souboru .pkgdef](../extensibility/shell/modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md)