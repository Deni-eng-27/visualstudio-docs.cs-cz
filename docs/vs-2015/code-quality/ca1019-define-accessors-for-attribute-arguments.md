---
title: 'CA1019: Definujte přístupové objekty pro argumenty atributu | Dokumentace Microsoftu'
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
- CA1019
- DefineAccessorsForAttributeArguments
helpviewer_keywords:
- CA1019
- DefineAccessorsForAttributeArguments
ms.assetid: 197f2378-3c43-427e-80de-9ec25006c05c
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 84f528e33d6f904cf44d9c7b2cea9a8f364f8a9e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667135"
---
# <a name="ca1019-define-accessors-for-attribute-arguments"></a>CA1019: Definujte přístupové objekty pro argumenty atributu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1019: Definujte přístupové objekty pro argumenty atributu](https://docs.microsoft.com/visualstudio/code-quality/ca1019-define-accessors-for-attribute-arguments).  
  
TypeName | DefineAccessorsForAttributeArguments |  
| ID kontroly | CA1019 |  
| Kategorie | Microsoft.Design|  
| Zásadní změna | Ukončování bez |  
  
## <a name="cause"></a>příčina  
 V konstruktoru definuje atribut argumenty, které nemají odpovídající vlastnosti.  
  
## <a name="rule-description"></a>Popis pravidla  
 Atributy mohou definovat povinné argumenty, které musí být specifikovány při použití atributu na cíl. Říká se jim také poziční argumenty, jelikož jsou konstruktorům atributů předány jako poziční parametry. Pro každý povinný argument by měl atribut navíc poskytovat odpovídající vlastnost jen pro čtení, aby mohla být hodnota argumentu během spuštění získána. Toto pravidlo zkontroluje, pro každý parametr konstruktoru definovanou odpovídající vlastnost.  
  
 Atributy mohou také definovat volitelné argumenty, které jsou rovněž známy jako pojmenované argumenty. Tyto argumenty jsou podle názvu poskytovány konstruktorům atributů a měly by mít odpovídající vlastnost pro čtení i zápis.  
  
 Povinné a nepovinné argumenty, odpovídající vlastnosti a parametry konstruktoru musí použít stejný název, ale jinou velikostí písmen. Vlastnosti využívají Pascal velká a malá písmena a parametry ve formátu camelCase použití malých a velkých písmen.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, přidejte vlastnost jen pro čtení pro každý parametr konstruktoru, který nemá.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Potlačit upozornění tohoto pravidla, pokud nechcete, aby hodnota retrievable povinný argument.  
  
## <a name="custom-attributes-example"></a>Příklad vlastní atributy  
  
### <a name="description"></a>Popis  
 Následující příklad ukazuje dva atributy, které definují povinný parametr (poziční). První implementaci atributu je nesprávně definovaný. Druhý implementace je správná.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Design.AttributeAccessors#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.AttributeAccessors/cs/FxCop.Design.AttributeAccessors.cs#1)]
 [!code-vb[FxCop.Design.AttributeAccessors#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.AttributeAccessors/vb/FxCop.Design.AttributeAccessors.vb#1)]  
  
## <a name="positional-and-named-arguments"></a>Poziční a pojmenované argumenty  
  
### <a name="description"></a>Popis  
 Pojmenované a poziční argumenty Ujistěte se, mazání a spotřebitelé knihovny které argumenty jsou povinné pro atribut a které argumenty jsou volitelné.  
  
 Následující příklad ukazuje implementaci atributu, který má pojmenované i poziční argumenty.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Design.AttributeAccessorsNamed#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.AttributeAccessorsNamed/cs/FxCop.Design.AttributeAccessorsNamed.cs#1)]  
  
### <a name="comments"></a>Komentáře  
 Následující příklad ukazuje, jak použít vlastní atribut na dvě vlastnosti.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Design.AttributeAccessorsNamedApplied#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.AttributeAccessorsNamedApplied/cs/FxCop.Design.AttributeAccessorsNamedApplied.cs#1)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1813: Vyhněte se nezapečetěným atributům](../code-quality/ca1813-avoid-unsealed-attributes.md)  
  
## <a name="see-also"></a>Viz také  
 [Atributy](http://msdn.microsoft.com/library/ee0038ef-b247-4747-a650-3c5c5cd58d8b)



