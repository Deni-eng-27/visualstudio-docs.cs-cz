---
title: OPTNAMECHANGEPFN | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OPTNAMECHANGEPFN
helpviewer_keywords: OPTNAMECHANGEPFN callback function
ms.assetid: 147303f3-c7f1-438a-81b7-db891ea3d076
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 666174c4f0f54679907bd239a81c5c369dc09a3d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="optnamechangepfn"></a>OPTNAMECHANGEPFN
Toto je funkce zpětného volání, zadaný ve volání [SccSetOption](../extensibility/sccsetoption-function.md) (pomocí možnosti `SCC_OPT_NAMECHANGEPFN`) a slouží ke komunikaci název změny provedené zdrojového kódu modulu plug-in zpět k prostředí IDE.  
  
## <a name="signature"></a>Podpis  
  
```cpp  
typedef void (*OPTNAMECHANGEPFN)(  
   LPVOID pvCallerData,  
   LPCSTR pszOldName,  
   LPCSTR pszNewName  
);  
```  
  
## <a name="parameters"></a>Parametry  
 pvCallerData  
 [v] Uživatel hodnota zadaná v předchozí volání [SccSetOption](../extensibility/sccsetoption-function.md) (pomocí možnosti `SCC_OPT_USERDATA`).  
  
 pszOldName  
 [v] Původní název souboru.  
  
 pszNewName  
 [v] Název souboru byl přejmenován na.  
  
## <a name="return-value"></a>Návratová hodnota  
 Žádné  
  
## <a name="remarks"></a>Poznámky  
 Pokud je soubor přejmenovat během operace řízení zdroje, modul plug-in správy zdroje uvědomí IDE o změnu názvu prostřednictvím této zpětného volání.  
  
 Pokud IDE nepodporuje tento zpětného volání, nebude volání [SccSetOption](../extensibility/sccsetoption-function.md) k jeho zadání. Pokud modul plug-in nepodporuje tento zpětného volání, vrátí `SCC_E_OPNOTSUPPORTED` z `SccSetOption` fungovat, pokud rozhraní IDE, pokusí se nastavit zpětné volání.  
  
## <a name="see-also"></a>Viz také  
 [Funkce zpětného volání, které implementují rozhraní IDE](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [SccSetOption](../extensibility/sccsetoption-function.md)