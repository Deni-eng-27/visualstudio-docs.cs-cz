---
title: DataKind | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DataKind enumeration
ms.assetid: b64be708-22d6-4360-99e7-8f4e6b196de7
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c3de9ef6128c3cd5ca6eae80a257b3dc2982cd0f
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="datakind"></a>DataKind
Určuje konkrétní rozsah datové hodnoty.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
enum DataKind {   
   DataIsUnknown,  
   DataIsLocal,  
   DataIsStaticLocal,  
   DataIsParam,  
   DataIsObjectPtr,  
   DataIsFileStatic,  
   DataIsGlobal,  
   DataIsMember,  
   DataIsStaticMember,  
   DataIsConstant  
};  
```  
  
## <a name="elements"></a>Elementy  
 DataIsUnknown  
 Datový symbol nelze určit.  
  
 DataIsLocal  
 Položka dat je místní proměnné.  
  
 DataIsStaticLocal  
 Položka dat je statický místní proměnné.  
  
 DataIsParam  
 Položka dat je formální parametr.  
  
 DataIsObjectPtr  
 Datová položka je objekt ukazatel (`this`).  
  
 DataIsFileStatic  
 Položka dat je proměnné s rozsahem souboru.  
  
 DataIsGlobal  
 Položka dat je globální proměnné.  
  
 DataIsMember  
 Položka dat je proměnná člen objektu.  
  
 DataIsStaticMember  
 Položka dat je proměnné statické třídy.  
  
 DataIsConstant  
 Položka dat je konstantní hodnotu.  
  
## <a name="remarks"></a>Poznámky  
 Jsou vrácené hodnoty v tento výčet [idiasymbol::get_datakind –](../../debugger/debug-interface-access/idiasymbol-get-datakind.md) metoda.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: cvconst.h  
  
## <a name="see-also"></a>Viz také  
 [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_dataKind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)