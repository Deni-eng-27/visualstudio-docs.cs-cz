---
title: 'IDebugSymbolProvider:: GetAddressesFromPosition | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugSymbolProvider::GetAddressesFromPosition
helpviewer_keywords:
- IDebugSymbolProvider::GetAddressesFromPosition method
ms.assetid: 1b0f02cb-8ace-4614-88f3-0e10239012b3
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 27767af36093e9424775074a55bafadac9a4480d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80719404"
---
# <a name="idebugsymbolprovidergetaddressesfromposition"></a>IDebugSymbolProvider::GetAddressesFromPosition
Tato metoda mapuje umístění dokumentu na pole adres ladění.

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

## <a name="parameters"></a>Parametry
`pDocPos`\
pro Pozice dokumentu.

`fStatmentOnly`\
pro Při hodnotě TRUE omezí adresy ladění na jediný příkaz.

`ppEnumBegAddresses`\
mimo Vrátí enumerátor pro počáteční adresy ladění přidružené k tomuto příkazu nebo řádku.

`ppEnumEndAddresses`\
mimo Vrátí enumerátor [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md) pro koncové adresy ladění přidružené k tomuto příkazu nebo řádku.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí. `S_OK` jinak vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Pozice dokumentu obvykle označuje rozsah zdrojových řádků. Tato metoda poskytuje počáteční a koncové adresy ladění přidružené k těmto řádkům. Některé jazyky umožňují příkazy, které jsou rozloženy na více řádků nebo řádky, které obsahují více než jeden příkaz. Tato metoda poskytuje příznak pro omezení adres ladění na jediný příkaz.

 Jeden příkaz může mít několik ladicích adres, jako v případě šablon.

## <a name="see-also"></a>Viz také
- [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)
- [GetAddressesFromContext](../../../extensibility/debugger/reference/idebugsymbolprovider-getaddressesfromcontext.md)
- [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)
