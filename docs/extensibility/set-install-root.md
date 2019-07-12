---
title: Instalace mimo složku rozšíření s VSIX v. 3 | Dokumentace Microsoftu
ms.date: 11/09/2016
ms.topic: conceptual
ms.assetid: 913c3745-8aa9-4260-886e-a05aecfb2225
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2d5fc36c1244edd0988b6b76f8106020369cd90b
ms.sourcegitcommit: da4079f5b6ec884baf3108cbd0519d20cb64c70b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2019
ms.locfileid: "67852199"
---
# <a name="install-outside-the-extensions-folder"></a>Instalace mimo složku rozšíření

Od verze Visual Studio 2017 a VSIX v. 3 (verze 3), rozšíření prostředků je možné nainstalovat mimo složku rozšíření. V současné době jsou povoleny následující umístění jako umístění platná instalace (kde [INSTALLDIR] je namapována na instanci aplikace Visual Studio Instalační adresář):

* \MSBuild [INSTALLDIR]
* [INSTALLDIR]\Xml\Schemas
* [INSTALLDIR]\Common7\IDE\PublicAssemblies
* \Licenses [INSTALLDIR]
* [INSTALLDIR]\Common7\IDE\ReferenceAssemblies
* [INSTALLDIR]\Common7\IDE\RemoteDebugger
* [INSTALLDIR] \Common7\IDE\VC\VCTargets (pouze podporované pro Visual Studio 2017; zastaralé funkce pro Visual Studio 2019 a novější)

> [!NOTE]
> Formát VSIX neumožňuje instalovat mimo strukturu složek instalace sady Visual Studio. 

Aby bylo možné podporovat instalace pro tyto adresáře, musí být rozšíření VSIX nainstalovaná "jednotlivé instance vázaná na počítač". Lze povolit zaškrtnutím políčka "all users" v Návrháři extension.vsixmanifest:

![Zkontrolujte všechny uživatele](media/check-all-users.png)

## <a name="how-to-set-the-installroot"></a>Jak nastavit InstallRoot

Nastavení adresáře instalace, můžete použít **vlastnosti** okna v sadě Visual Studio. Například můžete nastavit `InstallRoot` vlastnost odkaz na projekt do jednoho z výše uvedených umístění:

![Nainstalujte kořenový vlastnosti](media/install-root-properties.png)

Některá metadata se přidá do příslušné `ProjectReference` vlastnost v souboru .csproj projektu VSIX:

```xml
 <ProjectReference Include="..\ClassLibrary1\ClassLibrary1.csproj">
        <Project>{69a979f1-eba2-43e7-9346-0e56e803508b}</Project>
        <Name>ClassLibrary1</Name>
        <InstallRoot>PublicAssemblies</InstallRoot>
 </ProjectReference>
```

> [!NOTE]
> Pokud dáváte přednost můžete přímo, upravte soubor csproj.

## <a name="how-to-set-a-subpath-under-the-installroot"></a>Jak nastavit podřízená cesta v rámci InstallRoot

Pokud chcete nainstalovat podřízená cesta pod `InstallRoot`, lze provést nastavením `VsixSubPath` vlastnost stejně jako `InstallRoot` vlastnost. Například Řekněme, že chceme výstup naše projektu reference k instalaci na "[INSTALLDIR]\MSBuild\MyCompany\MySDK\1.0". Můžeme to snadno udělat pomocí návrháře vlastnost:

![podřízená cesta v sadě](media/set-subpath.png)

Odpovídající změny .csproj bude vypadat nějak takto:

```xml
<ProjectReference Include="..\ClassLibrary1\ClassLibrary1.csproj">
       <Project>{69a979f1-eba2-43e7-9346-0e56e803508b}</Project>
       <Name>ClassLibrary1</Name>
       <InstallRoot>MSBuild</InstallRoot>
       <VSIXSubPath>MyCompany\MySDK\1.0</VSIXSubPath>
</ProjectReference>
```

## <a name="extra-information"></a>Další informace

Vlastnosti návrháře změny se aplikují na víc než jenom odkazy projektu; můžete nastavit `InstallRoot` metadat pro položky v rámci projektu také (pomocí stejných metod popsaných výše).
