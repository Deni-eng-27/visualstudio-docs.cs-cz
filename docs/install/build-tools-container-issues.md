---
title: Známé problémy s kontejnery
description: Další informace o známých problémech, které mohou nastat při instalaci sady Visual Studio vytvářet nástroje 2017 do kontejneru Windows.
ms.custom: ''
ms.date: 04/18/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 140083f1-05bc-4014-949e-fb5802397c7a
author: heaths
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c94c6756e1272b08136f624e9cde63523d630b35
ms.sourcegitcommit: 6b092e7d466377f06913d49d183dbbdca16730f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/28/2018
ms.locfileid: "43139142"
---
# <a name="known-issues-for-containers"></a>Známé problémy s kontejnery

Existuje několik problémů při instalaci sady Visual Studio do kontejneru Dockeru.

## <a name="windows-container"></a>Kontejner Windows

Následující známé problémy při instalaci sady Visual Studio vytvářet nástroje 2017 do kontejneru Windows.

* Visual Studio nelze nainstalovat do kontejneru podle microsoft/windowsservercore:10.0.14393.1593 bitové kopie. Obrázky označené verzí Windows staršího nebo novějšího by mělo fungovat.
* Nelze nainstalovat sadu Windows SDK verze starší než 10.0.14393. Některé balíčky schopen provést instalaci, a úlohy, které jsou závislé na tyto balíčky nebudou fungovat.
* Předejte `-m 2GB` (nebo více) při sestavování image. Některé úlohy vyžadují více paměti, než je výchozí hodnota 1 GB při instalaci.
* Konfiguraci Dockeru, pokud chcete použít disky větší než výchozích 20 GB.
* Předejte `--norestart` na příkazovém řádku. Při psaní tohoto návodu pokusem o restartování kontejner Windows v rámci kontejneru vrátí `ERROR_TOO_MANY_OPEN_FILES` k hostiteli.
* Pokud vytváříte svou image přímo na microsoft/windowsservercore, nemusí správně nainstalovat rozhraní .NET Framework a je uvedena žádná chyba instalace. Po dokončení instalace se možná nespustí spravovaný kód. Místo toho na základní image [microsoft/dotnet-framework:4.7.1](https://hub.docker.com/r/microsoft/dotnet-framework) nebo novější. Například může zobrazit chyba při sestavování pomocí nástroje MSBuild, jako jsou:

  > C:\BuildTools\MSBuild\15.0\bin\Roslyn\Microsoft.CSharp.Core.TARGETS(84,5): Chyba MSB6003: spustitelný soubor "csc.exe" zadanou úlohu nejde spustit. Nelze načíst soubor nebo sestavení "System.IO.FileSystem, verze = 4.0.1.0, jazykové verze = neutrální, PublicKeyToken = b03f5f7f11d50a3a" nebo některá z jeho závislostí. Systém nemůže najít zadaný soubor.

## <a name="build-tools-container"></a>Sestavení nástroje kontejneru

Při použití nástroje pro sestavení kontejneru, může dojít k následující známé problémy. Zobrazit, zda byly vyřešeny problémy nebo pokud existují další známé problémy, navštivte https://developercommunity.visualstudio.com.

* IntelliTrace nemusí fungovat [některé scénáře](https://github.com/Microsoft/vstest/issues/940) v rámci kontejneru.

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [Instalace Build Tools do kontejneru](build-tools-container.md)
* [Rozšířený příklad pro kontejnery](advanced-build-tools-container.md)
* [ID pracovního vytížení a komponenta Visual Studio 2017 nástroje sestavení](workload-component-id-vs-build-tools.md)
