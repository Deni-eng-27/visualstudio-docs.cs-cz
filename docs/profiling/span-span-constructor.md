---
title: span::span – konstruktor | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic::span::span
helpviewer_keywords:
- Concurrency::diagnostic::span constructor
ms.assetid: 8b5578aa-5e5c-4ac7-87c7-ce87c4246e2c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f761e87c1658c11bfdfd93a4f4e22299d88575a8
ms.sourcegitcommit: cea6187005f8a0cdf44e866a1534a4cf5356208c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/27/2019
ms.locfileid: "56953298"
---
# <a name="spanspan-constructor"></a>span::span – konstruktor

Inicializuje novou instanci třídy `span` třídy.

## <a name="syntax"></a>Syntaxe

```cpp
span(
   const marker_series& _Series,
   _In_ LPCTSTR _Format,
   ...
);
span(
   const marker_series& _Series,
   marker_importance _Importance,
   _In_ LPCTSTR _Format,
   ...
);
span(
   const marker_series& _Series,
   int _Category,
   _In_ LPCTSTR _Format,
   ...
);
span(
   const marker_series& _Series,
   marker_importance _Importance,
   int _Category,
   _In_ LPCTSTR _Format,
   ...
);
```

#### <a name="parameters"></a>Parametry

`_Series` Platné značky řady kontextu.

`_Format` Složený řetězec formátu, který obsahuje textu smíšeného s nula nebo více položek formátu, který odpovídá objektům v seznamu argumentů.

`_Importance` Úroveň důležitosti.

`_Category` Kategorie.

## <a name="requirements"></a>Požadavky

**Záhlaví:** *cvmarkersobj.h*

**Namespace:** Concurrency::diagnostic

## <a name="see-also"></a>Viz také:

- [span třídy](../profiling/span-class.md)