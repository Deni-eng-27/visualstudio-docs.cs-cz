---
title: Kontext vyhodnocení výrazu | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- expression evaluation, context
ms.assetid: a2fd3758-09bd-45ae-8ecc-2d276c0036ba
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e939a4fa5f4673e2f701206c96599c54bc0c3b51
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80738732"
---
# <a name="expression-evaluation-context"></a>Kontext vyhodnocení výrazu
V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění je **kontext vyhodnocení výrazu**:

- Představuje kontext pro vyhodnocení výrazu. Obecně platí, že kontext vyhodnocení odpovídá lexikálnímu oboru, ve kterém chcete vyhodnotit proměnné, parametry, funkce a metody. Například kontext vyhodnocení výrazu spojený s rámcem zásobníku poskytne kontext pro vyhodnocení místních proměnných, parametrů metody a členů třídy (Pokud je k dispozici).

- Existuje, pokud se program zastavil na zarážce. Samotný výraz je datová struktura představující analyzovaný výraz, který je připravený pro vazbu a vyhodnocení v rámci daného kontextu.

     Podrobněji jsou výrazy vytvořeny pomocí metody [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) . Při vyhodnocování výrazu vygeneruje tisknutelné řetězec obsahující název a typ proměnné nebo argumentu a jeho hodnotu. Tento řetězec se zobrazí v okno Kukátko nebo v okně místních hodnot v integrovaném vývojovém prostředí (IDE).

     V případě `BSTR` rozhraní a rozhraní [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) může ladicí stroj (de) vytvořit rozhraní [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) pomocí analýzy výrazu. `IDebugExpression2`Rozhraní de může získat hodnotu prostřednictvím synchronního nebo asynchronního vyhodnocení výrazu. Tato hodnota, společně s názvem a typem proměnné nebo argumentu, se pošle na IDE pro zobrazení.

## <a name="see-also"></a>Viz také
- [Rozhraní pro vyhodnocení výrazu](../../extensibility/debugger/reference/expression-evaluation-interfaces.md)
- [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md)
