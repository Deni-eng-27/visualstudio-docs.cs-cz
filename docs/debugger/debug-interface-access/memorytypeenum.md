---
title: MemoryTypeEnum | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: MemoryTypeEnum enumeration
ms.assetid: 8778c047-edeb-4495-8f9f-3f8bbb297099
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: db6a66f8d496c73d05e05fd2f5398998c0a72484
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="memorytypeenum"></a>MemoryTypeEnum
Určuje typ paměti pro přístup.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
enum MemoryTypeEnum {  
   MemTypeCode,  
   MemTypeData,  
   MemTypeStack,  
   MemTypeAny = -1  
};  
```  
  
#### <a name="parameters"></a>Parametry  
 `MemTypeCode`  
 Přistupuje jenom kódu paměti.  
  
 `MemTypeData`  
 Data nebo zásobníku paměti přístupů.  
  
 `MemTypeStack`  
 Přistupuje jenom zásobníku paměti.  
  
 `MemTypeAny`  
 Přístup k jakýkoli druh paměti.  
  
## <a name="remarks"></a>Poznámky  
 Hodnoty v tento výčet jsou předávány [IDiaStackWalkHelper::readMemory](../../debugger/debug-interface-access/idiastackwalkhelper-readmemory.md) metoda omezení přístupu pro různé typy paměti.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: cvconst.h  
  
## <a name="see-also"></a>Viz také  
 [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaStackWalkHelper::readMemory](../../debugger/debug-interface-access/idiastackwalkhelper-readmemory.md)