---
title: Funkce SccGetExtendedCapabilities | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccGetExtendedCapabilities
helpviewer_keywords:
- SccGetExtendedCapabilities function
ms.assetid: 588c6a92-2147-4d8b-a357-96ca7da0a092
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5247f2de7ffc63db7235f915c72b3274b8fee5f5
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80700727"
---
# <a name="sccgetextendedcapabilities-function"></a>SccGetExtendedCapabilities – funkce
Tato funkce vrací další funkce podporované modulem plug-in správy zdrojových kódů.

## <a name="syntax"></a>Syntaxe

```cpp
SCCRTN SccGetExtendedCapabilities(
   LPVOID pContext,
   LONG lSccExCaps,
   LPBOOL pbSupported
);
```

### <a name="parameters"></a>Parametry
 pContext

pro Ukazatel kontextu modulu plug-in správy zdrojových kódů.

 lSccExCaps

pro Příznak určující rozšířenou schopnost, pro kterou se má testovat (viz tabulka kódů rozšířených schopností v [příznacích schopností](../extensibility/capability-flags.md) pro možné příznaky).

 pbSupported

mimo Vrátí nenulovou hodnotu ( `TRUE` ), pokud je zadaná možnost podporována. v opačném případě vrátí hodnotu nula ( `FALSE` ).

## <a name="return-value"></a>Vrácená hodnota
 Při implementaci modulu plug-in správy zdrojových kódů této funkce se očekává, že se vrátí jedna z následujících hodnot:

|Hodnota|Popis|
|-----------|-----------------|
|SCC_OK|Operace Get schopností se úspěšně dokončila.|
|SCC_E_UNKNOWNERROR<br /><br /> SCC_E_NONSPECIFICERROR|Došlo k neznámé nebo neurčené chybě.|

## <a name="remarks"></a>Poznámky
 Tato metoda je volána na vyžádání; To znamená, že pokud je nutné testovat schopnost, je volána Tato metoda k určení, zda je tato funkce podporována. Je určen pouze jeden příznak v čase.

## <a name="see-also"></a>Viz také
- [Funkce rozhraní API modulu plug-in správy zdrojového kódu](../extensibility/source-control-plug-in-api-functions.md)
- [Kódy chyb](../extensibility/error-codes.md)
- [Příznaky schopností](../extensibility/capability-flags.md)
