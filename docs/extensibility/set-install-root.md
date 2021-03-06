---
title: Instalace mimo složku rozšíření se souborem VSIX V3 | Microsoft Docs
ms.date: 11/09/2016
ms.topic: conceptual
ms.assetid: 913c3745-8aa9-4260-886e-a05aecfb2225
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: aa2c7d97dda9bba139ec613b367eedbc6307848a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80700186"
---
# <a name="install-outside-the-extensions-folder"></a>Instalace mimo složku rozšíření

Od verze Visual Studio 2017 a VSIX V3 (verze 3) se prostředky rozšíření dají instalovat mimo složku rozšíření. V současné době jsou povolena následující umístění jako platná umístění instalace (kde [INSTALLDIR] je namapována na instalační adresář instance sady Visual Studio):

* [INSTALLDIR] \MSBuild
* [INSTALLDIR] \Xml\Schemas
* [INSTALLDIR] \Common7\IDE\PublicAssemblies
* [INSTALLDIR] \Licenses
* [INSTALLDIR] \Common7\IDE\ReferenceAssemblies
* [INSTALLDIR] \Common7\IDE\RemoteDebugger
* [INSTALLDIR] \Common7\IDE\VC\VCTargets (podporuje se jenom pro Visual Studio 2017; zastaralé pro Visual Studio 2019 a novější)

> [!NOTE]
> Formát VSIX neumožňuje instalaci mimo strukturu instalační složky sady Visual Studio. 

Aby bylo možné podporovat instalaci do těchto adresářů, musí být VSIX nainstalováno pro jednotlivé instance počítače. To lze povolit zaškrtnutím políčka "Všichni uživatelé" v Návrháři Extension. vsixmanifest Designer:

![kontrolovat všechny uživatele](media/check-all-users.png)

## <a name="how-to-set-the-installroot"></a>Jak nastavit InstallRoot

Chcete-li nastavit instalační adresáře, můžete použít okno **vlastnosti** v aplikaci Visual Studio. Například můžete nastavit `InstallRoot` vlastnost odkazu na projekt na jedno z výše uvedených umístění:

![instalace kořenových vlastností](media/install-root-properties.png)

Tím se do odpovídající vlastnosti přidá nějaká metadata `ProjectReference` v souboru. csproj projektu VSIX:

```xml
 <ProjectReference Include="..\ClassLibrary1\ClassLibrary1.csproj">
        <Project>{69a979f1-eba2-43e7-9346-0e56e803508b}</Project>
        <Name>ClassLibrary1</Name>
        <InstallRoot>PublicAssemblies</InstallRoot>
 </ProjectReference>
```

> [!NOTE]
> Pokud dáváte přednost, můžete soubor. csproj upravit přímo.

## <a name="how-to-set-a-subpath-under-the-installroot"></a>Jak nastavit podcestu pod InstallRoot

Pokud byste chtěli nainstalovat do dílčí cesty pod, můžete to udělat tak, že `InstallRoot` nastavíte vlastnost, která je `VsixSubPath` stejně jako `InstallRoot` vlastnost. Řekněme například, že se má výstup odkazu na projekt nainstalovat do: [INSTALLDIR] \MSBuild\MyCompany\MySDK\1.0. To lze snadno provést pomocí návrháře vlastností:

![nastavit dílčí cestu](media/set-subpath.png)

Odpovídající změny. csproj budou vypadat takto:

```xml
<ProjectReference Include="..\ClassLibrary1\ClassLibrary1.csproj">
       <Project>{69a979f1-eba2-43e7-9346-0e56e803508b}</Project>
       <Name>ClassLibrary1</Name>
       <InstallRoot>MSBuild</InstallRoot>
       <VSIXSubPath>MyCompany\MySDK\1.0</VSIXSubPath>
</ProjectReference>
```

## <a name="extra-information"></a>Další informace

Změny návrháře vlastností se použijí na více než jenom odkazy na projekt. můžete `InstallRoot` také nastavit metadata pro položky v projektu (pomocí stejných metod popsaných výše).
