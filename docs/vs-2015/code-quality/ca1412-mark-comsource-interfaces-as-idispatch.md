---
title: 'CA1412: Označte rozhraní ComSource jako IDispatch | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MarkComSourceInterfacesAsIDispatch
- CA1412
helpviewer_keywords:
- CA1412
- MarkComSourceInterfacesAsIDispatch
ms.assetid: 131a7563-0410-443c-a8f5-52104250cfb4
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 59fec1fddb16296f1238deb5c2f9bbf0c350cdd2
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54794932"
---
# <a name="ca1412-mark-comsource-interfaces-as-idispatch"></a>CA1412: Označte rozhraní ComSource jako IDispatch
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|MarkComSourceInterfacesAsIDispatch|
|CheckId|CA1412|
|Kategorie|Microsoft.Interoperability|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Typ je označen pomocí <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute> atribut a alespoň jednu zadanou rozhraní není označen atributem <xref:System.Runtime.InteropServices.InterfaceTypeAttribute> atribut nastaven `InterfaceIsDispatch` hodnotu.

## <a name="rule-description"></a>Popis pravidla
 <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute> slouží k identifikaci událostí rozhraní, které třída poskytuje klientům modelu COM (Component Object). Tato rozhraní musí být vystavené jako `InterfaceIsIDispatch` povolení klientům modelu COM jazyka Visual Basic 6 příjem oznámení o události. Ve výchozím nastavení, pokud rozhraní není označen atributem <xref:System.Runtime.InteropServices.InterfaceTypeAttribute> atribut, je vystavena jako duální rozhraní.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, přidat nebo upravit <xref:System.Runtime.InteropServices.InterfaceTypeAttribute> tak, aby jeho hodnota nastavená na InterfaceIsIDispatch pro všechna rozhraní, která jsou určena pomocí atributu <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute> atribut.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje třídu, kde jednoho z rozhraní porušuje pravidlo.

 [!code-csharp[FxCop.Interoperability.MarkIDispatch#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.MarkIDispatch/cs/FxCop.Interoperability.MarkIDispatch.cs#1)]
 [!code-vb[FxCop.Interoperability.MarkIDispatch#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.MarkIDispatch/vb/FxCop.Interoperability.MarkIDispatch.vb#1)]

## <a name="related-rules"></a>Související pravidla
 [CA1408: Nepoužívejte AutoDual ClassInterfaceType](../code-quality/ca1408-do-not-use-autodual-classinterfacetype.md)

## <a name="see-also"></a>Viz také
 [Postupy: Generování událostí zpracovávaných jímkou COM](http://msdn.microsoft.com/7c9944b2-e951-4c3e-a0a1-59b2ae37d7fd) [spolupráce pomocí nespravovaného kódu](http://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)
