---
title: POPDIRLISTFUNC | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: POPLISTFUNC
helpviewer_keywords: POPDIRLISTFUNC callback function
ms.assetid: 0ee90fd2-5467-4154-ab4c-7eb02ac3a14c
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 8503afb26ec8dc244db39dff5bddcc6d3b733896
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="popdirlistfunc"></a>POPDIRLISTFUNC
Toto je funkce zpětného volání, zadané [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md) funkce aktualizujte kolekci adresářů a (volitelně) názvy souborů a zjistěte, které jsou v části Správa zdrojového kódu.  
  
 `POPDIRLISTFUNC` Zpětného volání by měla být volána pouze pro tyto adresáře a názvy souborů (v seznamu na `SccPopulateDirList` funkce), které jsou ve skutečnosti ve správě zdrojového kódu.  
  
## <a name="signature"></a>Podpis  
  
```cpp  
typedef BOOL (*POPDIRLISTFUNC)(  
   LPVOID pvCallerData,  
   BOOL bFolder,  
   LPCSTR lpDirectoryOrFileName  
);  
```  
  
## <a name="parameters"></a>Parametry  
 pvCallerData  
 [v] Hodnota uživatele na [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md).  
  
 bFolder  
 [v] `TRUE` Pokud název v `lpDirectoryOrFileName` je adresář; v opačném případě název je název souboru.  
  
 lpDirectoryOrFileName  
 [v] Úplná místní cesta k názvu adresář nebo soubor, který je ve správě zdrojového kódu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Prostředí IDE vrátí odpovídající chybový kód:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Pokračujte ve zpracování.|  
|SCC_I_OPERATIONCANCELED|Zastavte zpracování.|  
|SCC_E_xxx|Všechny příslušné zdrojové řízení chyby by se měla zastavit zpracování.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud `fOptions` parametr `SccPopulateDirList` funkce obsahuje `SCC_PDL_INCLUDEFILES` příznak, bude pravděpodobně obsahovat seznamu názvů souborů, jakož i názvy adresářů.  
  
## <a name="see-also"></a>Viz také  
 [Funkce zpětného volání, které implementují rozhraní IDE](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)   
 [Chybové kódy](../extensibility/error-codes.md)