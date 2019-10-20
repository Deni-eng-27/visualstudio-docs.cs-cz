---
title: CA5351 nepoužívá poškozené kryptografické algoritmy | Microsoft Docs
ms.date: 11/15/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
ms.assetid: 483f51b3-e186-4433-b48e-5ca24a9a9c94
caps.latest.revision: 12
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 7b4a15530a43937b4f73fba1779216391c862c11
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72669021"
---
# <a name="ca5351-do-not-use-broken-cryptographic-algorithms"></a>CA5351: Nepoužívejte poškozené kryptografické algoritmy
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotUseBrokenCryptographicAlgorithms|
|CheckId|CA5351|
|Kategorie|Microsoft. kryptografie|
|Narušující změna|Bez přerušení|

> [!NOTE]
> Toto upozornění se naposledy aktualizovalo od listopadu 2015.

## <a name="cause"></a>příčina
 Funkce hash, jako jsou <xref:System.Security.Cryptography.MD5> a algoritmy šifrování, jako je například <xref:System.Security.Cryptography.DES> a <xref:System.Security.Cryptography.RC2>, mohou vystavovat významné riziko a mohou vést k expozici citlivých informací prostřednictvím technik triviálního útoku, jako jsou útoky hrubou silou a kolize hodnot hash.

 Níže uvedený seznam kryptografických algoritmů podléhá známým kryptografickým útokům. Kryptografický algoritmus hash <xref:System.Security.Cryptography.MD5> podléhá útokům kolizí hash.  V závislosti na využití může kolizí hash vést k zosobnění, manipulaci nebo jiným druhům útoků na systémy, které spoléhají na jedinečný kryptografický výstup funkce hash. Šifrovací algoritmy <xref:System.Security.Cryptography.DES> a <xref:System.Security.Cryptography.RC2> podléhají kryptografickým útokům, které mohou vést k neúmyslnému zveřejnění šifrovaných dat.

## <a name="rule-description"></a>Popis pravidla
 Nefunkční kryptografické algoritmy nejsou považovány za zabezpečené a jejich použití by se mělo nedoporučuje. Algoritmus hash MD5 je náchylný ke známým útokům na kolizi, i když se konkrétní chyba zabezpečení liší v závislosti na kontextu použití.  K zajištění integrity dat (např. signatura souboru nebo digitální certifikát) jsou obzvláště ohroženy algoritmy hash.  V tomto kontextu by útočníci mohli vygenerovat dvě samostatná data, což by mohlo nahradit neškodná data, a to beze změny hodnoty hash nebo zrušení platnosti přidruženého digitálního podpisu.

 Pro šifrovací algoritmy:

- šifrování <xref:System.Security.Cryptography.DES> obsahuje malou velikost klíče, což může být hrubě vynuceně za méně než jeden den.

- šifrování <xref:System.Security.Cryptography.RC2> je náchylné k útokům související s klíčem, kde útočník nalezne matematické vztahy mezi všemi hodnotami klíče.

  Toto pravidlo se aktivuje, když nalezne některou z výše uvedených kryptografických funkcí ve zdrojovém kódu a vyvolá uživateli upozornění.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Používejte kryptograficky silnější možnosti:

- V případě MD5 použijte v rodině [SHA-2](https://msdn.microsoft.com/library/windows/desktop/aa382459.aspx) hodnoty hash (např.  <xref:System.Security.Cryptography.SHA512>, <xref:System.Security.Cryptography.SHA384> <xref:System.Security.Cryptography.SHA256>).

- V případě DES a RC2 použijte šifrování <xref:System.Security.Cryptography.Aes>.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačí upozornění z tohoto pravidla, pokud není zkontrolováno kryptografickým odborníkem.

## <a name="pseudo-code-example"></a>Příklad kódu pseudo-code
 Následující ukázka pseudo kódu znázorňuje vzor zjištěný tímto pravidlem a možné alternativy.

### <a name="md5-hashing-violation"></a>Narušení hash MD5

```
using System.Security.Cryptography;
...
var hashAlg = MD5.Create();

```

### <a name="solution"></a>Řešení

```
using System.Security.Cryptography;
...
var hashAlg = SHA256.Create();

```

### <a name="rc2-encryption-violation"></a>RC2 narušení šifrování RC2

```
using System.Security.Cryptography;
...
RC2 encAlg = RC2.Create();

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

### <a name="des-br-br-encryption-violation"></a>ALGORITMUS <br /><br />Narušení šifrování

```
using System.Security.Cryptography;
...
DES encAlg = DES.Create();

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