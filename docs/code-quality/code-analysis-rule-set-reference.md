---
title: "Referenční dokumentace sady pravidel nástroje Analýza kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: code analysis, rule sets
ms.assetid: 5874e854-e298-4d2e-bbe4-95e899d22587
caps.latest.revision: "43"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f396bb289e7e4288dbb80c6e08990960861e970c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="code-analysis-rule-set-reference"></a>Referenční dokumentace sady pravidel nástroje Analýza kódu
Když konfigurujete analýzy kódu pro spravovaný kód projekty v [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], nebo [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]zobrazí se seznam integrovaných *sad pravidel*. Můžete použít standardní pravidla sad, nebo můžete přizpůsobit podle svých požadavků projektu sadu pravidel.  
  
## <a name="available-rule-sets"></a>Sad pravidel k dispozici  
 V následující tabulce jsou uvedeny výchozí sady pravidel:  
  
|||  
|-|-|  
|[Sada pravidel Všechna pravidla](../code-quality/all-rules-rule-set.md)|Této sady pravidel obsahuje všechna pravidla. Spuštění této sady pravidel, může mít za následek velký počet upozornění nehlásí. Pomocí tohoto pravidla nastavit získat ucelený přehled o všech problémech ve vašem kódu. Můžete rozhodnout, které přesněji zaměřené pravidlo sady jsou nejvhodnější pro projekty.|  
|[Sada pravidel Základní pravidla správnosti pro spravovaný kód](../code-quality/basic-correctness-rules-rule-set-for-managed-code.md)|Tato pravidla se zaměřit na logických a běžných chyb provedené v používání prostředí rozhraní API. Toto pravidlo nastavit rozšíření seznam upozornění hlášené Minimální doporučená pravidla zahrnutí.|  
|[Sada pravidel Základní pravidla obecných zásad návrhu pro spravovaný kód](../code-quality/basic-design-guideline-rules-rule-set-for-managed-code.md)|Tato pravidla se zaměřit na vynucování osvědčené postupy s cílem zajistit, aby váš kód snadno pochopit a používat. Toto pravidlo nastavte, pokud projekt obsahuje kód knihovny, nebo pokud chcete vynutit osvědčené postupy pro snadno udržovatelného kódu zahrnutí.|  
|[Sada pravidel Rozšířená pravidla správnosti pro spravovaný kód](../code-quality/extended-correctness-rules-rule-set-for-managed-code.md)|Tato pravidla rozbalte v pravidlech základní správnost chcete maximalizovat využití chyby logiku a framework, které jsou hlášeny. Navíc je důraz na konkrétní scénáře, jako jsou například COM spolupráce a mobilní aplikace. Zvažte, včetně toto pravidlo nastavit, pokud jeden z těchto scénářů vztahuje na projektu nebo k nalezení dalších problémů ve vašem projektu.|  
|[Sada pravidel Rozšířená pravidla pokynů návrhu pro spravovaný kód](../code-quality/extended-design-guidelines-rules-rule-set-for-managed-code.md)|Tato pravidla rozbalit na pravidla obecných zásad návrhu základní maximalizovat použitelnost a jeho udržovatelnost problémy, které jsou hlášeny. Navíc je důraz na pokyny pro pojmenování. Zvažte, včetně toto pravidlo nastavte, pokud projekt obsahuje kód knihovny, nebo pokud chcete vynutit nejvyšší standardy pro zápis udržovatelného kódu.|  
|[Sada pravidel Pravidla globalizace pro spravovaný kód](../code-quality/globalization-rules-rule-set-for-managed-code.md)|Tato pravidla se zaměřit na problémy, které zabraňují dat v aplikaci zobrazit správně při použití v různých jazycích, národní prostředí a kultur. Toto pravidlo nastavit, pokud vaše aplikace je lokalizované nebo globalizovaná zahrnutí.|  
|[Pro spravovaný kód sada pravidel spravovaná minimální pravidla](../code-quality/managed-minimun-rules-rule-set-for-managed-code.md)|Tato pravidla se zaměřit na nejdůležitější problémy ve vašem kódu, pro kterou je nejpřesnější analýza kódu.  Tato pravidla jsou malý počet a jsou určeny pouze pro spouštění v omezené edice sady Visual Studio.  MinimumRecommendedRules.ruleset pomocí jiných edicích sady Visual Studio.|  
|[Sada pravidel Spravovaná doporučená pravidla pro spravovaný kód](../code-quality/managed-recommended-rules-rule-set-for-managed-code.md)|Tato pravidla se zaměřit na nejdůležitější problémy ve vašem kódu, včetně potenciální bezpečnostní díry, dojde k chybě aplikace a další důležité chyby logiku a návrhu. Toto pravidlo nastavit v žádné sadě vlastní pravidlo, že které vytvoříte pro projekty by měla obsahovat.|  
|[Sada pravidel Smíšená minimální pravidla](../code-quality/mixed-minimum-rules-rule-set.md)|Tato pravidla se zaměřit na nejdůležitější problémy ve vašich projektů C++, které podporují modul Common Language Runtime, včetně potenciální bezpečnostní díry a dojde k chybě aplikace. Toto pravidlo nastavit v žádné sadě vlastní pravidlo, že které vytvoříte pro projekty jazyka C++, které podporují modul Common Language Runtime by měla obsahovat.|  
|[Sada pravidel Smíšená doporučená pravidla](../code-quality/mixed-recommended-rules-rule-set.md)|Tato pravidla se zaměřit na nejčastějších a důležité problémy ve vašich projektů C++, které podporují modul Common Language Runtime, včetně potenciální bezpečnostní díry, dojde k chybě aplikace a další důležité chyby logiku a návrhu. Toto pravidlo nastavit v žádné sadě vlastní pravidlo, že které vytvoříte pro projekty jazyka C++, které podporují modul Common Language Runtime by měla obsahovat.  Tato sada pravidel pro je navržena ke konfiguraci s Visual Studio Professional edition a vyšší.|  
|[Sada pravidel Nativní minimální pravidla](../code-quality/native-minimum-rules-rule-set.md)|Tato pravidla se soustředí na nejdůležitější problémy v nativním kódu, včetně možných bezpečnostních děr a selhání aplikace. Toto pravidlo nastavit v žádné sadě vlastní pravidlo, že které vytvoříte pro nativní projekty by měla obsahovat.|  
|[Sada pravidel Nativní doporučená pravidla](../code-quality/native-recommended-rules-rule-set.md)|Tato pravidla se zaměřit na nejvíce kritické a běžné problémy v nativním kódu, včetně potenciální bezpečnostní díry a dojde k chybě aplikace.  Toto pravidlo nastavit v žádné sadě vlastní pravidlo, že které vytvoříte pro nativní projekty by měla obsahovat.  Tato sada pravidel pro je navržen pro práci s Visual Studio Professional edition a vyšší.|  
|[Sada pravidel Pravidla zabezpečení pro spravovaný kód](../code-quality/security-rules-rule-set-for-managed-code.md)|Této sady pravidel obsahuje všechna pravidla zabezpečení společnosti Microsoft. Toto pravidlo nastavte co nejvíce možné problémy zabezpečení, které jsou hlášeny zahrnutí.|
