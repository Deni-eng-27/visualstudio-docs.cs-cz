---
title: Moduly | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- modules
- debugging [Debugging SDK], modules
ms.assetid: c4cf2809-dbdb-4e75-9273-b3d3d77b67d0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1f31e3760a0697be8c9fc80eb811c99df79d32b1
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56718908"
---
# <a name="modules"></a>Moduly
Z hlediska architektury ladicího programu *modulu*:

-   Je fyzický kontejneru kódu, jako je spustitelný soubor nebo knihovny DLL.

-   Můžete znovu načíst jeho symboly a popsat sám sebe. Modul popisy jsou zobrazovány v okně moduly v integrovaném vývojovém prostředí.

-   Je reprezentován [IDebugModule2](../../extensibility/debugger/reference/idebugmodule2.md) rozhraní vytvořené ladicí stroj pro popis modulu.

## <a name="see-also"></a>Viz také:
- [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)
- [IDebugModule2](../../extensibility/debugger/reference/idebugmodule2.md)