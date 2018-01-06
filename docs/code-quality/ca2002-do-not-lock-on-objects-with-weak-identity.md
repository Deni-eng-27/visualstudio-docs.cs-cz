---
title: "CA2002: Nepoužívejte zámky na objekty se slabou identitou | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DoNotLockOnObjectsWithWeakIdentity
- CA2002
helpviewer_keywords:
- CA2002
- DoNotLockOnObjectsWithWeakIdentity
ms.assetid: 16100b39-c6fc-452b-8fca-8b459a26c286
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 55bc495f116b4a7be8c118b47c71a9fed9f85777
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca2002-do-not-lock-on-objects-with-weak-identity"></a>CA2002: Nepoužívejte zámky na objekty se slabou identitou
|||  
|-|-|  
|TypeName|DoNotLockOnObjectsWithWeakIdentity|  
|CheckId|CA2002|  
|Kategorie|Microsoft.Reliability|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Vlákno se pokusí získat zámek na objekt, který má slabou identitou.  
  
## <a name="rule-description"></a>Popis pravidla  
 Objekt má slabou identitu, pokud k němu lze přímo přistupovat přes hranice aplikační domény. Vlákno, které se pokouší získat zámek na objekt se slabou identitou, může být blokováno jiným vláknem v jiné aplikační doméně, které má zámek na stejný objekt. Následující typy mít slabou identitou a jsou označeny pravidlem:  
  
-   <xref:System.MarshalByRefObject>  
  
-   <xref:System.ExecutionEngineException>  
  
-   <xref:System.OutOfMemoryException>  
  
-   <xref:System.StackOverflowException>  
  
-   <xref:System.String>  
  
-   <xref:System.Reflection.MemberInfo>  
  
-   <xref:System.Reflection.ParameterInfo>  
  
-   <xref:System.Threading.Thread>  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, použijte objekt z typu, který se nenachází v seznamu v části Popis.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA2213: Uvolnitelné pole by mělo být uvolněno](../code-quality/ca2213-disposable-fields-should-be-disposed.md)  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje některé zámku objektu, která porušují pravidlo.  
  
 [!code-vb[FxCop.Reliability.LockWeakObjects#1](../code-quality/codesnippet/VisualBasic/ca2002-do-not-lock-on-objects-with-weak-identity_1.vb)]
 [!code-csharp[FxCop.Reliability.LockWeakObjects#1](../code-quality/codesnippet/CSharp/ca2002-do-not-lock-on-objects-with-weak-identity_1.cs)]  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Threading.Monitor>   
 <xref:System.AppDomain>   
 [Lock – příkaz](/dotnet/csharp/language-reference/keywords/lock-statement)   
 [Příkaz SyncLock](/dotnet/visual-basic/language-reference/statements/synclock-statement)