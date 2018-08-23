---
title: 'CA2235: Označte všechna neserializovatelná pole | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2235
- MarkAllNonSerializableFields
helpviewer_keywords:
- CA2235
- MarkAllNonSerializableFields
ms.assetid: 599ad877-3a15-426c-bf17-5de15427365f
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 641f9c4dc5deec777ed4a0f74a920fc73e6af3d8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42680775"
---
# <a name="ca2235-mark-all-non-serializable-fields"></a>CA2235: Označte všechna neserializovatelná pole
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2235: označte všechna neserializovatelná pole](https://docs.microsoft.com/visualstudio/code-quality/ca2235-mark-all-non-serializable-fields).  
  
TypeName | MarkAllNonSerializableFields |  
| ID kontroly | CA2235 |  
| Kategorie | Microsoft.Usage|  
| Zásadní změna | Bez zásadní |  
  
## <a name="cause"></a>příčina  
 Neserializovatelný typ pole instance je deklarován v serializovatelném typu.  
  
## <a name="rule-description"></a>Popis pravidla  
 Serializovatelný typ. je ten, který je označen <xref:System.SerializableAttribute?displayProperty=fullName> atribut. Když je typ serializován, <xref:System.Runtime.Serialization.SerializationException?displayProperty=fullName> je vyvolána výjimka, pokud typ obsahuje pole instance typu, který není serializovatelný.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, použijte <xref:System.NonSerializedAttribute?displayProperty=fullName> atributu na pole, který není serializovatelný.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Pouze v případě potlačit upozornění tohoto pravidla <xref:System.Runtime.Serialization.ISerializationSurrogate?displayProperty=fullName> typ je deklarován, která umožňuje instance pole, které chcete serializovat a deserializovat.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ, který porušuje pravidla a typ, který splňuje pravidlo.  
  
 [!code-csharp[FxCop.Usage.MarkNonSerializable#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.MarkNonSerializable/cs/FxCop.Usage.MarkNonSerializable.cs#1)]
 [!code-vb[FxCop.Usage.MarkNonSerializable#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.MarkNonSerializable/vb/FxCop.Usage.MarkNonSerializable.vb#1)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA2236: Volejte metody třídy Base na typech ISerializable](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)  
  
 [CA2240: Implementujte správně ISerializable](../code-quality/ca2240-implement-iserializable-correctly.md)  
  
 [CA2229: Implementovat serializační konstruktory](../code-quality/ca2229-implement-serialization-constructors.md)  
  
 [CA2238: Implementujte správně metody serializace](../code-quality/ca2238-implement-serialization-methods-correctly.md)  
  
 [CA2237: Označte typy ISerializable pomocí SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)  
  
 [CA2239: Poskytujte metody deserializace pro nepovinné pole](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)  
  
 [CA2120: Zabezpečte serializační konstruktory](../code-quality/ca2120-secure-serialization-constructors.md)



