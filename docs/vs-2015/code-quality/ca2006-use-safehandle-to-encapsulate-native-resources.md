---
title: 'CA2006: použijte SafeHandle pro zapouzdření nativních prostředků | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2006
- UseSafeHandleToEncapsulateNativeResources
helpviewer_keywords:
- UseSafeHandleToEncapsulateNativeResources
- CA2006
ms.assetid: a71950bd-bcc1-463d-b1f2-5233bc451456
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 394fafb0c9185a5e11ba759a5b873236956cf25b
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72652214"
---
# <a name="ca2006-use-safehandle-to-encapsulate-native-resources"></a>CA2006: Použijte SafeHandle pro zapouzdření nativních prostředků
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|UseSafeHandleToEncapsulateNativeResources|
|CheckId|CA2006|
|Kategorie|Microsoft.Reliability|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Spravovaný kód používá pro přístup k nativním prostředkům <xref:System.IntPtr>.

## <a name="rule-description"></a>Popis pravidla
 Použití `IntPtr` ve spravovaném kódu může poukazovat na potenciální problém zabezpečení a spolehlivosti. Všechna použití `IntPtr` musí být přezkoumána, aby bylo možné určit, zda je na svém místě vyžadováno použití <xref:System.Runtime.InteropServices.SafeHandle> nebo podobné technologie. K problémům dojde, pokud `IntPtr` představuje nějaký nativní prostředek, jako je například paměť, popisovač souboru nebo soket, který je spravovaným kódem považován za vlastní. Pokud spravovaný kód vlastní prostředek, musí také uvolnit nativní prostředky, které jsou k němu přidruženy, protože v důsledku selhání by to způsobilo únik prostředků.

 V takových scénářích budou k dispozici také problémy zabezpečení nebo spolehlivost, pokud je povolený přístup s více vlákny `IntPtr` a způsob uvolnění prostředku, který je reprezentován `IntPtr`. Tyto problémy zahrnují recyklaci hodnoty `IntPtr` v uvolnění prostředků, zatímco se souběžné používání prostředků provádí v jiném vlákně. To může způsobit časování časování, ve kterém jedno vlákno může číst nebo zapisovat data přidružená k chybnému prostředku. Například pokud váš typ uchovává popisovač operačního systému jako `IntPtr` a umožňuje uživatelům volat jak **Zavřít** , tak i jinou metodu, která tento popisovač používá současně a bez určitého druhu synchronizace, váš kód má potíže s recyklací popisovače.

 Tento problém recyklace obslužné rutiny může způsobit poškození dat a často ohrožení zabezpečení. `SafeHandle` a jeho třída na stejné úrovni <xref:System.Runtime.InteropServices.CriticalHandle> poskytuje mechanismus pro zapouzdření nativního popisovače do prostředku, aby se takové problémy s vlákny mohly vyhnout. Kromě toho můžete použít `SafeHandle` a jeho třídu stejné úrovně `CriticalHandle` pro jiné problémy s vlákny, například k pečlivému řízení životnosti spravovaných objektů, které obsahují kopii nativního popisovače přes volání do nativních metod. V této situaci můžete často odebrat volání `GC.KeepAlive`. Režijní náklady na výkon vám Thay, když používáte `SafeHandle` a, do menší úrovně `CriticalHandle` je často možné omezit prostřednictvím pečlivého návrhu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Převeďte `IntPtr` využití na `SafeHandle` pro bezpečnou správu přístupu k nativním prostředkům. Příklady najdete v tématu <xref:System.Runtime.InteropServices.SafeHandle> reference.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Toto upozornění byste neměli potlačit.

## <a name="see-also"></a>Viz také
 <xref:System.IDisposable>
