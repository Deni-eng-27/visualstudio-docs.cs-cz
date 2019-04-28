---
title: CaptureCurrentFrame | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 4509311d-6fe2-4b65-9b4a-ff0522585d6a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ec67013b41a5ec8876866044355534c42bfe2ee0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62848705"
---
# <a name="capturecurrentframe"></a>CaptureCurrentFrame
Zaznamená zbytek aktuálního snímku do souboru protokolu grafiky.

## <a name="syntax"></a>Syntaxe

```C++
void CaptureCurrentFrame();
```

## <a name="remarks"></a>Poznámky
 Pokud právě probíhá jiné sběrného – například zachycení, kterou zahájil `BeginCapture` funkce – zachycení je dokončena a zaznamenána do protokolu grafiky jako odlišné rámce. Okamžitě diagnostiky grafiky později, začne zachytávání zbytek aktuální rámec, která je také zaznamenána jako odlišné rámce. Konec aktuálního snímku je označen volání k dispozici.

 K zachycení snímku, musíte připravit aplikaci tak, aby zachycení a zaznamenání informací grafiky – to znamená, musí zavoláte [Init](init.md) prostřednictvím instance `VsgDbg` třídy před voláním `CaptureCurrentFrame`.

## <a name="see-also"></a>Viz také
- [Init](init.md)
- [BeginCapture](begincapture.md)