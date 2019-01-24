---
title: IDebugModule2::ReloadSymbols_Deprecated | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugModule2::ReloadSymbols
helpviewer_keywords:
- IDebugModule2::ReloadSymbols method
ms.assetid: 0f9f0133-7d58-4cd9-a6ca-1141e095749d
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 2ce816e20e59d407f9b3cd84e3dffa703d84a324
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54789374"
---
# <a name="idebugmodule2reloadsymbolsdeprecated"></a>IDebugModule2::ReloadSymbols_Deprecated
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

ZASTARALÉ. NEPOUŽÍVEJTE. Znovu načte symboly pro tento modul.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT ReloadSymbols(   
   LPCOLESTR pszUrlToSymbols,  
   BSTR*     pbstrDebugMessage  
);  
```  
  
```csharp  
int ReloadSymbols(   
   string     pszUrlToSymbols,  
   out string pbstrDebugMessage  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszUrlToSymbols`  
 [in] Cesta k úložišti symbolů.  
  
 `pbstrDebugMessage`  
 [out] Vrátí informačních zpráv, jako je například stav nebo chybové zprávy, který se zobrazí napravo od názvu modulu v okně moduly.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Ladicí stroj by měla vždy vrátit `E_FAIL`.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda se už nepodporuje. Implementace [LoadSymbols](../../../extensibility/debugger/reference/idebugmodule3-loadsymbols.md) metoda místo.  
  
## <a name="see-also"></a>Viz také  
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)   
 [LoadSymbols](../../../extensibility/debugger/reference/idebugmodule3-loadsymbols.md)
