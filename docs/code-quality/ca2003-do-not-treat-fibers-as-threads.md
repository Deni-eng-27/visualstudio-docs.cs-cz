---
title: 'CA2003: Nezacházejte s vlákénky jako s vlákny'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2003
- DoNotTreatFibersAsThreads
helpviewer_keywords:
- CA2003
- DoNotTreatFibersAsThreads
ms.assetid: 15398fb1-f384-4bcc-ad93-00e1c0fa9ddf
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9f5e4e7eb28207cb37824b23acbbac02b6df380d
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/24/2019
ms.locfileid: "71233135"
---
# <a name="ca2003-do-not-treat-fibers-as-threads"></a>CA2003: Nezacházejte s vlákénky jako s vlákny

|||
|-|-|
|TypeName|DoNotTreatFibersAsThreads|
|CheckId|CA2003|
|Kategorie|Microsoft.Reliability|
|Zásadní změna|Nenarušující|

## <a name="cause"></a>příčina

Spravované vlákno je považováno za vlákno Win32.

## <a name="rule-description"></a>Popis pravidla

Nepředpokládat spravované vlákno je vlákno Win32; je to vlákno. Modul CLR (Common Language Runtime) spouští spravovaná vlákna jako vlákna v kontextu reálných vláken, která vlastní SQL. Tato vlákna lze sdílet napříč doménami aplikace a dokonce i databázemi v procesu SQL Server. Použití spravovaného úložiště thread local funguje, ale nepoužíváte nespravované úložiště thread local nebo předpokládáte, že váš kód bude spuštěn v aktuálním vláknu operačního systému. Neměňte nastavení, jako je národní prostředí vlákna. Nevolejte CreateCriticalSection ani CreateMutex prostřednictvím P/Invoke, protože vyžadují, aby vlákno, které vstupuje na zámek, také ukončilo zámek. Vzhledem k tomu, že vlákno, které zadává zámek, neukončí zámek při použití vlákna, jsou důležité oddíly a mutexy Win32 v SQL nepoužitelné. Většinu stavu můžete bezpečně použít u spravovaného <xref:System.Threading.Thread> objektu, včetně spravovaného Thread localho úložiště a aktuální jazykové verze daného vlákna v uživatelském rozhraní. Nicméně pro účely programovacího modelu nebudete moci změnit aktuální jazykovou verzi vlákna při použití jazyka SQL. Toto omezení bude vynutilo nové oprávnění.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Prověřte použití vláken a odpovídajícím způsobem změňte kód.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Toto pravidlo potlačit.