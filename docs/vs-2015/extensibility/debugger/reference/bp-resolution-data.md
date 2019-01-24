---
title: BP_RESOLUTION_DATA | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- BP_RESOLUTION_DATA
helpviewer_keywords:
- BP_RESOLUTION_DATA structure
ms.assetid: 9e0b9000-6a84-47b9-b07a-367a75764389
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e4e266d1b5d0976ebc910a8228a3724f80001b5a
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54752560"
---
# <a name="bpresolutiondata"></a>BP_RESOLUTION_DATA
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Popisuje výsledek vazby datové zarážky.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
typedef struct _BP_RESOLUTION_DATA {   
   BSTR              bstrDataExpr;  
   BSTR              bstrFunc;  
   BSTR              bstrImage;  
   BP_RES_DATA_FLAGS dwFlags;  
} BP_RESOLUTION_DATA;  
```  
  
```csharp  
public struct BP_RESOLUTION_DATA {   
   public string bstrDataExpr;  
   public string bstrFunc;  
   public string bstrImage;  
   public uint   dwFlags;  
};  
```  
  
## <a name="members"></a>Členové  
 `bstrDataExpr`  
 Výraz data, která byla vázána.  
  
 `bstrFunc`  
 Název funkce datová zarážka má vázán v (pokud existuje).  
  
 `bstrImage`  
 Název modulu (například MyModule.dll), která má datová zarážka vázána v.  
  
 `dwFlags`  
 Hodnota z [BP_RES_DATA_FLAGS](../../../extensibility/debugger/reference/bp-res-data-flags.md) výčet popisující, jak je implementovaná datová zarážka.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je členem skupiny [BP_RESOLUTION_LOCATION](../../../extensibility/debugger/reference/bp-resolution-location.md) strukturou, který je v zapnout člen [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) vrácené struktury [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)metody.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_RESOLUTION_LOCATION](../../../extensibility/debugger/reference/bp-resolution-location.md)   
 [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)   
 [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)
