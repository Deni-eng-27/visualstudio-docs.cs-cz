---
title: ResumeTracking | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
apiname:
- ResumeTracking
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- ResumeTracking
ms.assetid: d637e019-7c50-4b0a-812e-bc822001e697
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e241af310821463f60f323b9fd20099fad44a3ba
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/22/2018
ms.locfileid: "36326277"
---
# <a name="resumetracking"></a>ResumeTracking
Obnoví sledování v aktuálním kontextu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT WINAPI ResumeTracking();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 **HRESULT** s **úspěšné** nastaven bit, pokud byla obnovena sledování. **E_FAIL** je vrácena, pokud sledování nemůže být obnoven, protože kontext nebyl k dispozici.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** FileTracker.h  
  
## <a name="see-also"></a>Viz také  
 [SuspendTracking](../msbuild/suspendtracking.md)