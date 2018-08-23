---
title: 'CA1404: Volejte GetLastError ihned po volání nespravovaného | Dokumentace Microsoftu'
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
- CallGetLastErrorImmediatelyAfterPInvoke
- CA1404
helpviewer_keywords:
- CallGetLastErrorImmediatelyAfterPInvoke
- CA1404
ms.assetid: 52ae9eff-50f9-4b2f-8039-ca7e49fba88e
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 718612b0e74eb0f4a8d966c4cb3ebc0cfa7c1f10
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675730"
---
# <a name="ca1404-call-getlasterror-immediately-after-pinvoke"></a>CA1404: Volejte GetLastError ihned po volání nespravovaného kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1404: volejte GetLastError ihned po volání nespravovaného](https://docs.microsoft.com/visualstudio/code-quality/ca1404-call-getlasterror-immediately-after-p-invoke).  
  
TypeName | CallGetLastErrorImmediatelyAfterPInvoke |  
| ID kontroly | CA1404 |  
| Kategorie | Microsoft.Interoperability|  
| Zásadní změna | Ukončování bez |  
  
## <a name="cause"></a>příčina  
 Je provedeno volání <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A?displayProperty=fullName> metody nebo ekvivalentní Win32 `GetLastError` funkce a volání, která se dodává bezprostředně před není na platformu vyvolání metody.  
  
## <a name="rule-description"></a>Popis pravidla  
 Platforma vyvolat metodu přístupy do nespravovaného kódu a je definován pomocí `Declare` – klíčové slovo v [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] nebo <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> atribut. Obecně platí, nebude úspěšná, volání nespravovaných funkcí Win32 `SetLastError` funkce pro nastavení, která souvisí s selhání kód chyby. Volající funkci neúspěšných volání Win32 `GetLastError` funkce načíst kód chyby a zjistěte příčinu selhání. Kód chyby se udržuje na základě vlákna a další volání přepíše `SetLastError`. Po volání se nezdařilo platformy vyvolat metodu, spravovaný kód může načíst kód chyby: voláním <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> metody. Protože kód chyby může být přepsána vnitřní volání z jiné metody knihovny spravovanou třídu `GetLastError` nebo <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> metoda by měla být volána ihned po volání metody vyvolání platformy.  
  
 Pravidlo ignoruje volání následující spravované členy, když k nim dojde mezi volání na platformu vyvolání metody a volání <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A>. Tyto členy, neměňte chyba kódu a jsou užitečné při určování úspěch některé platformy vyvolat volání metody.  
  
-   <xref:System.IntPtr.Zero?displayProperty=fullName>  
  
-   <xref:System.IntPtr.op_Equality%2A?displayProperty=fullName>  
  
-   <xref:System.IntPtr.op_Inequality%2A?displayProperty=fullName>  
  
-   <xref:System.Runtime.InteropServices.SafeHandle.IsInvalid%2A?displayProperty=fullName>  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, přesuňte volání <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> tak, aby okamžitě následuje volání na platformu vyvolání metody.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Potlačit upozornění tohoto pravidla, pokud kód mezi platformu vyvolání volání metody můžete bezpečně a <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> volání metody nelze explicitně nebo implicitně způsobit, že kód chyby: Chcete-li změnit.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje metodu, která porušuje pravidlo a metodu, která splňuje pravidlo.  
  
 [!code-csharp[FxCop.Interoperability.LastErrorPInvoke#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.LastErrorPInvoke/cs/FxCop.Interoperability.LastErrorPInvoke.cs#1)]
 [!code-vb[FxCop.Interoperability.LastErrorPInvoke#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.LastErrorPInvoke/vb/FxCop.Interoperability.LastErrorPInvoke.vb#1)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1060: Přesuňte volání nespravovaných kódů do třídy NativeMethods](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)  
  
 [CA1400: Vstupní body volání nespravovaného by měly existovat](../code-quality/ca1400-p-invoke-entry-points-should-exist.md)  
  
 [Ca1401: volání nespravovaných kódů. volání nespravovaných kódů by neměly být viditelné](../code-quality/ca1401-p-invokes-should-not-be-visible.md)  
  
 [CA2101: Určete zařazování pro argumenty řetězce volání nespravovaného](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)  
  
 [CA2205: Použijte spravované ekvivalenty rozhraní Win32 API](../code-quality/ca2205-use-managed-equivalents-of-win32-api.md)



