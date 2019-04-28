---
title: Copy (zachytávání prostřednictvím kódu programu) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 30ec235a-0abb-44b9-8852-61bc9e67ce22
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3a888605cfae6b5430782defd198f83988c31870
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62895951"
---
# <a name="copy-programmatic-capture"></a>Copy (zachytávání prostřednictvím kódu programu)
Zkopíruje obsah aktivní grafiky (.vsglog) protokolu do nového souboru.

## <a name="syntax"></a>Syntaxe

```C++
void Copy(
  wchar_t const * szNewVSGLog
);
```

#### <a name="parameters"></a>Parametry
 `szNewVSGLog` Název souboru nový soubor protokolu grafiky.

## <a name="remarks"></a>Poznámky
 Kopírování informací grafiky na nový soubor, musí již zaznamenáte některé informace grafiky; v opačném případě nic se nestane.