---
title: 'CA1031: Nezachycujte výjimky obecného typu | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1031
- DoNotCatchGeneralExceptionTypes
helpviewer_keywords:
- CA1031
- DoNotCatchGeneralExceptionTypes
ms.assetid: cbc283ae-2a46-4ec0-940e-85aa189b118f
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 4588a949b4b6439c3f76270b0bcdab9cd52c23d9
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63431215"
---
# <a name="ca1031-do-not-catch-general-exception-types"></a>CA1031: Nezachycujte výjimky obecného typu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotCatchGeneralExceptionTypes|
|CheckId|CA1031|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina
 Obecná výjimka jako například <xref:System.Exception?displayProperty=fullName> nebo <xref:System.SystemException?displayProperty=fullName> je zachycena v `catch` příkazu nebo obecnou klauzulí catch, jako `catch()` se používá.

## <a name="rule-description"></a>Popis pravidla
 Obecné výjimky by neměly být zachycovány.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, zachycení více specifické výjimky nebo znovu vyvolejte obecnou výjimku jako poslední příkaz v `catch` bloku.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo. Zachycení výjimky obecného typu může skrýt problémy za běhu z knihovny uživatele a může ztížit ladění.

> [!NOTE]
> Počínaje [!INCLUDE[net_v40_long](../includes/net-v40-long-md.md)], modul CLR (CLR) poskytuje už výjimky v poškozeném stavu, ke kterým dochází v operačním systému a spravovaného kódu, jako je například porušení přístupu v [!INCLUDE[TLA#tla_mswin](../includes/tlasharptla-mswin-md.md)], zpracovávat spravovaného kódu. Pokud chcete kompilovat aplikace [!INCLUDE[net_v40_short](../includes/net-v40-short-md.md)] nebo novější verze a Udržovat zpracování výjimek v poškozeném stavu, můžete použít <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> atributu na metodu, která zpracovává výjimku v poškozeném stavu.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který porušuje tato pravidla a typ, který implementuje správně `catch` bloku.

 [!code-cpp[FxCop.Design.ExceptionAndSystemException#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.ExceptionAndSystemException/cpp/FxCop.Design.ExceptionAndSystemException.cpp#1)]
 [!code-csharp[FxCop.Design.ExceptionAndSystemException#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.ExceptionAndSystemException/cs/FxCop.Design.ExceptionAndSystemException.cs#1)]
 [!code-vb[FxCop.Design.ExceptionAndSystemException#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.ExceptionAndSystemException/vb/FxCop.Design.ExceptionAndSystemException.vb#1)]

## <a name="related-rules"></a>Související pravidla
 [CA2200: Znovu vyvolejte pro zachování podrobností zásobníku](../code-quality/ca2200-rethrow-to-preserve-stack-details.md)
