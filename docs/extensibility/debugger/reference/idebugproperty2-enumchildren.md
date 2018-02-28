---
title: IDebugProperty2::EnumChildren | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProperty2::EnumChildren
helpviewer_keywords:
- IDebugProperty2::EnumChildren
ms.assetid: cf79f666-65d1-417c-af7c-9271bac9a267
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 8bd006cd2391acde9743d660b7cf154098e286c7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugproperty2enumchildren"></a>IDebugProperty2::EnumChildren
Načte seznam podřízených vlastnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EnumChildren (   
   DEBUGPROP_INFO_FLAGS      dwFields,  
   DWORD                     dwRadix,  
   REFGUID                   guidFilter,  
   DBG_ATTRIB_FLAGS          dwAttribFilter,  
   LPCOLESTR                 pszNameFilter,  
   DWORD                     dwTimeout,  
   IEnumDebugPropertyInfo2** ppEnum  
);  
```  
  
```csharp  
int EnumChildren (   
   enum_DEBUGPROP_INFO_FLAGS   dwFields,  
   uint                        dwRadix,  
   ref Guid                    guidFilter,  
   uint                        dwAttribFilter,  
   string                      pszNameFilter,  
   uint                        dwTimeout,  
   out IEnumDebugPropertyInfo2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwFields`  
 [v] Kombinace příznaků z [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md) výčet, který určuje pole, která výčtové [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktury mají být vyplněna.  
  
 `dwRadix`  
 [v] Určuje základ – který se má použít při formátování všechny číselné informace.  
  
 `guidFilter`  
 [v] Identifikátor GUID filtru použít s `dwAttribFilter` a `pszNameFilter` parametry vybrat, kterou `DEBUG_PROPERTY_INFO` podřízené objekty se mají vytvořit její výčet. Například `guidFilterLocals` filtry pro místní proměnné.  
  
 `dwAttribFilter`  
 [v] Kombinace příznaků z [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md) výčet, který určuje, jaký typ objektů, které chcete vytvořit výčet, například `DBG_ATTRIB_METHOD` pro všechny metody, které může být podřízené této vlastnosti. V kombinaci s `guidFilter` a `pszNameFilter` parametry.  
  
 `pszNameFilter`  
 [v] Název filtru použít s `guidFilter` a `dwAttribFilter` parametry vybrat, kterou `DEBUG_PROPERTY_INFO` podřízené objekty se mají vytvořit její výčet. Příklad nastavení tohoto parametru na "MyX" filtry pro všechny podřízené objekty s názvem "MyX."  
  
 `dwTimeout`  
 [v] Určuje maximální dobu v milisekundách pro čekání před návratem od této metody. Použití `INFINITE` čekání po neomezenou dobu.  
  
 `ppEnum`  
 [out] Vrátí [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) objekt obsahující seznam vlastností podřízené.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md)   
 [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md)   
 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)