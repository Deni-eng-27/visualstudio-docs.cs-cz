---
title: 'Postupy: Nastavení možností názvu datového souboru výkonu | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: d7a8d6b9-ab23-46fb-98ed-774781157860
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: faaa78d34c71d1f0b436b861ccb1ac4892267e9b
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60057833"
---
# <a name="how-to-set-performance-data-file-name-options"></a>Postupy: Nastavení možností názvu souboru dat výkonu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Ve výchozím nastavení uložte souboru dat profilování (.vsp) pomocí následující syntaxe:  
  
 *Path\VSP-File\YYMMDD(N)* **.vsp**  
  
 Pro relace výkonu můžete změnit libovolný pojmenování parametru na kartě Obecné v dialogovém okně Vlastnosti.  
  
 **Požadavky**  
  
- [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
|||  
|-|-|  
|*Cesta*|Adresář, který obsahuje sestavu. Výchozí umístění je složka řešení nebo výchozí umístění pro projekty a řešení pro daného uživatele.|  
|*VSP-File*|Název souboru dat profilování. Výchozí název je název řešení nebo spustitelného souboru, která je profilována.|  
|*YYMMDD*|Časové razítko, který ukazuje, rok, měsíc a den, shromážděná data profilace.|  
|*(N)*|Pokud existuje více než jeden soubor dat profilování se zvyšující číslo přidá k názvu souboru mezi závorky.|  
  
### <a name="to-change-the-naming-syntax-of-the-profiling-data-files-of-a-performance-session"></a>Chcete-li změnit pojmenování syntaxe datových souborů profilace relace výkonu  
  
1. V **prohlížeč výkonu**, klikněte pravým tlačítkem na název relace výkonu a potom klikněte na **vlastnosti**.  
  
2. Klikněte na tlačítko **Obecné**.  
  
3. V části **sestavy**, změnit následující nastavení:  
  
    |||  
    |-|-|  
    |**Umístění sestavy**|Zadejte adresář pro uložení souborů dat profilování.|  
    |**Název sestavy**|Zadejte základní název pro soubory.|  
    |**Automaticky přidávat nové zprávy do relace**|Zaškrtněte políčko k automatickému přidávání datového souboru do relace výkonu.|  
    |**Přidat zvětšující se číslo do vygenerovaných sestav**|Zaškrtněte políčko Přidat zvětšující se číslo k názvu souboru, pokud existuje více než jeden soubor se stejným názvem. Zrušte zaškrtnutí políčka pro přepis existujícího souboru.|  
    |**Použít časové razítko pro číslo**|Zaškrtněte políčko pro přidání datestamp k názvu souboru.|
