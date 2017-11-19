---
title: "Řešení potíží s rozšířeními pro diagramy závislostí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dependency diagrams, extension errors
- dependency diagrams, troubleshooting extensions
ms.assetid: 1fda4f8a-38b8-482b-87b8-eade1a4e5662
caps.latest.revision: "25"
author: alexhomer1
ms.author: ahomer
manager: douge
ms.openlocfilehash: fae53e45b231292df8b7a6ae8bf4f2babc5d9e88
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="troubleshoot-extensions-for-dependency-diagrams"></a>Řešení potíží s rozšířeními pro diagramy závislostí
Toto téma nabízí některé problémy, které se můžete setkat při vytváření vrstvy rozšířeních modelu.  
  
#### <a name="when-i-press-f5-to-debug-my-extension-my-commands-gesture-handlers-validation-extensions-or-custom-properties-do-not-appear-on-dependency-diagrams-in-the-experimental-instance-of-includevsprvscode-qualityincludesvsprvsmdmd"></a>Po stisknutí klávesy F5 k ladění Moje rozšíření, příkazy, obslužné rutiny gesto, ověření rozšíření nebo vlastní vlastnosti se nezobrazí v diagramech závislostí v experimentální instanci[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]  
  
1.  Otevřete řešení rozšíření v experimentální instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]a na **sestavení** nabídky, klikněte na tlačítko **znovu sestavit řešení**.  
  
2.  Stiskněte klávesu **F5** nebo **CTRL + F5** zahájíte experimentální instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Otevřít diagram závislostí a testování rozšíření.  
  
 V případě potřeby, pokračujte v dalším postupu.  
  
#### <a name="an-old-version-of-my-extension-runs"></a>Starší verzi rozšíření my spustí.  
  
1.  Ujistěte se, že není žádná instance experimentální [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] běží.  
  
2.  Odstraňte následující složku: %LocalAppData%\Microsoft\VisualStudio\\\ComponentModelCache [verze]  
  
    > [!NOTE]
    >  % LocalAppData % je obvykle *DriveName*: \Users\\*uživatelské jméno*\AppData\Local.  
  
 V případě potřeby, pokračujte v dalším postupu.  
  
#### <a name="an-old-version-of-my-validation-results-appears-or-my-validation-method-is-not-called"></a>Stará verze architektury Moje výsledky ověření se zobrazí, nebo Moje ověření metoda není volána.  
  
1.  V experimentální instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]na **sestavení** nabídky, klikněte na tlačítko **Vyčistit řešení**. Zruší výsledky uložené v mezipaměti předchozí analýzy ověření.  
  
2.  Ujistěte se, že vrstvy v modelu jsou spojeny s elementy kódu a že je alespoň jeden odkaz závislostí v modelu. Ověření není vyvolána, pokud není nic k ověření.  
  
3.  Regulární zarážky nemusí fungovat v metodu ověření, protože běží jako samostatný proces. Je třeba vložit volání `System.Diagnostics.Debugger.Launch()` Pokud chcete procházet metodu.  
  
4.  V **source.extension.vsixmanifest** ve vašem projektu ověření vrstvy, ujistěte se, přidali i **Komponenta MEF** položky a **vlastní typ rozšíření** položku **Obsahu**.  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření diagramů závislostí](../modeling/extend-layer-diagrams.md)
