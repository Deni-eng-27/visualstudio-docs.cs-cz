---
title: Iactivescriptprofilercontrol5 – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 7fd0ce34-6ae3-428f-ba90-3e86a8a98ed0
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dacca8e8bf161b6f3a84dc216596673d5df8258c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62992904"
---
# <a name="iactivescriptprofilercontrol5-interface"></a>IActiveScriptProfilerControl5 – rozhraní
Poskytuje metodu, jak vytvořit výčet objektů haldy GC spojených se skriptovacím modulem.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
interface IActiveScriptProfilerControl5 : IActiveScriptProfilerControl4  
```  
  
## <a name="methods"></a>Metody  
 [IActiveScriptProfilerControl5::EnumHeap2 – metoda](../../winscript/reference/iactivescriptprofilercontrol5-enumheap2-method.md)  
 Vrátí rozhraní ([iactivescriptprofilerheapenum – rozhraní](../../winscript/reference/iactivescriptprofilerheapenum-interface.md)), který lze použít k iteraci objektů haldy GC v rámci přidruženého skriptovacího modulu.