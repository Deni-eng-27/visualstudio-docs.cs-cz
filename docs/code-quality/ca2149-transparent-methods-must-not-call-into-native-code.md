---
title: "CA2149: Transparentní metody nesmějí provádět volání do nativního kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CA2149
ms.assetid: 28951bd7-f3db-4871-99aa-bad68d1ead80
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 937b6c203b7ee5a2dbe2c77ba1c67ca7500c1fa4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca2149-transparent-methods-must-not-call-into-native-code"></a>CA2149: Transparentní metody nesmějí provádět volání do nativního kódu
|||  
|-|-|  
|TypeName|TransparentMethodsMustNotCallNativeCode|  
|CheckId|CA2149|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Metoda volá nativní funkce prostřednictvím se zakázaným inzerováním metoda, jako je například P/Invoke.  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo je vyvoláno na jakékoli transparentní metodě, která přímo volá nativní kód, například prostřednictvím P/Invoke. Toto pravidlo porušení vést k <xref:System.MethodAccessException> ve model průhlednost úrovně 2 a úplný požadavek pro <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A> ve model průhlednost úrovně 1.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, označit metody, která volá nativní kód <xref:System.Security.SecurityCriticalAttribute> nebo <xref:System.Security.SecuritySafeCriticalAttribute> atribut.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 [!code-csharp[FxCop.Security.CA2149.TransparentMethodsMustNotCallNativeCode#1](../code-quality/codesnippet/CSharp/ca2149-transparent-methods-must-not-call-into-native-code_1.cs)]