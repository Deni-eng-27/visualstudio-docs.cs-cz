---
title: "Idiadatasource::get_lasterror – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaDataSource::get_lastError method
ms.assetid: cf08850b-8b75-4e8c-90bd-bd0214756f99
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 349477bed67450e897ec60a00635fb65442eb1ba
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiadatasourcegetlasterror"></a>IDiaDataSource::get_lastError
Načte název souboru pro poslední chyba zatížení.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_lastError (  
   BSTR* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pRetVal  
 [out] Vrátí řetězec, který obsahuje název souboru PDB spojený s poslední chyba zatížení.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí poslední kód chyby způsobené operace načtení. Vrátí `E_INVALIDARG` Pokud `pRetVal` parametr `NULL`.  
  
## <a name="example"></a>Příklad  
  
```C++  
BSTR    fileName;  
HRESULT errorCode = pSource->get_lastError( &fileName );  
```  
  
## <a name="see-also"></a>Viz také  
 [Idiadatasource –](../../debugger/debug-interface-access/idiadatasource.md)