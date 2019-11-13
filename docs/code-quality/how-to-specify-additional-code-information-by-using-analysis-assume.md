---
title: Použití _Analysis_assume pro tipy pro analýzu kódu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- _Analysis_assume
helpviewer_keywords:
- _Analysis_assume
ms.assetid: 51205d97-4084-4cf4-a5ed-3eeaf67deb1b
author: mikeblome
ms.author: mblome
manager: markl
ms.workload:
- multiple
ms.openlocfilehash: 9933a013ed4f2df0978fb66e3aff87b4cdc024f9
ms.sourcegitcommit: c6af923c1f485959d751b23ab3f03541013fc4a7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/12/2019
ms.locfileid: "73925965"
---
# <a name="how-to-specify-additional-code-information-by-using-_analysis_assume"></a>Postupy: určení dalších informací o kódu pomocí _Analysis_assume

Můžete poskytnout nápovědu nástroji pro analýzu kódu pro C/C++ kód, který pomůže procesu analýzy a omezit upozornění. Chcete-li zadat další informace, použijte následující funkci:

`_Analysis_assume(`  `expr`  `)`

`expr` – libovolný výraz, který se předpokládá pro vyhodnocení na hodnotu true.

Nástroj Analýza kódu předpokládá, že podmínka reprezentovaná výrazem je pravdivá v místě, kde je funkce zobrazena a zůstává true, dokud není výraz změněn, například přiřazením proměnné.

> [!NOTE]
> `_Analysis_assume` nemá vliv na optimalizaci kódu. Mimo nástroj pro analýzu kódu je `_Analysis_assume` definováno jako No-op.

## <a name="example"></a>Příklad

Následující kód používá `_Analysis_assume` k opravě upozornění analýzy kódu [C6388](../code-quality/c6388.md):

```cpp
#include<windows.h>
#include<codeanalysis\sourceannotations.h>

using namespace vc_attributes;

//requires pc to be null
void f([Pre(Null=Yes)] char* pc);

// calls free and sets ch to null
void FreeAndNull(char** ch);

void test()
{
    char pc = (char)malloc(5);
    FreeAndNull(&pc);
    _Analysis_assume(pc == NULL);
    f(pc);
}
```

## <a name="see-also"></a>Viz také:

- [__assume](/cpp/intrinsics/assume)
