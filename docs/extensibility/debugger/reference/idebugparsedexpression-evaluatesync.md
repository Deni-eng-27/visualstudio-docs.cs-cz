---
title: IDebugParsedExpression::EvaluateSync | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugParsedExpression::EvaluateSync
helpviewer_keywords:
- IDebugParsedExpression::EvaluateSync method
ms.assetid: 0ea04cfa-de87-4b6c-897e-4572c1a28942
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ea659b847149a6abb2c3a5ba7cc947a59c7ae41c
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56709639"
---
# <a name="idebugparsedexpressionevaluatesync"></a>IDebugParsedExpression::EvaluateSync
Tato metoda vyhodnotí výraz v analyzované a volitelně přetypování na jiný datový typ výsledku.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT EvaluateSync( 
   DWORD                 dwEvalFlags,
   DWORD                 dwTimeout,
   IDebugSymbolProvider* pSymbolProvider,
   IDebugAddress*        pAddress,
   IDebugBinder*         pBinder,
   BSTR                  bstrResultType,
   IDebugProperty2**     ppResult
);
```

```csharp
int EvaluateSync(
   uint                 dwEvalFlags,
   uint                 dwTimeout,
   IDebugSymbolProvider pSymbolProvider,
   IDebugAddress        pAddress,
   IDebugBinder         pBinder,
   string               bstrResultType,
   out IDebugProperty2  ppResult
);
```

#### <a name="parameters"></a>Parametry
 `dwEvalFlags`

 [in] Kombinace [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) konstanty, které řídí, jak se má vyhodnotit výraz.

 `dwTimeout`

 [in] Určuje maximální dobu (v milisekundách) čekání před návratem z této metody. Použití `INFINITE` čekat po neomezenou dobu.

 `pSymbolProvider`

 [in] Poskytovatel symbolů, vyjádřené jako [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) rozhraní.

 `pAddress`

 [in] Aktuální umístění pro spuštění v rámci metody, vyjádřené jako [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) rozhraní.

 `pBinder`

 [in] Vazač, vyjádřené jako [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) rozhraní.

 `bstrResultType`

 [in] Typ výsledku by měl být přetypovat na. Tento argument může být hodnota null.

 `ppResult`

 [out] Vrátí [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) rozhraní, které představuje výsledky hodnocení.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Kontext vyhodnocení výrazu je dán `pAddress`, takže je možné určit obsahující metodu a poté oborů použití jazyka pravidla k určení hodnoty symbolů ve výrazu.

## <a name="see-also"></a>Viz také
- [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)
- [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)
- [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
- [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md)