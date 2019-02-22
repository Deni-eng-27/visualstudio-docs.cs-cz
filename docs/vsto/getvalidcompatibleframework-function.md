---
title: Getvalidcompatibleframework – funkce
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: b975a4b4b2c1b4ae3f6ef0f1d6d23769bb4c77c7
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56643506"
---
# <a name="getvalidcompatibleframework-function"></a>Getvalidcompatibleframework – funkce
  Toto rozhraní API podporuje infrastrukturu sady Office a není určena pro použití přímo v kódu.

## <a name="syntax"></a>Syntaxe

```csharp
HRESULT WINAPI GetValidCompatibleFramework(
    LPCWSTR lpwszCompatibleFrameworksXML,
    BSTR* pbstrValidFrameworkTag
);
```

### <a name="parameters"></a>Parametry

|Parametr|Popis|
|---------------|-----------------|
|*lpwszCompatibleFrameworksXML*|Nepoužívejte.|
|*pbstrValidFrameworkTag*|Nepoužívejte.|

## <a name="return-value"></a>Návratová hodnota
 Pokud funkce uspěje, vrátí **S_OK**. Pokud funkce selže, vrátí kód chyby.
