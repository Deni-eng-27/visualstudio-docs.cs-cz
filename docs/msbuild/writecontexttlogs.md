---
title: WriteContextTLogs | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
apiname:
- WriteContextTLogs
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- WriteContextTLogs
ms.assetid: ffc6c7be-3f22-4624-9ffc-0122fe72b6ec
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 722d8c42786a7aaa2daae293b96f7926abcc90ca
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56719831"
---
# <a name="writecontexttlogs"></a>WriteContextTLogs
Zapíše soubory protokolů pro aktuální kontext.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT WINAPI WriteContextTLogs(LPCTSTR intermediateDirectory, LPCTSTR tlogRootName);
```

#### <a name="parameters"></a>Parametry
[in] `intermediateDirectory`

 Adresáře, ve kterém k uložení protokolu sledování.

[in] `tlogRootName`

 Název kořenového názvu souboru protokolu.

## <a name="return-value"></a>Návratová hodnota
 **HRESULT** s **SUCCEEDED** sadu bitů, pokud byl vytvořen kontext sledování.

## <a name="requirements"></a>Požadavky
 **Záhlaví:** *FileTracker.h*

## <a name="see-also"></a>Viz také:
- [WriteAllTLogs](../msbuild/writealltlogs.md)