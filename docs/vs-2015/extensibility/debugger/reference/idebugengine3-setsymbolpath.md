---
title: IDebugEngine3::SetSymbolPath | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugEngine3::SetSymbolPath
helpviewer_keywords:
- IDebugEngine3::SetSymbolPath
ms.assetid: 47b48f84-8a96-401f-84df-0baa8a96d26e
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 1ddb35af1d9f6541c85466a28bf9479ed4ce2fa4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54788479"
---
# <a name="idebugengine3setsymbolpath"></a>IDebugEngine3::SetSymbolPath
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nastaví cestu nebo cesty, které se vyhledávají symboly ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT SetSymbolPath (  
   LPOLESTR            szSymbolSearchPath,  
   LPOLESTR            szSymbolCachePath,  
   LOAD_SYMBOLS_FLAGS  Flags  
);  
```  
  
```csharp  
int SetSymbolPath(  
   string                    szSymbolSearchPath,   
   string                    szSymbolCachePath,   
   enum_LOAD_SYMBOLS_FLAGS   Flags  
);  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`szSymbolSearchPath`|[in] Řetězec obsahující cestu pro hledání symbolů nebo cesty. Podrobnosti najdete v části "Poznámky". Nemůže mít hodnotu null.|  
|`szSymbolCachePath`|[in] Řetězec obsahující místní cesta kde symboly můžete uložit do mezipaměti. Nemůže mít hodnotu null.|  
|`Flags`|[in] Nepoužívá se; vždy nastaven na hodnotu 0.|  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Řetězec `szSymbolSearchPath` seznam obsahuje jednu nebo několik cest oddělených středníky pro hledání symbolů. Tyto cesty může být místní cesta, cestu UNC – vizuální styl nebo adresu URL. Tyto cesty lze také kombinace různých typů. Pokud se cesta UNC (například \\\Symserver\Symbols), pak ladicí stroj musí zjistit, zda cesta je na server symbolů a by měl být schopný načíst symboly z tohoto serveru do mezipaměti je v cestě určené `szSymbolCachePath`.  
  
 Cesta k symbolu může také obsahovat jedno nebo více umístění mezipaměti. Mezipaměti jsou uvedeny jako první v pořadí podle priority, s nejvyšší prioritou mezipaměti a oddělené * symboly. Příklad:  
  
```  
\\symbols\symbols;\\someotherserver\symbols;c:\symbols\httpsymbols*http://msdl.microsoft.com  
```  
  
 [LoadSymbols](../../../extensibility/debugger/reference/idebugengine3-loadsymbols.md) metoda provádí vlastní operaci načtení symbolů.  
  
## <a name="see-also"></a>Viz také  
 [LoadSymbols](../../../extensibility/debugger/reference/idebugengine3-loadsymbols.md)   
 [IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)
