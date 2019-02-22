---
title: Enumerátor kódu stavu adresáře | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- directory status code enumerator
- source control plug-ins, directory status enumeration
ms.assetid: 616026b5-f529-40ef-90c1-1836e116d797
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6e62685a1a351c9a5773e18a53316106a18af66a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56694657"
---
# <a name="directory-status-code-enumerator"></a>Enumerátor kódu stavu adresáře
`SccDirStatus` Obsahuje čítače výčtu s názvem konstantní hodnoty, které určují stav adresáře v systému správy zdrojového kódu. Tento výčet je používán [sccdirqueryinfo –](../extensibility/sccdirqueryinfo-function.md). To byla zavedena ve verzi 1.2 rozhraní API modulu Plug-in zdroje ovládacího prvku.

## <a name="syntax"></a>Syntaxe

```
enum SccDirStatus {
   SCC_DIRSTATUS_INVALID       = -1L,
   SCC_DIRSTATUS_NOTCONTROLLED = 0x0000L,
   SCC_DIRSTATUS_CONTROLLED    = 0x0001L,
   SCC_DIRSTATUS_EMPTYPROJ     = 0x0002L
};
```

## <a name="members"></a>Členové
 Nebylo možné získat stav SCC_DIRSTATUS_INVALID; Nespoléhejte na to.

 Adresář SCC_DIRSTATUS_NOTCONTROLLED není pod správou zdrojových kódů.

 Adresář SCC_DIRSTATUS_CONTROLLED je pod správou zdrojových kódů.

 Projekt SCC_DIRSTATUS_EMPTYPROJ odpovídající tento adresář je prázdný.

## <a name="see-also"></a>Viz také:
- [Ovládací prvek moduly plug-in zdrojového kódu](../extensibility/source-control-plug-ins.md)
- [SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md)