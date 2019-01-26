---
title: IDebugSettingsCallback2::EnumEEs | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugSettingsCallback2::EnumEEs
ms.assetid: 9f884c49-426f-461b-b547-9d909486e73f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7d8872902f2b240e21a02e000f2aae815ae3d854
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55030714"
---
# <a name="idebugsettingscallback2enumees"></a>IDebugSettingsCallback2::EnumEEs
Vytvoří výčet vyhodnocení výrazu dostupné zadané identifikátory jazyka a dodavatele.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EnumEEs(  
   DWORD  celtBuffer,  
   GUID*  rgguidLang,  
   GUID*  rgguidVendor,  
   DWORD* pceltEEs  
);  
```  
  
```csharp  
public int EnumEEs(  
   uint       celtBuffer,  
   ref Guid   rgguidLang,  
   ref Guid   rgguidVendor,  
   ref uint[] pceltEEs  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `celtBuffer`  
 [in] Počet prvků v objektu `pceltEEs` vyrovnávací paměti.  
  
 `rgguidLang`  
 [out v] Jedinečný identifikátor pro programovací jazyk.  
  
 `rgguidVendor`  
 [out v] Jedinečný identifikátor pro dodavatele.  
  
 `pceltEEs`  
 [out v] Pole vyhodnocovače výrazů.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)