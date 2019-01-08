---
title: Profiler_property_type_substring_info – struktura | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3845c872-4302-47b6-8912-7b2d7a3b3357
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
ms.openlocfilehash: 5f873cdf2ebd394e48c1513135f1acdcd700c283
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54089970"
---
# <a name="profilerpropertytypesubstringinfo-structure"></a>Profiler_property_type_substring_info – struktura
Představuje informace o typu podřetězce používají v relaci. Použít v [profiler_heap_object_relationship – struktura](../../winscript/reference/profiler-heap-object-relationship-structure.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef struct _PROFILER_PROPERTY_TYPE_SUBSTRING_INFO {    UINT length;    LPCWSTR value; } PROFILER_PROPERTY_TYPE_SUBSTRING_INFO;  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Typ|Popis|  
|------------|----------|-----------------|  
|length|UINT|Objekt je UINT.|  
|value|LPCWSTR|Objekt je LPCWSTR.|