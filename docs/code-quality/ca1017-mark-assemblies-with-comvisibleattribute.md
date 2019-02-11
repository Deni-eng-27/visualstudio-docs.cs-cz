---
title: 'CA1017: Označte sestavení pomocí ComVisibleAttribute'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1017
- MarkAssembliesWithComVisible
helpviewer_keywords:
- MarkAssembliesWithComVisible
- CA1017
ms.assetid: 4842cb49-8dd8-4e5d-a2d6-ceeaf6c6cf8e
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 648c59e2660c0509edfcf65ac50bf8791bc5896e
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55920116"
---
# <a name="ca1017-mark-assemblies-with-comvisibleattribute"></a>CA1017: Označte sestavení pomocí ComVisibleAttribute

|||
|-|-|
|TypeName|MarkAssembliesWithComVisible|
|CheckId|CA1017|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Sestavení nemá <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> byt aplikovaný atribut.

## <a name="rule-description"></a>Popis pravidla
 <xref:System.Runtime.InteropServices.ComVisibleAttribute> Atribut určuje způsob přístupu klientů COM ke spravovanému kódu. Dobrý návrh přikazuje, aby sestavení explicitně uvedla viditelnost modelu COM. Viditelnost modelu COM lze nastavit pro celé sestavení a poté přepsána pro jednotlivé typy a členy typu. Pokud atribut neexistuje, je obsah sestavení viditelný klientům com.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, přidejte atribut do sestavení. Pokud nechcete, aby sestavení viditelný klientům modelu COM, použijte atribut a nastavte jej na hodnotu `false`.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo. Pokud chcete sestavení viditelný, použijte atribut a nastavte jej na hodnotu `true`.

## <a name="example"></a>Příklad
 Následující příklad ukazuje sestavení, který má <xref:System.Runtime.InteropServices.ComVisibleAttribute> atribut tak, aby se pro klienty modelu COM viditelný.

 [!code-cpp[FxCop.Design.AssembliesCom#1](../code-quality/codesnippet/CPP/ca1017-mark-assemblies-with-comvisibleattribute_1.cpp)]
 [!code-vb[FxCop.Design.AssembliesCom#1](../code-quality/codesnippet/VisualBasic/ca1017-mark-assemblies-with-comvisibleattribute_1.vb)]
 [!code-csharp[FxCop.Design.AssembliesCom#1](../code-quality/codesnippet/CSharp/ca1017-mark-assemblies-with-comvisibleattribute_1.cs)]

## <a name="see-also"></a>Viz také:

- [Spolupráce s nespravovaným kódem](/dotnet/framework/interop/index)
- [Kvalifikace typů .NET pro spolupráci](/dotnet/framework/interop/qualifying-net-types-for-interoperation)