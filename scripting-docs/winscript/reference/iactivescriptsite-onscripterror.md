---
title: IActiveScriptSite::OnScriptError | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSite.OnScriptError
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSite_OnScriptError
ms.assetid: 5c9c85cc-21ad-4232-be83-a24cc7570108
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d76aa46cbbcdab9a3c5c7b561b91ee58cfcac4ac
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58147615"
---
# <a name="iactivescriptsiteonscripterror"></a>IActiveScriptSite::OnScriptError
Informuje o hostiteli, provádění došlo k chybě při spuštění skriptu modulu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT OnScriptError(  
    IActiveScriptError *pase  // address of error interface  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pase`  
 [in] Adresa objektu chyba [iactivescripterror –](../../winscript/reference/iactivescripterror.md) rozhraní. Hostitel může pomocí tohoto rozhraní k získání informací o chybě spuštění.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí `S_OK` Pokud chyba byla zpracována správně nebo OLE definované jinak kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)