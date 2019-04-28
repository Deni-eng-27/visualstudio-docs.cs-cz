---
title: Automatické použití kódů product key
description: Zjistěte, jak prostřednictvím kódu programu použití kódů product key při nasazení sady Visual Studio.
ms.date: 04/10/2019
ms.custom: seodec18
ms.topic: conceptual
ms.assetid: d79260be-6234-4fd3-89b5-a9756b4a93c1
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: 3f1cdc3d8516271cd397c1d22118ca21a92f78cd
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62974212"
---
# <a name="automatically-apply-product-keys-when-deploying-visual-studio"></a>Automatické použití kódů Product Key při nasazení sady Visual Studio

Můžete použít kód product key prostřednictvím kódu programu jako součást skriptu, který se používá k automatizaci nasazení sady Visual Studio. Můžete nastavit kód product key na zařízení prostřednictvím kódu programu při instalaci sady Visual Studio nebo po dokončení instalace.

## <a name="apply-the-license-after-installation"></a>Použití licence, které jsou po instalaci

::: moniker range="vs-2017"

Nainstalovaná verze sady Visual Studio s kódem product key můžete aktivovat pomocí `StorePID.exe` nástroj na cílových počítačích, v bezobslužném režimu. `StorePID.exe` program je nástroj, který nainstaluje sady Visual Studio 2017 následující výchozí umístění: <br> `C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE`

::: moniker-end

::: moniker range="vs-2019"

Nainstalovaná verze sady Visual Studio s kódem product key můžete aktivovat pomocí `StorePID.exe` nástroj na cílových počítačích, v bezobslužném režimu. `StorePID.exe` program je nástroj, který nainstaluje se Visual Studio 2019 následující výchozí umístění: <br> `C:\Program Files (x86)\Microsoft Visual Studio\2019\Enterprise\Common7\IDE`

::: moniker-end

 Spustit `StorePID.exe` se zvýšenými oprávněními, buď pomocí agenta System Center nebo z příkazového řádku se zvýšenými oprávněními. Kód product key a kód produktu společnosti Microsoft (MPC) za ním.

>[!IMPORTANT]
> Ujistěte se, že mají být zahrnuty pomlček kód product key.

 ```cmd
 StorePID.exe [product key including the dashes] [MPC]
 ```

::: moniker range="vs-2017"

Následující příklad ukazuje použití licence pro Visual Studio 2017 Enterprise, která má MPC 08860, příkazový řádek, kód product key z `AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE`a které předpokládá výchozí umístění instalace:

```cmd
"C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\StorePID.exe" AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE 08860
```

::: moniker-end

::: moniker range="vs-2019"

Následující příklad ukazuje použití licence pro Visual Studio Enterprise. 2019, který má MPC 09260, příkazový řádek, kód product key z `AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE`a které předpokládá výchozí umístění instalace:

```cmd
"C:\Program Files (x86)\Microsoft Visual Studio\2019\Enterprise\Common7\IDE\StorePID.exe" AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE 09260
```

::: moniker-end

::: moniker range="vs-2017"

 V následující tabulce jsou uvedeny kódy MPC pro jednotlivé edice aplikace Visual Studio:

| Edice sady Visual Studio                | MPC   |
|--------------------------------------|-------|
| Visual Studio Enterprise 2017        | 08860 |
| Visual Studio Professional 2017      | 08862 |
| Visual Studio Test Professional 2017 | 08866 |

::: moniker-end

::: moniker range="vs-2019"

| Edice sady Visual Studio                | MPC   |
|--------------------------------------|-------|
| Visual Studio Enterprise 2019        | 09260 |
| Visual Studio Professional 2019      | 09262 |

::: moniker-end

Pokud `StorePID.exe` úspěšně platí kód product key, vrátí se `%ERRORLEVEL%` 0. Pokud se zjistí chyby, vrátí jednu z následujících kódů, v závislosti na podmínce chyby:

| Chyba                     | Kód |
|---------------------------|------|
| `PID_ACTION_SUCCESS`      | 0    |
| `PID_ACTION_NOTINSTALLED` | 1    |
| `PID_ACTION_INVALID`      | 2    |
| `PID_ACTION_EXPIRED`      | 3    |
| `PID_ACTION_INUSE`        | 4    |
| `PID_ACTION_FAILURE`      | 5    |
| `PID_ACTION_NOUPGRADE`    | 6    |

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [Instalace sady Visual Studio](../install/install-visual-studio.md)
* [Vytvoření offline instalace sady Visual Studio](../install/create-an-offline-installation-of-visual-studio.md)
