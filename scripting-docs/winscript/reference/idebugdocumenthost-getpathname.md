---
title: IDebugDocumentHost::GetPathName | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugDocumentHost.GetPathName
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugDocumentHost::GetPathName
ms.assetid: 8abe2a86-e467-4ac9-8ccb-8761141bfa0d
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5c33844ade2367ffeb7690306a5febbabde2f016
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54096028"
---
# <a name="idebugdocumenthostgetpathname"></a>IDebugDocumentHost::GetPathName
Vrátí úplnou cestu a název zdrojového souboru dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetPathName(  
   BSTR*  pbstrLongName,  
   BOOL*  pfIsOriginalFile  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pbstrLongName`  
 [out] Řetězec obsahující dlouhý název.  
  
 `pfIsOriginalFile`  
 [out] Příznak, který je hodnota true v případě `pbstrLongName` odkazuje na původní soubor dokumentu, false v opačném případě.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`E_FAIL`|Žádný zdrojový soubor můžou vytvořit nebo určit.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vrátí úplnou cestu a název zdrojového souboru dokumentu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentHost – rozhraní](../../winscript/reference/idebugdocumenthost-interface.md)