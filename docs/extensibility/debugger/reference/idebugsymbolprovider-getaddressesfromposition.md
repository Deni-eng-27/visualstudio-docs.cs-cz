---
title: IDebugSymbolProvider::GetAddressesFromPosition | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugSymbolProvider::GetAddressesFromPosition
helpviewer_keywords:
- IDebugSymbolProvider::GetAddressesFromPosition method
ms.assetid: 1b0f02cb-8ace-4614-88f3-0e10239012b3
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 44da9f9b7585e7523a244f84e8407aa4148bef2f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53898918"
---
# <a name="idebugsymbolprovidergetaddressesfromposition"></a>IDebugSymbolProvider::GetAddressesFromPosition
Tato metoda mapuje umístění dokumentu do pole adresy ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetAddressesFromPosition(   
   IDebugDocumentPosition2* pDocPos,  
   BOOL                     fStatmentOnly,  
   IEnumDebugAddresses**    ppEnumBegAddresses,  
   IEnumDebugAddresses**    ppEnumEndAddresses  
);  
```  
  
```csharp  
int GetAddressesFromPosition(   
   IDebugDocumentPosition2  pDocPos,  
   bool                     fStatmentOnly,  
   out IEnumDebugAddresses  ppEnumBegAddresses,  
   out IEnumDebugAddresses  ppEnumEndAddresses  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pDocPos`  
 [in] Pozice dokumentu.  
  
 `fStatmentOnly`  
 [in] Pokud je hodnota TRUE, omezí ladění adresy, které mají jeden příkaz.  
  
 `ppEnumBegAddresses`  
 [out] Vrátí enumerátor pro počáteční ladění adresy přidružené k tomuto prohlášení nebo řádku.  
  
 `ppEnumEndAddresses`  
 [out] Vrátí [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md) enumerátor pro koncové adresy ladění přidružené k tomuto prohlášení nebo řádku.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pozice dokumentu obvykle udává určitý rozsah řádků zdroje. Tato metoda poskytuje počáteční a koncovou adresu ladění přidružené tyto řádky. Některé jazyky povolit příkazy, které zahrnují více řádků nebo řádky, které obsahuje více než jeden výraz. Tato metoda poskytuje příznak, který chcete omezit adresy ladění, které mají jeden příkaz.  
  
 Je možné mít víc adres ladění, jako v případě šablon jeden příkaz.  
  
## <a name="see-also"></a>Viz také  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [GetAddressesFromContext](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromcontext.md)   
 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)