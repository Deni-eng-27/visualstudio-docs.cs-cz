---
title: "Getautoinsertextensions – metoda | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
ms.assetid: 78388cce-7aae-4163-8db5-ce00d0a0c331
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1d222f7b6751381ceb4ebdb27bb6a6bf223616df
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="getautoinsertextensions-method"></a>GetAutoInsertExtensions – metoda
  Získá informace o aplikacích pro Office, které se mají automaticky vložit během ladění.  
  
 Tato metoda je vyhrazena pro budoucí použití.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetAutoInsertExtensions(  
    [out, retval] SAFEARRAY(BSTR)* psaExtensionNames  
);  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Popis|  
|---------------|-----------------|  
|*psaExtensionNames*|Názvy rozšíření aplikace pro Office.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Hodnota HRESULT, která určuje, zda metoda byla úspěšně dokončena.  
  
## <a name="remarks"></a>Poznámky  
 Každá aplikace pro Office má být vložen se vrátí jako název rozšíření aplikace Office, který odpovídá hodnotě pod HKEY_CURRENT_USER\Software\Microsoft\Office\WEF\Developer. Hostitel musí vyhledat tyto hodnoty v registru a automaticky vložit rozšíření.  
  
  