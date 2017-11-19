---
title: "CA2228: Nedodávejte nevydané formáty prostředku | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DoNotShipUnreleasedResourceFormats
- CA2228
helpviewer_keywords:
- CA2228
- DoNotShipUnreleasedResourceFormats
ms.assetid: 2c614edc-4e94-4b4f-8067-eea677a75cd9
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 959d88751ff250e54f6a3f89f0b4b0554add96d1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca2228-do-not-ship-unreleased-resource-formats"></a>CA2228: Nedodávejte nevydané formáty prostředku
|||  
|-|-|  
|TypeName|DoNotShipUnreleasedResourceFormats|  
|CheckId|CA2228|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Zdrojového souboru byl vytvořený pomocí verze [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] , se aktuálně nepodporuje.  
  
## <a name="rule-description"></a>Popis pravidla  
 Soubory prostředků, které byly vytvořené pomocí předprodejní verze [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] nemusí být použitelná pro podporované verze rozhraní .NET Framework.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, vytvoření prostředku, který používá podporovanou verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]kB.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.