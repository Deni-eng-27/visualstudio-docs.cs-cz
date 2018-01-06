---
title: IDebugSymbolProvider::GetAddressesFromContext | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugSymbolProvider::GetAddressesFromContext
helpviewer_keywords: IDebugSymbolProvider::GetAddressesFromContext method
ms.assetid: a3124883-a255-4543-a5ec-e1c7a97beb69
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3d8776ee9e00aebbe3c33021c160c8f7f3677743
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugsymbolprovidergetaddressesfromcontext"></a>IDebugSymbolProvider::GetAddressesFromContext
Tato metoda mapuje kontextu dokumentu do pole adres ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetAddressesFromContext(   
   IDebugDocumentContext2* pDocContext,  
   BOOL                    fStatmentOnly,  
   IEnumDebugAddresses**   ppEnumBegAddresses,  
   IEnumDebugAddresses**   ppEnumEndAddresses  
);  
```  
  
```csharp  
int GetAddressesFromContext(  
   IDebugDocumentContext2  pDocContext,  
   bool                    fStatmentOnly,  
   out IEnumDebugAddresses ppEnumBegAddresses,  
   out IEnumDebugAddresses ppEnumEndAddresses  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pDocContext`  
 [v] Kontext dokumentu.  
  
 `fStatmentOnly`  
 [v] V případě hodnoty TRUE omezuje ladění adresy, které mají jeden příkaz.  
  
 `ppEnumBegAddresses`  
 [out] Vrátí enumerátor pro počáteční ladění adresy přidružené k tomuto prohlášení nebo řádku.  
  
 `ppEnumEndAddresses`  
 [out] Vrátí [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md) enumerátor pro koncovou ladění adresy přidružené k tomuto prohlášení nebo řádku.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Kontext dokumentu obvykle udává určitý rozsah řádků zdroje. Tato metoda poskytuje počáteční a koncové adresy ladění přidružené tyto řádky. Některé jazyky povolit příkazy, které jsou rozmístěny v několika řádky a řádky, které obsahuje více než jeden výraz. Tato metoda poskytuje příznak omezit ladění adresy, které mají jeden příkaz.  
  
 Je možné pro jediný příkaz tak, aby měl více adres ladění, jako v případě šablon.  
  
## <a name="see-also"></a>Viz také  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [GetAddressesFromPosition](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromposition.md)   
 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)