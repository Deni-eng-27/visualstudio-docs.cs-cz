---
title: Cvreleaseprovider – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmarkers/CvReleaseProvider
helpviewer_keywords:
- CvReleaseProvider method
ms.assetid: 8d74379e-295d-452b-bd5f-0769df387d4f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 419cf6c30822a041397e73104974989881ac6e59
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53822473"
---
# <a name="cvreleaseprovider-function"></a>Cvreleaseprovider – funkce
Verze poskytovatele značek. Uvolňování poskytovatele značek neovlivní dříve vytvořené značky řady tohoto zprostředkovatele. Značky řady musí být verze samostatně voláním cvreleasemarkerseries –. Nepodařilo se uvolnit poskytovatele způsobí, že nevracení paměti.  
  
## <a name="syntax"></a>Syntaxe  
  
```C  
HRESULT CvReleaseProvider(  
   _In_ PCV_PROVIDER pProvider  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pProvider`  
 Kontext zprostředkovatele. Nemůže mít hodnotu NULL.  
  
## <a name="return-value"></a>Návratová hodnota  
 S_OK při poskytovatele se úspěšně uvolnily nebo kód chyby v případě, že existuje byly všechny chyby. Použití makra SUCCEEDED nebo FAILED zkontrolujte chybovou podmínku.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** *cvmarkers.h*  
  
## <a name="see-also"></a>Viz také:  
 [Referenční dokumentace knihoven jazyka C++](../profiling/cpp-library-reference.md)