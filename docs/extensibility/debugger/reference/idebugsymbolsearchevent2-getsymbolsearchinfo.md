---
title: IDebugSymbolSearchEvent2::GetSymbolSearchInfo | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugSymbolSearchEvent2::GetSymbolSearchInfo
helpviewer_keywords:
- IDebugSymbolSearchEvent2::GetSymbolSearchInfo
ms.assetid: ae9eb72b-f2aa-43b8-87ca-da19d2e78d17
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d917a3f33d0c4339420c048fe20184245bb8dac1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62868405"
---
# <a name="idebugsymbolsearchevent2getsymbolsearchinfo"></a>IDebugSymbolSearchEvent2::GetSymbolSearchInfo
Volá obslužnou rutinou události k načtení výsledků o proces načítání symbolů.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetSymbolSearchInfo(
   IDebugModule3**    pModule,
   BSTR*              pbstrDebugMessage,
   MODULE_INFO_FLAGS* pdwModuleInfoFlags
);
```

```csharp
int GetSymbolSearchInfo(
   IDebugModule3              pModule,
   ref string                 pbstrDebugMessage,
   out enum_MODULE_INFO_FLAGS pdwModuleInfoFlags
);
```

#### <a name="parameters"></a>Parametry
 `pModule`

 [out] IDebugModule3 objekt, který reprezentuje modul, pro kterou byly načteny symboly.

 `pbstrDebugMessage`

 [out v] Vrátí řetězec obsahující všechny chybové zprávy z modulu. Pokud se nezobrazí žádná chyba, tento řetězec bude obsahovat pouze název modulu ale nikdy je prázdný.

> [!NOTE]
> [C++] `pbstrDebugMessage` nemůže být `NULL` a musí být uvolněna pomocí operátoru `SysFreeString`.

 `pdwModuleInfoFlags`

 [out] Kombinace příznaků z [MODULE_INFO_FLAGS](../../../extensibility/debugger/reference/module-info-flags.md) výčet označující, zda nebyly načteny žádné symboly.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Když se obdrží obslužnou rutinu [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md) událost po pokusu o načtení symbolů ladění pro modul, obslužná rutina může volat thismethod k určení výsledků zátěž.

## <a name="see-also"></a>Viz také
- [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)
- [MODULE_INFO_FLAGS](../../../extensibility/debugger/reference/module-info-flags.md)
- [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md)