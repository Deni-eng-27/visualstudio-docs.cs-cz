---
title: IDebugSettingsCallback2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugSettingsCallback2 interface
ms.assetid: 7e525d0b-7d7a-4d1c-8b78-e1398fa922f2
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2c85b54f92970dca5d712b827019300f850b03cc
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80719937"
---
# <a name="idebugsettingscallback2"></a>IDebugSettingsCallback2
Umožňuje modulům ladění vzdáleně číst nastavení metriky.

## <a name="syntax"></a>Syntax

```
IDebugSettingsCallback2D : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
Toto rozhraní je implementováno pomocí zpětného volání události Správce ladění relace a spotřebované moduly ladění. Dá se použít taky místně místo dbgmetric [d]. lib.

## <a name="methods"></a>Metody
V následující tabulce jsou uvedeny metody `IDebugSettingsCallback2` .

|Metoda|Popis|
|------------|-----------------|
|[EnumEEs](../../../extensibility/debugger/reference/idebugsettingscallback2-enumees.md)|Vytvoří výčet dostupných vyhodnocení výrazů pro daný jazyk a identifikátory dodavatelů.|
|[GetEELocalObject](../../../extensibility/debugger/reference/idebugsettingscallback2-geteelocalobject.md)|Načte místní objekt vyhodnocení výrazu pro danou metriku.|
|[GetEEMetricDword](../../../extensibility/debugger/reference/idebugsettingscallback2-geteemetricdword.md)|Načte hodnotu, která odpovídá zadané metrikě vyhodnocovacího filtru výrazů.|
|[GetEEMetricFile](../../../extensibility/debugger/reference/idebugsettingscallback2-geteemetricfile.md)|Načte soubor metriky vyhodnocovacího filtru výrazů s daným názvem nebo metrikou.|
|[GetEEMetricGuid](../../../extensibility/debugger/reference/idebugsettingscallback2-geteemetricguid.md)|Načte jedinečný identifikátor metriky vyhodnocovacího filtru výrazů daného názvu.|
|[GetEEMetricString](../../../extensibility/debugger/reference/idebugsettingscallback2-geteemetricstring.md)|Načte řetězec hodnoty metriky vyhodnocovacího filtru výrazů daného názvu.|
|[GetMetricDword](../../../extensibility/debugger/reference/idebugsettingscallback2-getmetricdword.md)|Načte hodnotu metriky daného názvu.|
|[GetMetricGuid](../../../extensibility/debugger/reference/idebugsettingscallback2-getmetricguid.md)|Načte jedinečný identifikátor metriky daného názvu.|
|[GetMetricString](../../../extensibility/debugger/reference/idebugsettingscallback2-getmetricstring.md)|Načte řetězec hodnoty metriky daného názvu.|

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg. h

Obor názvů: Microsoft. VisualStudio. Debugger. Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="example"></a>Příklad
Následující příklad ukazuje funkci, která přebírá objekt **IDebugSettingsCallback2** jako parametr.

```cpp
HRESULT GetDebugSettingsCallback (IDebugSettingsCallback2 **ppCallback)
{
    HRESULT hRes = E_FAIL;

    if ( ppCallback )
    {
        if ( EVAL(m_pdec) )
            hRes = m_pdec->QueryInterface(IID_IDebugSettingsCallback2, (void **)ppCallback);
        else
            hRes = E_FAIL;
    }
    else
        hRes = E_INVALIDARG;

    return ( hRes );
}
```
