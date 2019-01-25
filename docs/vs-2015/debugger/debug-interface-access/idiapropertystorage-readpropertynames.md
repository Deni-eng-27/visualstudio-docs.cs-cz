---
title: IDiaPropertyStorage::ReadPropertyNames | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadPropertyNames
ms.assetid: f8bcab77-afca-4a8f-8710-697842f8a518
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: f3f6d3ac520a396b5207767a3fec0913c801c287
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54769885"
---
# <a name="idiapropertystoragereadpropertynames"></a>IDiaPropertyStorage::ReadPropertyNames
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Načte odpovídající názvů řetězce pro daný vlastnost identifikátory.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT ReadPropertyNames (  
   ULONG         cpropid,  
   PROPID const* rgpropid,  
   BSTR*         rglpwstrName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cpropid`  
 [in] Počet ID vlastnosti v `rgpropid`.  
  
 `rgpropid`  
 [in] Pole ID vlastnost, pro které chcete načíst názvy (`PROPID` je definována v WTypes.h jako `ULONG`).  
  
 `rglpwstrName`  
 [out v] Pole názvy vlastností pro zadanou vlastnost ID. Pole musí být předběžně přidělit k uložení požadovaného počtu názvy vlastností a musí být do něj vejít aspoň `cpropid``BSTR` řetězce.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Názvy vráceného vlastností, které musí být uvolněna (voláním `SysFreeString` funkce) když jsou už nepotřebujete.  
  
## <a name="see-also"></a>Viz také  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)
