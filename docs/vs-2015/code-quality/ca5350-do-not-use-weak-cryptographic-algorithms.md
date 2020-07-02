---
title: 'CA5350: Nepoužívejte slabé kryptografické algoritmy | Microsoft Docs'
ms.date: 11/15/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
ms.assetid: 4c51bb8a-fcfa-46aa-ab61-634be84c4a7a
caps.latest.revision: 11
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: afadf41fc753051047e858758bfe0677987d726d
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/30/2020
ms.locfileid: "85545064"
---
# <a name="ca5350-do-not-use-weak-cryptographic-algorithms"></a>CA5350: Nepoužívejte slabé kryptografické algoritmy
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Položka|Hodnota|
|-|-|
|TypeName|DoNotUseWeakCryptographicAlgorithms|
|CheckId|CA5350|
|Kategorie|Microsoft. kryptografie|
|Narušující změna|Bez přerušení|

> [!NOTE]
> Toto upozornění se naposledy aktualizovalo od listopadu 2015.

## <a name="cause"></a>Příčina
 Šifrovací algoritmy jako <xref:System.Security.Cryptography.TripleDES> a algoritmy hash, jako <xref:System.Security.Cryptography.SHA1> jsou a, <xref:System.Security.Cryptography.RIPEMD160> se považují za slabé.

 Tyto kryptografické algoritmy neposkytují žádné záruky zabezpečení jako pokročilejší protějšky. Kryptografické algoritmy hash <xref:System.Security.Cryptography.SHA1> a <xref:System.Security.Cryptography.RIPEMD160> poskytují méně kolizí proti kolizi než moderní algoritmy hash. Šifrovací algoritmus <xref:System.Security.Cryptography.TripleDES> poskytuje méně bitů zabezpečení než více moderních šifrovacích algoritmů.

## <a name="rule-description"></a>Popis pravidla
 Slabé algoritmy šifrování a funkce hash jsou dnes používány z mnoha důvodů, ale neměly by se používat ke zaručení důvěrnosti dat, která chrání.

 Pravidlo se aktivuje, když v kódu nalezne algoritmy 3DES, SHA1 nebo RIPEMD160 a vyvolá uživateli upozornění.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Používejte kryptograficky silnější možnosti:

- Pro šifrování TripleDES použijte <xref:System.Security.Cryptography.Aes> šifrování.

- V případě funkcí hash SHA1 nebo RIPEMD160 používejte funkce v rodině [SHA-2](https://msdn.microsoft.com/library/windows/desktop/aa382459.aspx) (např., <xref:System.Security.Cryptography.SHA512> <xref:System.Security.Cryptography.SHA384> <xref:System.Security.Cryptography.SHA256> ).

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačí upozornění od tohoto pravidla, pokud úroveň ochrany potřebná pro data nevyžaduje záruku zabezpečení.

## <a name="pseudo-code-example"></a>Příklad kódu pseudo-code
 V době psaní tohoto pravidla znázorňuje následující příklad pseudo kódu ilustrující vzor zjištěný tímto pravidlem.

### <a name="sha-1-hashing-violation"></a>Porušení hodnoty hash SHA-1

```
using System.Security.Cryptography;
...
var hashAlg = SHA1.Create();

```

### <a name="solution"></a>Řešení

```
using System.Security.Cryptography;
...
var hashAlg = SHA256.Create();

```

### <a name="ripemd160-br-br-hashing-violation"></a>RIPEMD160 <br /><br />Porušení hashování

```
using System.Security.Cryptography;
...
var hashAlg = RIPEMD160Managed.Create();

```

### <a name="solution"></a>Řešení

```
using System.Security.Cryptography;
...
var hashAlg = SHA256.Create();

```

### <a name="tripledes-encryption-violation"></a>Narušení šifrování TripleDES

```
using System.Security.Cryptography;
...
using (TripleDES encAlg = TripleDES.Create())
{
  ...
}
```

### <a name="solution"></a>Řešení

```
using System.Security.Cryptography;
...
using (AesManaged encAlg = new AesManaged())
{
  ...
}
```