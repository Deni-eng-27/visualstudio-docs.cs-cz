---
title: Idiastackwalkframe::put_registervalue – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkFrame::put_registerValue method
ms.assetid: 2d8b79b6-7240-43fe-b24e-e4ff3e2c15b0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 440c7d19382b813b3f34451d7c177c6e8b57f16f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62831844"
---
# <a name="idiastackwalkframeputregistervalue"></a>IDiaStackWalkFrame::put_registerValue
Nastaví hodnotu registru.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT put_registerValue ( 
   DWORD     index,
   ULONGLONG NewVal
);
```

#### <a name="parameters"></a>Parametry
 `index`

[in] Hodnota z [cv_hreg_e – výčet](../../debugger/debug-interface-access/cv-hreg-e.md) výčet určující k zápisu do registru.

 `NewVal`

[in] Nové hodnoty registru.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)
- [CV_HREG_e – výčet](../../debugger/debug-interface-access/cv-hreg-e.md)