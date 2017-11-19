---
title: "CA1404: Volejte GetLastError ihned po vyvolání P | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CallGetLastErrorImmediatelyAfterPInvoke
- CA1404
helpviewer_keywords:
- CallGetLastErrorImmediatelyAfterPInvoke
- CA1404
ms.assetid: 52ae9eff-50f9-4b2f-8039-ca7e49fba88e
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 63cd84136861b80617285a5f7f03ff4767efddca
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1404-call-getlasterror-immediately-after-pinvoke"></a>CA1404: Volejte GetLastError ihned po volání nespravovaného kódu
|||  
|-|-|  
|TypeName|CallGetLastErrorImmediatelyAfterPInvoke|  
|CheckId|CA1404|  
|Kategorie|Microsoft.Interoperability|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Přišla žádost o k <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A?displayProperty=fullName> metoda nebo ekvivalentní Win32 `GetLastError` funkce a volání, která se dodává bezprostředně před není pro platformu vyvolat metodu.  
  
## <a name="rule-description"></a>Popis pravidla  
 Platforma volání nespravovaného kódu metoda přístupů a je definován pomocí `Declare` – klíčové slovo v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] nebo <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> atribut. Obecně platí, při selhání, volání nespravovaných funkcí Win32 `SetLastError` funkce nastavit kód chyby, která souvisí s chybou. Volající neúspěšné funkce volá Win32 `GetLastError` funkce načíst kód chyby a zjistěte příčinu selhání. Kód chyby je udržovaný na základě vlákna a je přepsat další volání `SetLastError`. Po volání se nezdařilo platformy vyvolání metody, spravovaného kódu můžete načíst kód chyby při volání <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> metoda. Protože kód chyby může být přepsána interní volání z jiné metody knihovny spravované třídy, `GetLastError` nebo <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> metoda by měla být volána hned po volání metody vyvolání platformy.  
  
 Pravidlo ignoruje volání následující spravované členy při jejich výskytu mezi volání platformou vyvolat metodu a volání <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A>. Tito členové neměňte chyba kód a jsou užitečné pro určení úspěch některé platformy vyvolat volání metody.  
  
-   <xref:System.IntPtr.Zero?displayProperty=fullName>  
  
-   <xref:System.IntPtr.op_Equality%2A?displayProperty=fullName>  
  
-   <xref:System.IntPtr.op_Inequality%2A?displayProperty=fullName>  
  
-   <xref:System.Runtime.InteropServices.SafeHandle.IsInvalid%2A?displayProperty=fullName>  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Pokud chcete odstranit toto pravidlo je porušení pravidel, přesuňte volání <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> tak, aby následuje volání platformou vyvolat metodu.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění na toto pravidlo, pokud kód mezi platformou vyvolat volání metody a <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error%2A> volání metody, které nelze explicitně nebo implicitně způsobit kód chyby, chcete-li změnit.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje metodu, která porušuje pravidlo a metodu, která splňuje pravidlo.  
  
 [!code-vb[FxCop.Interoperability.LastErrorPInvoke#1](../code-quality/codesnippet/VisualBasic/ca1404-call-getlasterror-immediately-after-p-invoke_1.vb)]
 [!code-csharp[FxCop.Interoperability.LastErrorPInvoke#1](../code-quality/codesnippet/CSharp/ca1404-call-getlasterror-immediately-after-p-invoke_1.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1060: Přesuňte P/vyvolá do třídy NativeMethods](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)  
  
 [CA1400: Vstupní body P/Invoke by měla existovat.](../code-quality/ca1400-p-invoke-entry-points-should-exist.md)  
  
 [CA1401: P/by neměla být viditelné](../code-quality/ca1401-p-invokes-should-not-be-visible.md)  
  
 [CA2101: Určete zařazování pro argumenty řetězce P/Invoke](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)  
  
 [CA2205: Použijte spravované ekvivalenty rozhraní Win32 API](../code-quality/ca2205-use-managed-equivalents-of-win32-api.md)