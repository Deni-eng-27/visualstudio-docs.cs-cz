---
title: "marker_series::marker_series – konstruktor | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: cvmarkersobj/Concurrency::diagnostic::marker_series::marker_series
helpviewer_keywords: Concurrency::diagnostic::marker_series constructor
ms.assetid: 042c7d23-f1d8-4e09-9e76-a21c30243790
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 83922b913e810042bef82eb0b81a0e42f8d3bbb1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="markerseriesmarkerseries-constructor"></a>marker_series::marker_series – konstruktor
Inicializuje novou instanci třídy `marker_series` třídy.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
marker_series();  
marker_series(  
   _In_ LPCTSTR _SeriesName  
);  
marker_series(  
   _In_ const GUID* _ProviderGuid  
);  
marker_series(  
   _In_ const GUID* _ProviderGuid,  
   _In_ LPCTSTR _SeriesName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `_SeriesName`  
 Název řady, chcete-li vytvořit.  
  
 `_ProviderGuid`  
 Identifikátor GUID řady zprostředkovatele.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** cvmarkersobj.h  
  
 **Namespace:** Concurrency::Diagnostic –  
  
## <a name="see-also"></a>Viz také  
 [marker_series – třída](../profiling/marker-series-class.md)