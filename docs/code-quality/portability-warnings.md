---
title: Upozornění přenositelnosti
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.PortabilityRules
helpviewer_keywords:
- portability warnings
- managed code analysis warnings, portability warnings
- warnings, portability
ms.assetid: 902e859a-2153-4970-baaa-8a5b4a11806f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a6a3557cffec60de91da46f60040ec675c866cbf
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55946598"
---
# <a name="portability-warnings"></a>Upozornění přenositelnosti
Upozornění přenositelnosti podporují přenositelnost napříč různými operačními systémy.

## <a name="in-this-section"></a>V tomto oddílu

|Pravidlo|Popis|
|----------|-----------------|
|[CA1900: Pole hodnot by měla být přenosná](../code-quality/ca1900-value-type-fields-should-be-portable.md)|Toto pravidlo zkontroluje, že budou při zařazení na nespravovaný kód v 64bitových operačních systémech správně zarovnány struktury, které jsou deklarovány pomocí explicitního rozložení atribut.|
|[CA1901: Deklarace volání nespravovaného kódu by měla být přenosná](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)|Toto pravidlo vyhodnotí velikost každého parametru a vrácené hodnoty deklarace P/Invoke a ověří, jestli je správná při zařazení na nespravovaný kód v 32bitové a 64bitové operační systémy jejich velikost.|
|[CA1903: Použijte pouze API z cíleného rozhraní](../code-quality/ca1903-use-only-api-from-targeted-framework.md)|Člen nebo typ používá člen nebo typ, který byl uveden v aktualizaci Service Pack, která nebyla zahrnuta stejně jako cílové rozhraní projektu.|