---
title: Sccgetuseroption – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccGetUserOption
helpviewer_keywords:
- SccGetUserOption function
ms.assetid: 17863747-1901-4c53-a2b3-ed996085e120
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8b237ded8ac0d22500986a9d390834147f24a2c6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62433185"
---
# <a name="sccgetuseroption-function"></a>SccGetUserOption – funkce
Tato funkce načítá širokou škálu možností specifické pro uživatele.

## <a name="syntax"></a>Syntaxe

```cpp
SCCRTN SccGetUserOption(
   LPVOID pContext,
   LONG nOption,
   LPLONG lpVal
);
```

#### <a name="parameters"></a>Parametry
 pContext

[in] Ukazatel kontext modulu plug-in zdroje ovládacího prvku.

 nOption

[in] Možnost načíst (viz poznámky pro možnosti).

 lpVal

[out] Hodnota přidružená k možnost.

## <a name="return-value"></a>Návratová hodnota
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:

|Value|Popis|
|-----------|-----------------|
|SCC_OK|Možnost se načetla úspěšně.|
|SCC_E_OPNOTSUPPORTED|možnost není podporována.|
|SCC_E_NONSPECIFICERROR|Došlo k nespecifikované chybě.|

## <a name="remarks"></a>Poznámky
 Tento příkaz podporuje následující možnosti:

|Možnosti uživatele|Popis|
|-----------------|-----------------|
|`SCC_USEROPT_CHECKOUT_LOCALVER`|Určuje, zda chce uživatel podívejte se na místní verzi souborů. `lpVal` je přiřazen `SCC_USEROPT_COLV_YES` (chce uživatel podívejte se na místní soubory) nebo `SCC_USEROPT_COLV_NO`.|

## <a name="see-also"></a>Viz také
- [Funkce modulu plug-in správy zdrojového kódu v rozhraní API](../extensibility/source-control-plug-in-api-functions.md)
- [Chybové kódy](../extensibility/error-codes.md)