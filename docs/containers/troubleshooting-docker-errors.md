---
title: Poradce při potížích s chybami klienta Docker ve Windows | Microsoft Docs
description: Řešení problémů, ke kterým dochází při používání sady Visual Studio k vytvoření a nasazení webových aplikací do Docker ve Windows pomocí sady Visual Studio.
ms.technology: vs-azure
author: ghogen
manager: jillfra
ms.custom: seodec18
ms.assetid: 346f70b9-7b52-4688-a8e8-8f53869618d3
ms.devlang: dotnet
ms.topic: troubleshooting
ms.workload: multiple
ms.date: 01/27/2020
ms.author: ghogen
ms.openlocfilehash: 31b9d8649abed0f9901aa872ff3939c25e3025b8
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "87235105"
---
# <a name="troubleshoot-visual-studio-development-with-docker"></a>Řešení potíží při vývoji v sadě Visual Studio pomocí Dockeru

Při práci s nástroji kontejneru sady Visual Studio může při sestavování nebo ladění aplikace dojít k problémům. Níže jsou uvedeny některé běžné kroky při řešení potíží.

## <a name="volume-sharing-is-not-enabled-enable-volume-sharing-in-the-docker-ce-for-windows-settings--linux-containers-only"></a>Sdílení svazků není povoleno. Povolit sdílení svazků v nastaveních Docker CE for Windows (jenom kontejnery Linux)

Řešení tohoto problému:

1. V oznamovací oblasti klikněte pravým tlačítkem na **Docker for Windows** a pak vyberte **Nastavení**.
1. Vyberte **sdílené jednotky** a nasdílejte systémovou jednotku společně s jednotkou, ve které se nachází projekt.

> [!NOTE]
> Pokud se soubory zobrazují jako sdílené, možná budete muset kliknout na resetovat přihlašovací údaje... odkaz ve spodní části dialogového okna, aby bylo možné sdílení svazků znovu povolit. Chcete-li pokračovat po resetování přihlašovacích údajů, bude pravděpodobně nutné restartovat aplikaci Visual Studio.

![sdílené jednotky](media/troubleshooting-docker-errors/shareddrives.png)

> [!TIP]
> Verze sady Visual Studio novější než Visual Studio 2017 verze 15,6 se zobrazí výzva, když nejsou nakonfigurovány **sdílené jednotky** .

### <a name="container-type"></a>Typ kontejneru

Když do projektu přidáte podporu Docker, zvolíte buď kontejner Windows, nebo Linux. Hostitel Docker musí používat stejný typ kontejneru. Chcete-li změnit typ kontejneru v běžící instanci Docker, klikněte pravým tlačítkem myši na ikonu Docker panelu systému a vyberte možnost **Přepnout na kontejnery Windows...** nebo **Přepnout na kontejnery platformy Linux..**..

## <a name="unable-to-start-debugging"></a>Nejde spustit ladění

Jedním z důvodů může souviset se zastaralými součástmi ladění ve složce profilu uživatele. Spusťte následující příkazy, abyste tyto složky odebrali, aby se nejnovější ladicí komponenty stáhly do další relace ladění.

- del%USERPROFILE%\vsdbg
- del%USERPROFILE%\onecoremsvsmon

## <a name="errors-specific-to-networking-when-debugging-your-application"></a>Chyby specifické pro sítě při ladění aplikace

Zkuste provést stažení skriptu z části [vyčistit síťové hostitele kontejneru](https://github.com/MicrosoftDocs/Virtualization-Documentation/tree/master/windows-server-container-tools/CleanupContainerHostNetworking), čímž aktualizujete součásti související se sítí na hostitelském počítači.

## <a name="mounts-denied"></a>Připojení byla zamítnuta.

Při použití Docker pro macOS se může zobrazit chyba odkazování na složku/usr/local/share/dotnet/sdk/NuGetFallbackFolder. Přidat složku na kartu Sdílení souborů v Docker

## <a name="docker-users-group"></a>Skupina uživatelů Docker

Při práci s kontejnery může dojít k následující chybě v aplikaci Visual Studio:

```
The current user must be in the 'docker-users' group to use Docker Desktop. 
Add yourself to the 'docker-users' group and then log out of Windows.
```

Abyste mohli mít oprávnění k práci s kontejnery Docker, musíte být členem skupiny Docker-Users.  Pokud se chcete do skupiny ve Windows 10 přidat sami, postupujte takto:

1. V nabídce Start otevřete položku **Správa počítače**.
1. Rozbalte položku **místní uživatelé a skupiny**a klikněte na možnost **skupiny**.
1. Vyhledejte skupinu **Docker-Users** , klikněte pravým tlačítkem myši a vyberte **Přidat do skupiny**.
1. Přidejte svůj uživatelský účet nebo účty.
1. Odhlaste se a znovu se přihlaste, aby se tyto změny projevily.

`net localgroup`K přidání uživatelů do konkrétních skupin můžete použít také příkaz na příkazovém řádku správce.

```cmd
net localgroup docker-users DOMAIN\username /add
```

V PowerShellu použijte funkci [Add-LocalGroupMember](/powershell/module/microsoft.powershell.localaccounts/add-localgroupmember) .

## <a name="low-disk-space"></a>Nedostatek místa na disku

Ve výchozím nastavení Docker ukládá obrázky do složky *% Složka ProgramData%/Docker/* , která se obvykle nachází na systémové jednotce * C:\ProgramData\Docker \* . Pokud nechcete, aby obrázky zabíraly cenné místo na systémové jednotce, můžete změnit umístění složky s obrázkem.  Z ikony Docker na panelu úloh otevřete nastavení Docker, klikněte na **démon**a přepněte ze **základního** na **Upřesnit**. V podokně úpravy přidejte `graph` nastavení vlastnosti s hodnotou požadovaného umístění pro Image Docker:

```json
    "graph": "D:\\mypath\\images"
```

![Snímek obrazovky s nastavením umístění bitové kopie Docker](media/troubleshooting-docker-errors/docker-settings-image-location.png)

Klikněte na **použít** a restartujte Docker. Tyto kroky upraví konfigurační soubor v umístění *% Složka ProgramData% \docker\config\daemon.jsna*. Dříve sestavené obrázky nejsou přesunuty.

## <a name="microsoftdockertools-github-repo"></a>Úložiště GitHub pro Microsoft/DockerTools

Další problémy, se kterými se setkáte, najdete v článku problémy s  [Microsoftem a DockerTools](https://github.com/microsoft/dockertools/issues) .

## <a name="see-also"></a>Viz také

- [Řešení potíží s Visual Studiem](/troubleshoot/visualstudio/welcome-visual-studio/)