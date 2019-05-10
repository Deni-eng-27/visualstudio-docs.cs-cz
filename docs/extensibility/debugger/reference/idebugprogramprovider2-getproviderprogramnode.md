---
title: IDebugProgramProvider2::GetProviderProgramNode | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramProvider2::GetProviderProgramNode
helpviewer_keywords:
- IDebugProgramProvider2::GetProviderProgramNode
ms.assetid: e62e8e83-acbb-4c52-aedf-ffbd4670db29
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 594fef8a83c01b4bad4d47fdb206d64e445ad515
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65459021"
---
# <a name="idebugprogramprovider2getproviderprogramnode"></a>IDebugProgramProvider2::GetProviderProgramNode
Načte uzel program pro konkrétní aplikaci.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetProviderProgramNode(
   PROVIDER_FLAGS       Flags,
   IDebugDefaultPort2*  pPort,
   AD_PROCESS_ID        processId,
   REFGUID              guidEngine,
   UINT64               programId,
   IDebugProgramNode2** ppProgramNode
);
```

```csharp
int GetProviderProgramNode(
   enum_PROVIDER_FLAGS    Flags,
   IDebugDefaultPort2     pPort,
   AD_PROCESS_ID          ProcessId,
   ref Guid               guidEngine,
   ulong                  programId,
   out IDebugProgramNode2 ppProgramNode
);
```

## <a name="parameters"></a>Parametry
 `Flags`\

 [in] Kombinace příznaků z [PROVIDER_FLAGS](../../../extensibility/debugger/reference/provider-flags.md) výčtu. Následující příznaky jsou typické pro toto volání:

|Příznak|Popis|
|----------|-----------------|
|`PFLAG_REMOTE_PORT`|Volající běží na vzdáleném počítači.|
|`PFLAG_DEBUGGEE`|Volající je momentálně laděna (Další informace o zařazování bude vrácen pro každý uzel).|
|`PFLAG_ATTACHED_TO_DEBUGGEE`|Volající, byl připojený k ale není spuštěn pomocí ladicího programu.|

 `pPort`\

 [in] Port volající proces běží na.

 `processId`\

 [in] [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) struktura obsahující dotyčný ID procesu, který obsahuje program.

 `guidEngine`\

 [in] Identifikátor GUID ladicího stroje, který program je připojen k (pokud existuje).

 `programId`\

 [in] ID aplikace, pro které chcete získat uzel programu.

 `ppProgramNode`\

 [out] [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) objekt představující uzel pro požadovaný program.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také:
- [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)
- [PROVIDER_FLAGS](../../../extensibility/debugger/reference/provider-flags.md)
- [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)
- [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)
- [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)