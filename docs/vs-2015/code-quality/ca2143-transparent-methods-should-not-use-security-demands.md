---
title: 'CA2143: Transparentní metody nemohou používat požadavky zabezpečení | Dokumentace Microsoftu'
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
- CA2143
ms.assetid: 5d3923d7-cf40-4512-bc5c-0db0e0d6e25a
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 91d54d7b8376d5abd0916516bdd9e8049744a37d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42696581"
---
# <a name="ca2143-transparent-methods-should-not-use-security-demands"></a>CA2143: Transparentní metody nemohou používat požadavky zabezpečení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2143: transparentní metody nemohou používat požadavky zabezpečení](https://docs.microsoft.com/visualstudio/code-quality/ca2143-transparent-methods-should-not-use-security-demands).  
  
TypeName | TransparentMethodsShouldNotDemand |  
| ID kontroly | CA2143 |  
| Kategorie | Microsoft.Security|  
| Zásadní změna | Zásadní |  
  
## <a name="cause"></a>příčina  
 Které má průhledné typ nebo metoda je označena pomocí deklarace s <xref:System.Security.Permissions.SecurityAction?displayProperty=fullName> `.Demand` vyžádání nebo volání metody <xref:System.Security.CodeAccessPermission.Demand%2A?displayProperty=fullName> metody.  
  
## <a name="rule-description"></a>Popis pravidla  
 Kód transparentní z hlediska zabezpečení by neměl být odpovědný za ověření zabezpečení operace, a proto by neměl požadovat oprávnění. Kód transparentní z hlediska zabezpečení by měl k učinění rozhodnutí o zabezpečení používat úplné požadavky a bezpečně kritický kód by neměl spoléhat na to, že transparentní kód tyto úplné požadavky provede. Místo toho by měl být bezpečný a kritický veškerý kód, který provádí kontroly zabezpečení, jako jsou požadavky na zabezpečení.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Obecně platí, chcete-li opravit porušení tohoto pravidla, označte metody <xref:System.Security.SecuritySafeCriticalAttribute> atribut. Můžete také odebrat vyžádání.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Pravidlo soubory v následujícím kódu, protože transparentní metoda provede požadavek deklarativní zabezpečení.  
  
 [!code-csharp[FxCop.Security.CA2143.TransparentMethodsShouldNotDemand#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2143.transparentmethodsshouldnotdemand/cs/ca2143 - transparentmethodsshouldnotdemand.cs#1)]  
  
## <a name="see-also"></a>Viz také  
 [CA2142: Transparentní kód nemůže být chráněn pomocí LinkDemands](../code-quality/ca2142-transparent-code-should-not-be-protected-with-linkdemands.md)



