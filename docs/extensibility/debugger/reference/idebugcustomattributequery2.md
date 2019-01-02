---
title: IDebugCustomAttributeQuery2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugCustomAttributeQuery2
helpviewer_keywords:
- IDebugCustomAttributeQuery interface
- IDebugCustomAttributeQuery2 interface
ms.assetid: 7cfa23e4-a05a-47a3-af6c-bd40c655014b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b5c71c8a8820a76eb0f3784aaf899f05f48a76e4
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53836371"
---
# <a name="idebugcustomattributequery2"></a>IDebugCustomAttributeQuery2
Určuje existenci vlastní atribut pro toto pole a pokud existuje, vrátí informace o atributu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugCustomAttributeQuery2 : IDebugCustomAttributeQuery  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Poskytovatel symbolů implementuje toto rozhraní na stejný objekt, který implementuje [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) za účelem podpory vlastních atributů.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Použití [QueryInterface](/cpp/atl/queryinterface) získat z tohoto rozhraní [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu **IDebugCustomAttributeQuery** rozhraní.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugcustomattributequery2-iscustomattributedefined.md)|Určuje, zda existuje vlastní atribut podle názvu.|  
|[GetCustomAttributeByName](../../../extensibility/debugger/reference/idebugcustomattributequery2-getcustomattributebyname.md)|Získá informace o atributu pro dané vlastní atribut.|  
  
 Kromě **IDebugCustomAttributeQuery** metody, `IDebugCustomAttributeQuery2` implementuje následující metodu:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[EnumCustomAttributes](../../../extensibility/debugger/reference/idebugcustomattributequery2-enumcustomattributes.md)|Získá enumerátor pro všechny vlastní atributy připojené k tomuto poli.|  
  
## <a name="remarks"></a>Poznámky  
 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md) metoda může vrátit enumerátor pro všechny vlastní atributy definované pro toto pole.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní poskytovatele symbolů](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)