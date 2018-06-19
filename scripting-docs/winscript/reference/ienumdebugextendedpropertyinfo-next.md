---
title: IEnumDebugExtendedPropertyInfo::Next | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugExtendedPropertyInfo.Next
apilocation:
- scrobj.dll
helpviewer_keywords:
- IEnumDebugExtendedPropertyInfo::Next
ms.assetid: ac41c9a3-19d1-4596-8a87-01c10b131be3
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 343620e4539e9d095f2708ab46077ee0dafd1932
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24794547"
---
# <a name="ienumdebugextendedpropertyinfonext"></a>IEnumDebugExtendedPropertyInfo::Next
Načte zadaný počet`ExtendedDebugPropertyInfo` struktury v posloupnosti výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT Next (  
   ULONGcelt,  
   ExtendedDebugPropertyInfo *rgelt,  
   ULONG* pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `celt`  
 [v] Počet `ExtendedDebugPropertyInfo`struktury mají být načteny.  
  
 `rgelt`  
 [out] Pole `ExtendedDebugPropertyInfo` struktury načíst.  
  
 `pceltFetched`  
 [out] Počet `ExtendedDebugPropertyInfo` struktury, ve skutečnosti načíst.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrací platnou `HRESULT`, obvykle `S_OK`.  
  
## <a name="see-also"></a>Viz také  
 [Ienumdebugextendedpropertyinfo – rozhraní](../../winscript/reference/ienumdebugextendedpropertyinfo-interface.md)   
 [Extendeddebugpropertyinfo – struktura](../../winscript/reference/extendeddebugpropertyinfo-structure.md)