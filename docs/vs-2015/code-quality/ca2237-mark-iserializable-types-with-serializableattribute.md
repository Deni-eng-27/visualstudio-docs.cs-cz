---
title: 'CA2237: Označte typy ISerializable pomocí SerializableAttribute | Dokumentace Microsoftu'
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
- CA2237
- MarkISerializableTypesWithSerializable
helpviewer_keywords:
- MarkISerializableTypesWithSerializable
- CA2237
ms.assetid: 9bd6bb24-a527-43dd-9952-043c0c694f46
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 8191ca3ca58bcdaaf182c6a5ee5310e2cea5b87f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632402"
---
# <a name="ca2237-mark-iserializable-types-with-serializableattribute"></a>CA2237: Označte typy ISerializable pomocí SerializableAttribute
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2237: označte typy ISerializable pomocí SerializableAttribute](https://docs.microsoft.com/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute).  
  
TypeName | MarkISerializableTypesWithSerializable |  
| ID kontroly | CA2237 |  
| Kategorie | Microsoft.Usage|  
| Zásadní změna | Bez zásadní |  
  
## <a name="cause"></a>příčina  
 Externě viditelný typ implementuje <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> rozhraní a typ není označen atributem <xref:System.SerializableAttribute?displayProperty=fullName> atribut. Pravidlo ignoruje odvozené typy, jehož základní typ není serializovatelný.  
  
## <a name="rule-description"></a>Popis pravidla  
 Chcete-li rozpoznán modulem common language runtime jako serializovatelný, musí být označen pomocí <xref:System.SerializableAttribute> atribut i v případě, že typ používá vlastní rutinu serializace prostřednictvím implementace <xref:System.Runtime.Serialization.ISerializable> rozhraní.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, použijte <xref:System.SerializableAttribute> atribut typu.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění tohoto pravidla pro třídy výjimek, protože musí být serializovatelný fungování napříč doménami aplikace.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ, který porušuje pravidla. Zrušením komentáře u <xref:System.SerializableAttribute> atribut řádku splňovat pravidla.  
  
 [!code-csharp[FxCop.Usage.MarkSerializable#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.MarkSerializable/cs/FxCop.Usage.MarkSerializable.cs#1)]
 [!code-vb[FxCop.Usage.MarkSerializable#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.MarkSerializable/vb/FxCop.Usage.MarkSerializable.vb#1)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA2236: Volejte metody třídy Base na typech ISerializable](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)  
  
 [CA2240: Implementujte správně ISerializable](../code-quality/ca2240-implement-iserializable-correctly.md)  
  
 [CA2229: Implementovat serializační konstruktory](../code-quality/ca2229-implement-serialization-constructors.md)  
  
 [CA2238: Implementujte správně metody serializace](../code-quality/ca2238-implement-serialization-methods-correctly.md)  
  
 [CA2235: Označte všechna neserializovatelná pole](../code-quality/ca2235-mark-all-non-serializable-fields.md)  
  
 [CA2239: Poskytujte metody deserializace pro nepovinné pole](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)  
  
 [CA2120: Zabezpečte serializační konstruktory](../code-quality/ca2120-secure-serialization-constructors.md)


