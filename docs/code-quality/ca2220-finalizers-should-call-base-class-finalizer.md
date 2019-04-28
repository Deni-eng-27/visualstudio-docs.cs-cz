---
title: 'CA2220: Finalizační metody by měly volat finalizační metodu základní třídy'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2220
- FinalizersShouldCallBaseClassFinalizer
helpviewer_keywords:
- CA2220
- FinalizersShouldCallBaseClassFinalizer
ms.assetid: 48329f42-170d-45ee-a381-e33f55a240c5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 034f80c9198ab098070e6642f4a4d96cff1744c5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541855"
---
# <a name="ca2220-finalizers-should-call-base-class-finalizer"></a>CA2220: Finalizační metody by měly volat finalizační metodu základní třídy

|||
|-|-|
|TypeName|FinalizersShouldCallBaseClassFinalizer|
|CheckId|CA2220|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina

Typ, který přepíše <xref:System.Object.Finalize%2A?displayProperty=fullName> nevolá <xref:System.Object.Finalize%2A> metoda v její základní třídě.

## <a name="rule-description"></a>Popis pravidla

Finalizační metoda musí být šířena přes hierarchii dědičnosti. Aby toto bylo zajištěno, musí typy zavolat své základní třídy <xref:System.Object.Finalize%2A> metodu z v rámci své vlastní <xref:System.Object.Finalize%2A> metody. Kompilátor jazyka C# automaticky přidá volání finalizační metodu třídy base.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, zavolejte základní typ <xref:System.Object.Finalize%2A> metodu z vašeho <xref:System.Object.Finalize%2A> metody.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění na toto pravidlo. Některé kompilátory, které se zaměřují na modul common language runtime vložit volání do finalizační metodu základního typu do Microsoft intermediate language (MSIL). Pokud upozornění toto pravidlo se použije v hlášení, kompilátor nevkládá volání a je třeba přidat ji do vašeho kódu.

## <a name="example"></a>Příklad

Následující příklad jazyka Visual Basic ukazuje typ `TypeB` , která správně volá <xref:System.Object.Finalize%2A> metoda v její základní třídě.

[!code-vb[FxCop.Usage.IDisposableBaseCalled#1](../code-quality/codesnippet/VisualBasic/ca2220-finalizers-should-call-base-class-finalizer_1.vb)]

## <a name="see-also"></a>Viz také:

- [Vzor pro metodu Dispose](/dotnet/standard/design-guidelines/dispose-pattern)