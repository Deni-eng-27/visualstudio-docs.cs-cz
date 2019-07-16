---
title: Deklarace CA5122 nespravovaného kódu nesmí být bezpečné kritické | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
ms.assetid: f2581a6d-2a0e-40c1-b600-f5dc70909200
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: eff316ac6f5d73e157e3dbef5126195bd0d62878
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68201480"
---
# <a name="ca5122-pinvoke-declarations-should-not-be-safe-critical"></a>CA5122: Deklarace volání nespravovaného kódu nesmí být kritické pro zabezpečení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|PInvokesShouldNotBeSafeCriticalFxCopRule|
|CheckId|CA5122|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Deklarace P/Invoke byla označena atributem <xref:System.Security.SecuritySafeCriticalAttribute>:

```csharp
[assembly: AllowPartiallyTrustedCallers]

// ...
public class C
{
    [SecuritySafeCritical]
    [DllImport("kernel32.dll")]
    public static extern bool Beep(int frequency, int duration); // CA5122 – safe critical p/invoke
   }
```

 V tomto příkladu `C.Beep(...)` byl označen jako zabezpečení bezpečně kritická metoda.

## <a name="rule-description"></a>Popis pravidla
 Metody jsou při provádění operace citlivé na zabezpečení označeny jako SecuritySafeCritical, ale lze je také bezpečně použít transparentním kódem. Jedním ze základních pravidel modelu transparentnosti zabezpečení je, že transparentní kód nikdy nesmí přímo volat nativní kód prostřednictvím deklarace P/Invoke. Proto označení P/Invoke jako bezpečně kritické z hlediska zabezpečení neumožní transparentnímu kódu vyvolat je a je zavádějící pro analýzu zabezpečení.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Aby byla deklarace P/Invoke zpřístupněna pro transparentní kód, vystavte pro něj z hlediska zabezpečení bezpečně kritickou obalující metodu.

```csharp
[assembly: AllowPartiallyTrustedCallers

class C
{
   [SecurityCritical]
   [DllImport(“kernel32.dll”, EntryPoint=”Beep”)]
   private static extern bool BeepPinvoke(int frequency, int duration); // Security Critical P/Invoke

   [SecuritySafeCritical]
   public static bool Beep(int frequency, int duration)
   {
      return BeepPInvoke(frequency, duration);
   }
}
```

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.
