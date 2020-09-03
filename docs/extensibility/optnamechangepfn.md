---
title: OPTNAMECHANGEPFN | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- OPTNAMECHANGEPFN
helpviewer_keywords:
- OPTNAMECHANGEPFN callback function
ms.assetid: 147303f3-c7f1-438a-81b7-db891ea3d076
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 603bd08c1ec3832bf732e0b33101076738d009e3
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80702249"
---
# <a name="optnamechangepfn"></a>OPTNAMECHANGEPFN
Toto je funkce zpětného volání určená při volání metody [SccSetOption](../extensibility/sccsetoption-function.md) (using `SCC_OPT_NAMECHANGEPFN` ) a slouží ke sdělování změn názvů provedených modulem plug-in správy zdrojových kódů zpět do integrovaného vývojového prostředí (IDE).

## <a name="signature"></a>Podpis

```cpp
typedef void (*OPTNAMECHANGEPFN)(
   LPVOID pvCallerData,
   LPCSTR pszOldName,
   LPCSTR pszNewName
);
```

## <a name="parameters"></a>Parametry
 pvCallerData

pro Hodnota uživatele zadaná v předchozím volání metody [SccSetOption](../extensibility/sccsetoption-function.md) (s použitím možnosti `SCC_OPT_USERDATA` )

 pszOldName

pro Původní název souboru

 pszNewName

pro Název souboru byl přejmenován na.

## <a name="return-value"></a>Vrácená hodnota
 Žádné

## <a name="remarks"></a>Poznámky
 Pokud je soubor přejmenován během operace správy zdrojových kódů, modul plug-in správy zdrojových kódů může rozhraní IDE upozornit na změnu názvu prostřednictvím tohoto zpětného volání.

 Pokud rozhraní IDE toto zpětné volání nepodporuje, nebude volat [SccSetOption](../extensibility/sccsetoption-function.md) k jeho zadání. Pokud modul plug-in nepodporuje toto zpětné volání, vrátí se `SCC_E_OPNOTSUPPORTED` ze `SccSetOption` funkce, když se IDE pokusí nastavit zpětné volání.

## <a name="see-also"></a>Viz také
- [Funkce zpětného volání implementované rozhraním IDE](../extensibility/callback-functions-implemented-by-the-ide.md)
- [SccSetOption](../extensibility/sccsetoption-function.md)
