---
title: 'IDiaFrameData:: get_functionParent | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_functionParent method
ms.assetid: f00b9ab1-d4da-4818-973a-58f8f0e66769
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 809de8589302ddc35a14e2ea0663248a163176e6
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2019
ms.locfileid: "72743627"
---
# <a name="idiaframedataget_functionparent"></a>IDiaFrameData::get_functionParent
Načte rozhraní rámce dat pro ohraničující funkci.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_functionParent ( 
   IDiaFrameData** pRetVal
);
```

#### <a name="parameters"></a>Parametry
 `pRetVal`

mimo Vrátí objekt [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md) pro ohraničující funkci.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také:
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)