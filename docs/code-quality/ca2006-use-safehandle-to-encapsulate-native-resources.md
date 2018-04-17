---
title: 'CA2006: Použijte SafeHandle pro zapouzdření nativních prostředků | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2006
- UseSafeHandleToEncapsulateNativeResources
helpviewer_keywords:
- UseSafeHandleToEncapsulateNativeResources
- CA2006
ms.assetid: a71950bd-bcc1-463d-b1f2-5233bc451456
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 0fdef78fdad92eb08012a474afff5c4c8c4d7ab8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca2006-use-safehandle-to-encapsulate-native-resources"></a>CA2006: Použijte SafeHandle pro zapouzdření nativních prostředků
|||  
|-|-|  
|TypeName|UseSafeHandleToEncapsulateNativeResources|  
|CheckId|CA2006|  
|Kategorie|Microsoft.Reliability|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Spravovaný kód používá <xref:System.IntPtr> přístupu k prostředkům, nativní.  
  
## <a name="rule-description"></a>Popis pravidla  
 Použití `IntPtr` ve spravovaném kódu může znamenat potenciální problém zabezpečení a spolehlivost. Všechna použití `IntPtr` musí být zkontrolovány k určení zda použití <xref:System.Runtime.InteropServices.SafeHandle> , nebo podobné technologie, je potřeba na příslušné místo. Pokud dojde k problémům `IntPtr` představuje některé nativní prostředků, například paměť, popisovače souboru nebo soketu a že spravovaný kód se považuje za vlastní. Pokud spravovaný kód vlastní prostředek, ho musí také uvolnit nativní prostředky přidružené k, protože způsobí selhání Uděláte to tak úniku prostředků.  
  
 V takových případech problémům se zabezpečením nebo spolehlivost bude také existovat, pokud je povolen vícevláknové přístup k `IntPtr` a způsob uvolnění prostředků, která je reprezentována `IntPtr` je k dispozici. Tyto problémy zahrnují recyklace `IntPtr` hodnota na uvolnění prostředků při souběžné používání prostředku se provádí na jiné vlákno. To může způsobit konflikty časování kde jedno vlákno můžou číst nebo zapisovat data, který je přidružen nesprávný prostředků. Pokud váš typ uloží popisovač operačního systému, jako například `IntPtr` a umožňuje uživatelům volání obě **Zavřít** a kterákoli metoda, která používá tento popisovač současně a bez nějaký druh synchronizace, kódu má popisovač recyklace došlo k potížím.  
  
 Tento popisovač recyklace problém může způsobit poškození dat a často, ohrožení zabezpečení. `SafeHandle` a třída jeho na stejné úrovni <xref:System.Runtime.InteropServices.CriticalHandle> poskytují mechanismus pro zapouzdření nativních popisovač pro prostředek tak, aby se takovým problémům vláken vyhnout. Kromě toho můžete použít `SafeHandle` a její na stejné úrovni jako třída `CriticalHandle` pro další vláken problémy, například k pečlivě řízení životnost spravovaných objektů, které obsahují kopii nativní popisovač prostřednictvím volání do nativního metod. V takovém případě můžete často eliminovat volání `GC.KeepAlive`. Režijní získána výkonu dojít při použití `SafeHandle` a v menší míře `CriticalHandle`, lze omezit často pečlivě návrhu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Převést `IntPtr` využití pro `SafeHandle` pro bezpečnou správu přístupu k prostředkům nativní. Najdete v článku <xref:System.Runtime.InteropServices.SafeHandle> referenční téma pro příklady.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Toto upozornění nesmí potlačit.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.IDisposable>