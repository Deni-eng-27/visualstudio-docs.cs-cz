---
title: span::span – konstruktor | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic::span::span
helpviewer_keywords:
- Concurrency::diagnostic::span constructor
ms.assetid: 8b5578aa-5e5c-4ac7-87c7-ce87c4246e2c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: afd383dfd03a1e4e0a2ca9c377ce372d1586c738
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/11/2018
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
 `_Series`  
 Kontext řady platný značky.  
  
 `_Format`  
 Složený formátovací řetězec, který obsahuje text smíšeného s nula nebo více položek formátu, odpovídajících objektů v seznamu argumentů.  
  
 `_Importance`  
 Úroveň význam.  
  
 `_Category`  
 Kategorie.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** cvmarkersobj.h  
  
 **Namespace:** Concurrency::Diagnostic –
 
 ## <a name="see-also"></a>Viz také
 [span – třída](../profiling/span-class.md)