---
title: EX_DBGPROP_INFO_FLAGS | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- EX_DBGPROP_INFO_FLAGS
apilocation:
- scrobj.dll
helpviewer_keywords:
- EX_DBGPROP_INFO_FLAGS
ms.assetid: ee309dfe-9432-4dff-8756-7a8d677f9dcc
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3b40ef5c0ceb950873b47033d51555c3ba2fe27a
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094507"
---
# <a name="exdbgpropinfoflags"></a>EX_DBGPROP_INFO_FLAGS
Používá se k určení `ExtendedDebugPropertyInfo` pole.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
enum {  
   EX_DBGPROP_INFO_ID  =0x0100,  
   EX_DBGPROP_INFO_NTYPE  =0x0200,  
   EX_DBGPROP_INFO_NVALUE  =0x0400,  
   EX_DBGPROP_INFO_LOCKBYTES  =0x0800,  
   EX_DBGPROP_INFO_DEBUGEXTPROP  =0x1000  
};  
```  
  
## <a name="members"></a>Členové  
 EX_DBGPROP_INFO_ID  
 Identifikátor pro vlastnost inicializuje.  
  
 EX_DBGPROP_INFO_NTYPE  
 Inicializuje typu vlastnosti.  
  
 EX_DBGPROP_INFO_NVALUE  
 Inicializuje hodnoty vlastnosti.  
  
 EX_DBGPROP_INFO_LOCKBYTES  
 Inicializuje `plb` pole.  
  
 EX_DBGPROP_INFO_DEBUGEXTPROP  
 Inicializuje `pDebugExtProp` pole s údajem `IDebugExtendedProperty` rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Extendeddebugpropertyinfo – struktura](../../winscript/reference/extendeddebugpropertyinfo-structure.md)   
 [IDebugExtendedProperty – rozhraní](../../winscript/reference/idebugextendedproperty-interface.md)