---
title: IDispatchEx::GetNameSpaceParent | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispatchEx.GetNameSpaceParent
apilocation:
- scrobj.dll
helpviewer_keywords:
- GetNameSpaceParent method
ms.assetid: 0b077d39-2fd6-4390-8cd5-128d9b8dc90c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1abe2a880e12d6a4a3c1dfda32d30722525858f5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63000820"
---
# <a name="idispatchexgetnamespaceparent"></a>IDispatchEx::GetNameSpaceParent
Načte rozhraní pro obor názvů nadřazeného objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetNameSpaceParent(  
   IUnknown **ppunk  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppunk`  
 Adresa `IUnknown` ukazatel rozhraní, která bude přijímat nadřazený obor názvů rozhraní.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí `S_OK` v případě úspěchu nebo jinak kód chyby definované OLE.  
  
## <a name="see-also"></a>Viz také  
 [IDispatchEx – rozhraní](../../winscript/reference/idispatchex-interface.md)