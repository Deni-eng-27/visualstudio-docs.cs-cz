---
title: Funkce háku sestavy | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.hooks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- hooks, report
- _CrtDbgReport function
- debugger, report hook functions
- memory allocation, debug heap
- debugging [C++], hook functions
- _CrtSetReportHook function
- report hook functions
ms.assetid: 1854bca7-d7eb-4502-89bf-b1ee64cb50ef
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 093b7732f78f7257a2e58812ca2697496d65682f
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2018
ms.locfileid: "37056479"
---
# <a name="report-hook-functions"></a>Sestava funkcí háku
Funkce háku sestavy, nainstalovat pomocí [_crtsetreporthook –](/cpp/c-runtime-library/reference/crtsetreporthook), se nazývá pokaždé, když [_crtdbgreport –](/cpp/c-runtime-library/reference/crtdbgreport-crtdbgreportw) generuje sestavy ladění. Můžete použít, mimo jiné pro filtrování sestavy a zaměřit se na konkrétní typy přidělení. Funkce háku sestavy musí mít prototyp takto:  
  
```cpp
int YourReportHook(int nRptType, char *szMsg, int *retVal);  
```  
  
 Ukazatele, který můžete předat **_crtsetreporthook –** je typu **_crt_report_hook –**, jak jsou definovány v CRTDBG. V:  
  
```cpp
typedef int (__cdecl *_CRT_REPORT_HOOK)(int, char *, int *);  
```  
  
 Při volání funkce háku, běhové knihovny *nRptType* argument obsahuje kategorii sestavy (**_CRT_WARN**, **_CRT_ERROR**, nebo **_CRT _ASSERT**), *szMsg* obsahuje ukazatel na řetězec zprávy plně sestavený sestavy a *retVal* Určuje, zda `_CrtDbgReport` by měly pokračovat normální spuštění Po generování sestavy nebo spuštění ladicího programu. (A *retVal* hodnota nula pokračuje v provádění, hodnotu 1 spustí ladicí program.)  
  
 Pokud hák má na starosti dotyčném zpráva úplně, tak, aby další vykazování se nevyžaduje, by měla vrátit **TRUE**. Vrátí-li **FALSE**, `_CrtDbgReport` bude sestava zpráva normálně.  
  
## <a name="see-also"></a>Viz také  
 [Zápis funkce háku ladění](../debugger/debug-hook-function-writing.md)   
 [Ukázka crt_dbg2](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167)
