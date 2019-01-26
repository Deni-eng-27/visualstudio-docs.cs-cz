---
title: marker_series – třída | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic::marker_series
helpviewer_keywords:
- Concurrency::diagnostic::marker_series class
ms.assetid: b8445ed0-c512-4f92-b6b4-3d05c044f939
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 13329ce649ac1947b335ee73d1408e94a5ff52e7
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2019
ms.locfileid: "55068889"
---
# <a name="markerseries-class"></a>marker_series – třída
Představuje kanál sériového portu události generované modulem jednoho zprostředkovatele.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
class marker_series;  
```  
  
## <a name="members"></a>Členové  
  
### <a name="public-constructors"></a>Veřejné konstruktory  
  
|Název|Popis|  
|----------|-----------------|  
|[marker_series::marker_series – konstruktor](../profiling/marker-series-marker-series-constructor.md)|Inicializuje novou instanci třídy `marker_series` třídy.|  
|[marker_series:: ~ marker_series – destruktor](../profiling/marker-series-tilde-marker-series-destructor.md)|Odstraní objekt marker_series – a uvolní všechny přidělené prostředky.|  
  
### <a name="public-methods"></a>Veřejné metody  
  
|Název|Popis|  
|----------|-----------------|  
|[marker_series::is_enabled – metoda](../profiling/marker-series-is-enabled-method.md)|Určuje, zda všechny relace má povoleno zprostředkovatele.|  
|[marker_series::write_alert – metoda](../profiling/marker-series-write-alert-method.md)|Zapíše upozornění do souboru trasování vizualizátoru souběžnosti.|  
|[marker_series::write_flag – metoda](../profiling/marker-series-write-flag-method.md)|Příznak, který zapisuje do souboru trasování vizualizátoru souběžnosti.|  
|[marker_series::write_message – metoda](../profiling/marker-series-write-message-method.md)|Zapíše zprávu do souboru trasování vizualizátoru souběžnosti.|  
  
## <a name="inheritance-hierarchy"></a>Hierarchie dědičnosti  
 `marker_series`  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** *cvmarkersobj.h*  
  
 **Namespace:** Concurrency::diagnostic  
  
## <a name="see-also"></a>Viz také:  
 [Diagnostic – obor názvů](../profiling/diagnostic-namespace.md)