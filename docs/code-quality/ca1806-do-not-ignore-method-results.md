---
title: 'CA1806: Neignorujte výsledky metody'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1806
- DoNotIgnoreMethodResults
helpviewer_keywords:
- CA1806
- DoNotIgnoreMethodResults
ms.assetid: fd805687-0817-481e-804e-b62cfb3b1076
author: gewarren
ms.author: gewarren
dev_langs:
- CPP
- CSharp
- VB
manager: jillfra
ms.openlocfilehash: 2e68fb6b4c40c165a09ae2631a2ad0a64bf52fbc
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921559"
---
# <a name="ca1806-do-not-ignore-method-results"></a>CA1806: Neignorujte výsledky metody

|||
|-|-|
|TypeName|DoNotIgnoreMethodResults|
|CheckId|CA1806|
|Kategorie|Microsoft.Usage|
|Narušující změna|Bez přerušení|

## <a name="cause"></a>příčina

Toto upozornění může mít několik možných důvodů:

- Vytvoří se nový objekt, ale nikdy se nepoužije.

- Metoda, která vytvoří a vrátí nový řetězec, je volána a nový řetězec se nikdy nepoužije.

- Metoda COM nebo volání nespravovaného kódu, která vrací hodnotu HRESULT nebo kód chyby, který se nikdy nepoužívá. Popis pravidla

Zbytečným vytvářením objektů a přidruženým uvolňováním paměti nevyužitého objektu, který snižuje výkon.

Řetězce jsou neměnné a metody, jako je String. ToUpper vrací novou instanci řetězce namísto úpravy instance řetězce v volající metodě.

Ignorování HRESULT nebo kód chyby může vést k neočekávanému chování v chybových stavech nebo v podmínkách s nízkými prostředky.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Pokud metoda A vytvoří novou instanci objektu B, který se nikdy nepoužívá, předejte instanci jako argument jiné metodě nebo přiřaďte instanci proměnné. Pokud je vytvoření objektu zbytečné, odeberte ho.-nebo-

Pokud metoda volá metodu B, ale nepoužívá novou instanci řetězce, kterou metoda B vrátí. Předejte instanci jako argument jiné metodě, přiřaďte instanci proměnné. Nebo odeberte volání, pokud není nutné.

 -nebo-

Pokud metoda volá metodu B, ale nepoužívá HRESULT nebo kód chyby, který metoda vrátí. Použijte výsledek v podmíněném příkazu, přiřaďte výsledek proměnné nebo ji předejte jako argument jiné metodě.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Potlačit upozornění z tohoto pravidla, pokud se nejedná o vytvoření objektu, který slouží k nějakému účelu.

## <a name="example"></a>Příklad
Následující příklad ukazuje třídu, která ignoruje výsledek volání String. trim.

[!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults3#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_1.cs)]
[!code-vb[FxCop.Usage.DoNotIgnoreMethodResults3#1](../code-quality/codesnippet/VisualBasic/ca1806-do-not-ignore-method-results_1.vb)]
[!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults3#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_1.cpp)]

## <a name="example"></a>Příklad
Následující příklad opravuje předchozí porušení přiřazením výsledku String. střih zpět na proměnnou, na které byla volána.

[!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults4#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_2.cs)]
[!code-vb[FxCop.Usage.DoNotIgnoreMethodResults4#1](../code-quality/codesnippet/VisualBasic/ca1806-do-not-ignore-method-results_2.vb)]
[!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults4#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_2.cpp)]

## <a name="example"></a>Příklad
Následující příklad ukazuje metodu, která nepoužívá objekt, který je vytvořen.

> [!NOTE]
> Toto porušení nelze reprodukovat v Visual Basic.

[!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults5#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_3.cpp)]
[!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults5#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_3.cs)]

## <a name="example"></a>Příklad
Následující příklad opravuje předchozí porušení odebráním zbytečného vytvoření objektu.

[!code-csharp[FxCop.Usage.DoNotIgnoreMethodResults6#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_4.cs)]
[!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults6#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_4.cpp)]

<!-- Examples don't exist for the below... -->
<!--
## Example
The following example shows a method that ignores the error code that the native method GetShortPathName returns.

## Example
The following example fixes the previous violation by checking the error code and throwing an exception when the call fails.
-->