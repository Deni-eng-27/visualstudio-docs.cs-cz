---
title: Nastavení projektu VC ++, projekty a řešení, dialogové okno Možnosti | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Projects.VCBuild
helpviewer_keywords:
- builds [Visual Studio], logs
- build process [C++]
- files [Visual Studio], built by C/C++ compiler
- file extensions, built by C or C++ compiler
- cl.exe compiler, file extensions
- extensions, files built by C or C++ compiler
- BuildLog.htm
ms.assetid: 56420efd-6a95-464e-b890-e2b38c48d66a
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 66110f6544bc19476bb4ecdfd6929fb4e26f0b52
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60082431"
---
# <a name="vc-project-settings-projects-and-solutions-options-dialog-box"></a>Nastavení projektu VC++, projekty a řešení, dialogové okno Možnosti
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Toto dialogové okno umožňuje definovat [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] nastavení související s sestavení, protokolování a podpůrné typy souborů projektu.  
  
### <a name="to-access-this-dialog-box"></a>Pro přístup k tomuto dialogovému oknu  
  
1. Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.  
  
2. Vyberte **projekty a řešení**a pak vyberte **nastavení projektu VC ++**.  
  
## <a name="build-customization-search-path"></a>Cesty pro hledání vlastního nastavení sestavení  
 Určuje seznam adresářů, které obsahují .rules soubory, které vám pomůžou definovat pravidla sestavení pro vaše projekty.  
  
## <a name="build-logging"></a>Protokolování sestavení  
 **Ano**  
 Zapnutí generování souboru protokolu sestavení. Tato možnost vygeneruje BuildLog.htm, který se nachází v adresáři zprostředkujících souborů projektu. Každé nové sestavení přepíše předchozí soubor BuildLog.htm.  
  
 **Ne**  
 Vypne generování souboru protokolu sestavení.  
  
## <a name="build-timing"></a>Časování sestavení  
 **Ano**  
 Zapne časování sestavení. Pokud vybraná, čas potřebný pro na dokončení sestavení se zveřejní v okně výstupu. Další informace najdete v tématu [okno výstup](../../ide/reference/output-window.md).  
  
 **Ne**  
 Vypne časování sestavení.  
  
## <a name="extensions-to-hide"></a>Přípony ke skrytí  
 Určuje přípony názvů souborů, které se nezobrazí v **Průzkumníka řešení** při **zobrazit všechny soubory** je povolená.  
  
## <a name="extensions-to-include"></a>Rozšíření zahrnout  
 Určuje přípony názvů souborů, které můžete přenést do projektu.  
  
## <a name="maximum-concurrent-c-compilations"></a>Maximum souběžných kompilací C++  
 Určuje maximální počet Procesorových jader pro paralelní kompilaci jazyka C++.  
  
## <a name="show-environment-in-log"></a>Zobrazit prostředí v protokolu  
 **Ano**  
 Seznam proměnných prostředí v souboru protokolu sestavení. Tato možnost určuje vypisovat všech proměnných prostředí během sestavení [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] projekty, do souboru protokolu sestavení.  
  
 **Ne**  
 Proměnné prostředí vyloučíte ze souboru protokolu sestavení.  
  
## <a name="solution-explorer-mode"></a>Režim Průzkumník řešení  
 **Zobrazit pouze soubory v projektu**  
 Nakonfiguruje **Průzkumníka řešení** můžete zobrazit jenom soubory v projektu.  
  
 **Zobrazit všechny soubory**  
 Nakonfiguruje **Průzkumníka řešení** k zobrazení souborů v projektu a souborů na disku ve složce projektu.  
  
## <a name="see-also"></a>Viz také  
 [Sestavování programů jazyka C/C++](http://msdn.microsoft.com/library/fa6ed4ff-334a-4d99-b5e2-a1f83d2b3008)   
 [Referenční zdroje k sestavení programu v jazyce C/C++](http://msdn.microsoft.com/library/100b4ccf-572c-4d1f-970c-fa0bc0cc0d2d)
