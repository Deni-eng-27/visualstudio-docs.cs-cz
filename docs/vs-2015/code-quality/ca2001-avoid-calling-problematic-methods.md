---
title: 'CA2001: Vyhněte se volání problematických metod | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2001
- AvoidCallingProblematicMethods
helpviewer_keywords:
- CA2001
- AvoidCallingProblematicMethods
ms.assetid: 19db8edb-31ce-441c-b0de-a0f2746155b7
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 17f3c283f0a837873c5e01716ec2c412b1e67f16
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72667734"
---
# <a name="ca2001-avoid-calling-problematic-methods"></a>CA2001: Vyhněte se volání problematických metod
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|AvoidCallingProblematicMethods|
|CheckId|CA2001|
|Kategorie|Microsoft.Reliability|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Člen volá potencionálně nebezpečnou nebo problematickou metodu.

## <a name="rule-description"></a>Popis pravidla
 Vyhněte se zbytečným a potenciálně nebezpečným voláním metody.

 Porušení tohoto pravidla nastane, když člen volá jednu z následujících metod.

|Metoda|Popis|
|------------|-----------------|
|<xref:System.GC.Collect%2A?displayProperty=fullName>|Volání GC. Shromažďování může významně ovlivnit výkon aplikace a je zřídka nezbytné. Další informace najdete na blogu [Mariani Performance pikantní](http://go.microsoft.com/fwlink/?LinkId=169256) na webu MSDN.|
|<xref:System.Threading.Thread.Resume%2A?displayProperty=fullName><br /><br /> <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName>|Vlákno. Suspend a Thread. Resume bylo Zastaralé z důvodu jejich nepředvídatelného chování.  Použijte jiné třídy v oboru názvů <xref:System.Threading>, například <xref:System.Threading.Monitor>, <xref:System.Threading.Mutex> a <xref:System.Threading.Semaphore> k synchronizaci vláken nebo ochraně prostředků.|
|<xref:System.Runtime.InteropServices.SafeHandle.DangerousGetHandle%2A?displayProperty=fullName>|Metoda DangerousGetHandle představuje bezpečnostní riziko, protože může vrátit neplatný popisovač. Další informace o tom, jak bezpečně používat metodu DangerousGetHandle, najdete v <xref:System.Runtime.InteropServices.SafeHandle.DangerousAddRef%2A> a <xref:System.Runtime.InteropServices.SafeHandle.DangerousRelease%2A> metodách.|
|<xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName><br /><br /> <xref:System.Reflection.Assembly.LoadFile%2A?displayProperty=fullName><br /><br /> <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=fullName>|Tyto metody mohou načítat sestavení z neočekávaných umístění. Přečtěte si třeba informace o metodách, které načítají sestavení, na blogu Suzanne Cook – blogové příspěvky [LoadFile vs. LoadFrom](http://go.microsoft.com/fwlink/?LinkId=164450) a [Výběr kontextu vazby](http://go.microsoft.com/fwlink/?LinkId=164451) na webu MSDN.|
|[CoSetProxyBlanket](http://go.microsoft.com/fwlink/?LinkID=169250) (Ole32)<br /><br /> [: CoInitializeSecurity](http://go.microsoft.com/fwlink/?LinkId=169255) (Ole32)|V době, kdy se uživatelský kód začne spouštět ve spravovaném procesu, je příliš pozdě spolehlivě volat CoSetProxyBlanket. Modul CLR (Common Language Runtime) provede inicializační akce, které mohou zabránit úspěšnému volání uživatelů.<br /><br /> Pokud je třeba volat CoSetProxyBlanket pro spravovanou aplikaci, doporučujeme spustit proces pomocí spustitelného souboru nativního kódu (C++), zavolat CoSetProxyBlanket v nativním kódu a pak spustit aplikaci spravovaného kódu v procesu. (Nezapomeňte zadat číslo verze modulu runtime.)|

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, odeberte nebo nahraďte volání nebezpečné nebo problematické metody.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Zprávy z tohoto pravidla byste měli potlačit pouze v případě, že nejsou k dispozici žádné alternativy problematické metody.

## <a name="see-also"></a>Viz také
 [Upozornění spolehlivosti](../code-quality/reliability-warnings.md)
