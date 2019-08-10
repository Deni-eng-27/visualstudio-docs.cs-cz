---
title: 'CA1060: Přesuňte volání nespravovaných kódů do třídy NativeMethods'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- MovePInvokesToNativeMethodsClass
- CA1060
helpviewer_keywords:
- MovePInvokesToNativeMethodsClass
- CA1060
ms.assetid: 06686c8c-6ad3-42f7-a355-cbaefa347cfc
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 9c05c0b17bc9866edd7c07874be14578ed4cf884
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922550"
---
# <a name="ca1060-move-pinvokes-to-nativemethods-class"></a>CA1060: Přesuňte volání nespravovaných kódů do třídy NativeMethods

|||
|-|-|
|TypeName|MovePInvokesToNativeMethodsClass|
|CheckId|CA1060|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina

Metoda používá služby vyvolání platformy pro přístup k nespravovanému kódu a není členem jedné z tříd **NativeMethods** .

## <a name="rule-description"></a>Popis pravidla

Metody vyvolání platformy, například ty, které jsou označeny pomocí <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> atributu nebo metody, které jsou definovány `Declare` pomocí klíčového slova v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], přistupuje k nespravovanému kódu. Tyto metody by měly být v jedné z následujících tříd:

- **NativeMethods** – Tato třída potlačí procházení zásobníku pro oprávnění nespravovaného kódu. (<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> nesmí být použito pro tuto třídu.) Tato třída je určena pro metody, které lze použít kdekoli, protože bude provedeno procházení zásobníku.

- **SafeNativeMethods** – Tato třída potlačí procházení zásobníku pro oprávnění nespravovaného kódu. (<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> je použito pro tuto třídu.) Tato třída je určena pro metody, které jsou bezpečné pro všechny volání. Volající z těchto metod nejsou vyžadováni k provedení úplné kontroly zabezpečení, aby bylo zajištěno, že je používání bezpečné, protože metody jsou pro libovolného volajícího neškodné.

- **UnsafeNativeMethods** – Tato třída potlačí procházení zásobníku pro oprávnění nespravovaného kódu. (<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> je použito pro tuto třídu.) Tato třída je určena pro metody, které jsou potenciálně nebezpečné. Každý volající těchto metod musí provést úplnou kontrolu zabezpečení, aby bylo zajištěno, že je použití zabezpečené, protože se neprovede žádné procházení zásobníku.

Tyto třídy jsou deklarovány `internal` jako`Friend`(, v Visual Basic) a deklaraci soukromého konstruktoru, aby se zabránilo vytváření nových instancí. Metody v těchto třídách by měly `static` být `internal` a`Shared` ( `Friend` a v Visual Basic).

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, přesuňte metodu do příslušné třídy **NativeMethods** . Pro většinu aplikací je k dispozici pouze přesun volání nespravovaného volání do nové třídy s názvem **NativeMethods** .

Pokud však vyvíjíte knihovny pro použití v jiných aplikacích, měli byste zvážit definování dvou dalších tříd, které se nazývají **SafeNativeMethods** a **UnsafeNativeMethods**. Tyto třídy připomínají třídu **NativeMethods** ; jsou však označeny pomocí speciálního atributu s názvem **SuppressUnmanagedCodeSecurityAttribute**. Při použití tohoto atributu modul runtime neprovede kompletní procházení zásobníku, aby bylo zajištěno, že všichni volající mají oprávnění k dispozici . Modul runtime obvykle při spuštění kontroluje toto oprávnění. Vzhledem k tomu, že se kontrolu neprovádí, může výrazně zlepšit výkon pro volání těchto nespravovaných metod, ale také umožňuje kód, který má omezená oprávnění k volání těchto metod.

Tento atribut byste však měli používat s velkou opatrností. Může mít vážné důsledky na zabezpečení, pokud je nesprávně implementován..

Informace o tom, jak implementovat metody, naleznete v příkladu **NativeMethods** , **SafeNativeMethods** example a **UnsafeNativeMethods** .

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
Následující příklad deklaruje metodu, která porušuje toto pravidlo. Chcete-li opravit porušení, **RemoveDirectory** volání nespravovaného přístupu do příslušné třídy, která je navržena tak, aby obsahovala pouze volání nespravovaného objektu.

[!code-vb[FxCop.Design.DllImportNativeMethods#1](../code-quality/codesnippet/VisualBasic/ca1060-move-p-invokes-to-nativemethods-class_1.vb)]
[!code-csharp[FxCop.Design.DllImportNativeMethods#1](../code-quality/codesnippet/CSharp/ca1060-move-p-invokes-to-nativemethods-class_1.cs)]

## <a name="nativemethods-example"></a>Příklad NativeMethods

### <a name="description"></a>Popis
Vzhledem k tomu, že třída **NativeMethods** by neměla být označena pomocí metody **SuppressUnmanagedCodeSecurityAttribute**, volání nespravovaného přístupu, která jsou uvedena v této třídě, budou vyžadovat oprávnění k roztřídě. Vzhledem k tomu, že většina aplikací běží z místního počítače a běží společně s úplným vztahem důvěryhodnosti, obvykle se nejedná o problém. Nicméně pokud vyvíjíte opakovaně použitelné knihovny, měli byste zvážit definování třídy **SafeNativeMethods** nebo **UnsafeNativeMethods** .

Následující příklad ukazuje metodu **interakce. ZvukovýSignál** , která zabalí funkci **MessageBeep** z User32. dll. **MessageBeep** P/Invoke je vložen do třídy **NativeMethods** .

### <a name="code"></a>Kód
[!code-csharp[FxCop.Design.NativeMethods#1](../code-quality/codesnippet/CSharp/ca1060-move-p-invokes-to-nativemethods-class_2.cs)]
[!code-vb[FxCop.Design.NativeMethods#1](../code-quality/codesnippet/VisualBasic/ca1060-move-p-invokes-to-nativemethods-class_2.vb)]

## <a name="safenativemethods-example"></a>Příklad SafeNativeMethods

### <a name="description"></a>Popis
Metody volání, které mohou být bezpečně zpřístupněny všem aplikacím a nemají žádné vedlejší účinky, by měly být umístěny do třídy s názvem **SafeNativeMethods**. Nemáte oprávnění k vyžádání a nemusíte platit mnohem pozor na to, odkud jsou volány.

Následující příklad ukazuje vlastnost **prostředí. TickCount** , která zabalí funkci **GetTickCount** z Kernel32. dll.

### <a name="code"></a>Kód
[!code-vb[FxCop.Design.NativeMethodsSafe#1](../code-quality/codesnippet/VisualBasic/ca1060-move-p-invokes-to-nativemethods-class_3.vb)]
[!code-csharp[FxCop.Design.NativeMethodsSafe#1](../code-quality/codesnippet/CSharp/ca1060-move-p-invokes-to-nativemethods-class_3.cs)]

## <a name="unsafenativemethods-example"></a>Příklad UnsafeNativeMethods

### <a name="description"></a>Popis
Metody volání, které nelze bezpečně volat a které by mohly způsobit vedlejší účinky, by měly být umístěny ve třídě s názvem **UnsafeNativeMethods**. Tyto metody by měly být přísně kontrolovány, aby se zajistilo, že nejsou uživateli k úmyslu nevystaveni. Pravidlo [CA2118: Kontrola využití](../code-quality/ca2118-review-suppressunmanagedcodesecurityattribute-usage.md) SuppressUnmanagedCodeSecurityAttribute vám může s tímto. Další možností je, že metody by měly mít jiné oprávnění, které je požadováno namísto nejenom při jejich použití.

Následující příklad ukazuje metodu **Cursor. Hide** , která zabalí funkci **ShowCursor** z User32. dll.

### <a name="code"></a>Kód
[!code-vb[FxCop.Design.NativeMethodsUnsafe#1](../code-quality/codesnippet/VisualBasic/ca1060-move-p-invokes-to-nativemethods-class_4.vb)]
[!code-csharp[FxCop.Design.NativeMethodsUnsafe#1](../code-quality/codesnippet/CSharp/ca1060-move-p-invokes-to-nativemethods-class_4.cs)]

## <a name="see-also"></a>Viz také:

- [Upozornění ohledně návrhu](../code-quality/design-warnings.md)