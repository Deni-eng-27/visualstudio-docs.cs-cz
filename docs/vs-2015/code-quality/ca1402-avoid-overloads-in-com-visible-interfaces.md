---
title: 'CA1402: Vyhněte se přetížení ve viditelných rozhraních modelu COM | Dokumentace Microsoftu'
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
- AvoidOverloadsInComVisibleInterfaces
- CA1402
helpviewer_keywords:
- AvoidOverloadsInComVisibleInterfaces
- CA1402
ms.assetid: 2724c1f9-d5d3-4704-b124-21c4d398e5df
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 975e0f2601818a52bdf128869310d3af389c2da7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666399"
---
# <a name="ca1402-avoid-overloads-in-com-visible-interfaces"></a>CA1402: Vyhněte se přetížení ve viditelných rozhraních modelu COM
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1402: Vyhněte se přetížení ve viditelných rozhraních modelu COM](https://docs.microsoft.com/visualstudio/code-quality/ca1402-avoid-overloads-in-com-visible-interfaces).  
  
TypeName | AvoidOverloadsInComVisibleInterfaces |  
| ID kontroly | CA1402 |  
| Kategorie | Microsoft.Interoperability|  
| Zásadní změna | Zásadní |  
  
## <a name="cause"></a>příčina  
 Modelu COM (Component Object) viditelné rozhraní deklaruje přetížení metod.  
  
## <a name="rule-description"></a>Popis pravidla  
 Když jsou přetížené metody vystaveny klientům modulu COM, zachová svůj název pouze první přetížení metody. Následná přetížení jsou jednoznačně přejmenována přidáním názvu podtržítko znak "_" a celého čísla odpovídajícího pořadí deklarace tohoto přetížení. Představte si třeba následující metody.  
  
```  
void SomeMethod(int valueOne);  
void SomeMethod(int valueOne, int valueTwo, int valueThree);  
void SomeMethod(int valueOne, int valueTwo);  
```  
  
 Tyto metody jsou zveřejněné klientům modelu COM jako následující.  
  
```  
void SomeMethod(int valueOne);  
void SomeMethod_2(int valueOne, int valueTwo, int valueThree);  
void SomeMethod_3(int valueOne, int valueTwo);  
```  
  
 Klienty modulu COM jazyka Visual Basic 6 nemohou implementovat metody rozhraní s použitím v názvu podtržítko.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, přejmenujte přetížené metody tak, aby byly jedinečné názvy. Alternativně skrytí rozhraní modelu COM změnou usnadnění přístupu ke `internal` (`Friend` v [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) nebo použitím <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> atribut nastaven na `false`.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje rozhraní, který porušuje pravidla a rozhraní, které splňuje pravidlo.  
  
 [!code-csharp[FxCop.Interoperability.OverloadsInterface#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.OverloadsInterface/cs/FxCop.Interoperability.OverloadsInterface.cs#1)]
 [!code-vb[FxCop.Interoperability.OverloadsInterface#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.OverloadsInterface/vb/FxCop.Interoperability.OverloadsInterface.vb#1)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1413: Vyhněte se neveřejným polím v hodnotách viditelných modulem COM](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)  
  
 [CA1407: Vyhněte se statickým členům ve viditelných typech modelu COM](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)  
  
 [CA1017: Označte sestavení pomocí atributu ComVisibleAttribute](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)  
  
## <a name="see-also"></a>Viz také  
 [Spolupráce s nespravovaným kódem](http://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)   
 [Datový typ Long](http://msdn.microsoft.com/library/b4770c34-1804-4f8c-b512-c10b0893e516)



