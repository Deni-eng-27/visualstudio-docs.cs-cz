---
title: IDebugDocumentHelper::SetShortName | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHelper.SetShortName
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugDocumentHelper::SetShortName
ms.assetid: 811a444b-0ea4-4374-9d4c-4f7713bdd1ff
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 84cab7872272b08e12c532e6c07b4afb741a53c3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62963543"
---
# <a name="idebugdocumenthelpersetshortname"></a>IDebugDocumentHelper::SetShortName
Nastaví krátký název dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT SetShortName(  
   LPCOLESTR  pszShortName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszShortName`  
 [in] Řetězec zakončený hodnotou null obsahující krátký název dokumentu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda nastaví nový krátký název dokumentu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentHelper – rozhraní](../../winscript/reference/idebugdocumenthelper-interface.md)