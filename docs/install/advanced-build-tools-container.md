---
title: Rozšířený příklad pro kontejnery
description: ''
ms.date: 07/03/2019
ms.topic: conceptual
ms.assetid: e03835db-a616-41e6-b339-92b41d0cfc70
author: heaths
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: a1a9c1a8db0c4f3481e1edf220412612d70064a8
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2019
ms.locfileid: "67825180"
---
# <a name="advanced-example-for-containers"></a>Rozšířený příklad pro kontejnery

::: moniker range="vs-2017"

Ukázkový soubor Dockerfile v [instalace Build Tools do kontejneru](build-tools-container.md) vždy používá [microsoft/dotnet-framework:4.7.2](https://hub.docker.com/r/microsoft/dotnet-framework) image na základě nejnovější image microsoft/windowsservercore a nejnovější Vizuálu Instalační program sady Studio Build Tools. Pokud publikujete, aby k této bitové kopie [registru Dockeru](https://azure.microsoft.com/services/container-registry) pro ostatní uživatele o přijetí změn, tato image může být v pořádku pro řadu scénářů. Ale v praxi je běžné konkrétně o jaké základní image, můžete použít, jaké binární soubory můžete stáhnout, a který nástroj verze je nainstalovat.

::: moniker-end

::: moniker range="vs-2019"

Ukázkový soubor Dockerfile v [instalace Build Tools do kontejneru](build-tools-container.md) vždy používá [microsoft/dotnet-framework: 4.8](https://hub.docker.com/r/microsoft/dotnet-framework) image na základě nejnovější image microsoft/windowsservercore a nejnovější Vizuálu Instalační program sady Studio Build Tools. Pokud publikujete, aby k této bitové kopie [registru Dockeru](https://azure.microsoft.com/services/container-registry) pro ostatní uživatele o přijetí změn, tato image může být v pořádku pro řadu scénářů. Ale v praxi je běžné konkrétně o jaké základní image, můžete použít, jaké binární soubory můžete stáhnout, a který nástroj verze je nainstalovat.

::: moniker-end

V následujícím příkladu soubor Dockerfile použije značku konkrétní verzi Image microsoft/dotnet-framework. Použití s konkrétní značkou pro základní image je běžné a umožňuje snadno zapamatovatelné budovy nebo vždy znovu sestavit Image má stejný základ.

> [!NOTE]
> Visual Studio nelze nainstalovat do microsoft/windowsservercore:10.0.14393.1593 nebo všechny bitové kopie na základě, který obsahuje známé problémy, spouští se instalační program v kontejneru. Další informace najdete v tématu [známé problémy pro kontejnery](build-tools-container-issues.md).

Následující příklad stáhne nejnovější verze sestavovacích nástrojů. Pokud chcete použít starší verzi Build Tools do kontejneru můžete nainstalovat později, je nutné nejprve [vytvořit](create-an-offline-installation-of-visual-studio.md) a [udržovat](update-a-network-installation-of-visual-studio.md) rozložení.

## <a name="install-script"></a>Instalace skriptu

Shromažďování protokolů při chybě instalace dojde, vytvořte dávkový skript, který je pojmenován "Soubor Install.cmd" v pracovním adresáři, který obsahuje následující obsah:

```shell
@if not defined _echo echo off
setlocal enabledelayedexpansion

call %*
if "%ERRORLEVEL%"=="3010" (
    exit /b 0
) else (
    if not "%ERRORLEVEL%"=="0" (
        set ERR=%ERRORLEVEL%
        call C:\TEMP\collect.exe -zip:C:\vslogs.zip

        exit /b !ERR!
    )
)
```

## <a name="dockerfile"></a>Dockerfile

V pracovním adresáři vytvořte "Soubor Dockerfile" s následujícím obsahem:

::: moniker range="vs-2017"

```dockerfile
# escape=`

# Use a specific tagged image. Tags can be changed, though that is unlikely for most images.
# You could also use the immutable tag @sha256:3eaa3ba18f45e6561f32d8dd927045413f1dd043d7d29fb581f5cb3c6f7d7481
ARG FROM_IMAGE=mcr.microsoft.com/dotnet/framework/sdk:4.7.2-windowsservercore-ltsc2019
FROM ${FROM_IMAGE}

# Copy our Install script.
COPY Install.cmd C:\TEMP\

# Download collect.exe in case of an install failure.
ADD https://aka.ms/vscollect.exe C:\TEMP\collect.exe

# Use the latest release channel. For more control, specify the location of an internal layout.
ARG CHANNEL_URL=https://aka.ms/vs/15/release/channel
ADD ${CHANNEL_URL} C:\TEMP\VisualStudio.chman

# Download and install Build Tools excluding workloads and components with known issues.
ADD https://aka.ms/vs/15/release/vs_buildtools.exe C:\TEMP\vs_buildtools.exe
RUN C:\TEMP\Install.cmd C:\TEMP\vs_buildtools.exe --quiet --wait --norestart --nocache `
    --installPath C:\BuildTools `
    --channelUri C:\TEMP\VisualStudio.chman `
    --installChannelUri C:\TEMP\VisualStudio.chman `
    --all `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.10240 `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.10586 `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.14393 `
    --remove Microsoft.VisualStudio.Component.Windows81SDK

# Start developer command prompt with any other commands specified.
ENTRYPOINT C:\BuildTools\Common7\Tools\VsDevCmd.bat &&

# Default to PowerShell if no other command specified.
CMD ["powershell.exe", "-NoLogo", "-ExecutionPolicy", "Bypass"]
```

   > [!WARNING]
   > Visual Studio 2017 verze 15,8 nebo starší (libovolný produkt) nenainstaluje správně mcr\.microsoft\.com\/windows\/servercore:1809 nebo novější. Se nezobrazí žádná chyba.
   >
   > Zobrazit [známé problémy pro kontejnery](build-tools-container-issues.md) Další informace.

::: moniker-end

::: moniker range="vs-2019"

```dockerfile
# escape=`

# Use a specific tagged image. Tags can be changed, though that is unlikely for most images.
# You could also use the immutable tag @sha256:324e9ab7262331ebb16a4100d0fb1cfb804395a766e3bb1806c62989d1fc1326
ARG FROM_IMAGE=mcr.microsoft.com/dotnet/framework/sdk:4.8-windowsservercore-ltsc2019
FROM ${FROM_IMAGE}

# Copy our Install script.
COPY Install.cmd C:\TEMP\

# Download collect.exe in case of an install failure.
ADD https://aka.ms/vscollect.exe C:\TEMP\collect.exe

# Use the latest release channel. For more control, specify the location of an internal layout.
ARG CHANNEL_URL=https://aka.ms/vs/16/release/channel
ADD ${CHANNEL_URL} C:\TEMP\VisualStudio.chman

# Download and install Build Tools excluding workloads and components with known issues.
ADD https://aka.ms/vs/16/release/vs_buildtools.exe C:\TEMP\vs_buildtools.exe
RUN C:\TEMP\Install.cmd C:\TEMP\vs_buildtools.exe --quiet --wait --norestart --nocache `
    --installPath C:\BuildTools `
    --channelUri C:\TEMP\VisualStudio.chman `
    --installChannelUri C:\TEMP\VisualStudio.chman `
    --all `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.10240 `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.10586 `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.14393 `
    --remove Microsoft.VisualStudio.Component.Windows81SDK

# Start developer command prompt with any other commands specified.
ENTRYPOINT C:\BuildTools\Common7\Tools\VsDevCmd.bat &&

# Default to PowerShell if no other command specified.
CMD ["powershell.exe", "-NoLogo", "-ExecutionPolicy", "Bypass"]
```

::: moniker-end

Spusťte následující příkaz k sestavení image v aktuálním pracovním adresáři:

::: moniker range="vs-2017"

```shell
docker build -t buildtools2017:15.6.27428.2037 -t buildtools2017:latest -m 2GB .
```

::: moniker-end

::: moniker range="vs-2019"

```shell
docker build -t buildtools2019:16.0.28714.193 -t buildtools2019:latest -m 2GB .
```

::: moniker-end

Volitelně můžete předat jednoho nebo obou `FROM_IMAGE` nebo `CHANNEL_URL` argumentů pomocí `--build-arg` přepínač příkazového řádku a zadejte jinou základní image nebo umístění interní rozložení zachovat pevnou image.

## <a name="diagnosing-install-failures"></a>Diagnostika selhání instalace

Tento příklad stáhne konkrétních nástrojů a ověří, že klíče hash shodují. Se také stáhne nejnovější sady Visual Studio a nástroj pro shromažďování protokolů rozhraní .NET tak, že pokud dojde k selhání instalace, můžete zkopírovat protokoly na hostitelském počítači k analýze selhání.

::: moniker range="vs-2017"

```shell
> docker build -t buildtools2017:15.6.27428.2037 -t buildtools2017:latest -m 2GB .
Sending build context to Docker daemon

...
Step 8/10 : RUN C:\TEMP\Install.cmd C:\TEMP\vs_buildtools.exe --quiet --wait --norestart --nocache ...
 ---> Running in 4b62b4ce3a3c
The command 'cmd /S /C C:\TEMP\Install.cmd C:\TEMP\vs_buildtools.exe ...' returned a non-zero code: 1603

> docker cp 4b62b4ce3a3c:C:\vslogs.zip "%TEMP%\vslogs.zip"
```

::: moniker-end

::: moniker range="vs-2019"

```shell
> docker build -t buildtools2019:16.0.28714.193 -t buildtools2019:latest -m 2GB .
Sending build context to Docker daemon

...
Step 8/10 : RUN C:\TEMP\Install.cmd C:\TEMP\vs_buildtools.exe --quiet --wait --norestart --nocache ...
 ---> Running in 4b62b4ce3a3c
The command 'cmd /S /C C:\TEMP\Install.cmd C:\TEMP\vs_buildtools.exe ...' returned a non-zero code: 1603

> docker cp 4b62b4ce3a3c:C:\vslogs.zip "%TEMP%\vslogs.zip"
```

::: moniker-end

Po poslední řádek nedokončí, otevřete na svém počítači "% TEMP%\vslogs.zip", nebo odešlete problém na [komunity vývojářů](https://developercommunity.visualstudio.com) webu.

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [Instalace Build Tools do kontejneru](build-tools-container.md)
* [Známé problémy s kontejnery](build-tools-container-issues.md)
* [ID pracovního vytížení a komponenta Visual Studio Build Tools](workload-component-id-vs-build-tools.md)
