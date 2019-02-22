---
title: '&lt;Řetězce&gt; – Element (zaváděcí nástroj) | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- MSBuild.GenerateBootstrapper.NoStringsForCulture
- MSBuild.GenerateBootstrapper.ProductCultureNotFound
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- <Strings> element [bootstrapper]
ms.assetid: d5ea3613-5fc9-4a11-bef3-46a01178bf60
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c5766beb87626efd11ba50422d5f811d1ae1d91e
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56632339"
---
# <a name="ltstringsgt-element-bootstrapper"></a>&lt;Řetězce&gt; – element (zaváděcí nástroj)
Definuje lokalizované řetězce pro názvy produktů, názvů balíčků a chybové zprávy instalace.

## <a name="syntax"></a>Syntaxe

```xml
<Strings>
    <String
        Name
    >
    </String>
</Strings>
```

## <a name="elements-and-attributes"></a>Elementy a atributy
 `Strings` Element je podřízeným prvkem `Package` elementu. Nemá žádné atributy.

## <a name="string"></a>String
 `String` Element je podřízeným prvkem `Strings` elementu. A `Strings` element může obsahovat jeden nebo více `String` elementy.

 `String` má následující atribut.

|Atribut|Popis|
|---------------|-----------------|
|`Name`|Povinný parametr. Název řetězce.|

## <a name="example"></a>Příklad
 Následující příklad kódu určuje všechny anglické řetězce pro [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] Instalační služby.

```xml
<Strings>
    <String Name="DisplayName">.NET Framework 2.0</String>
    <String Name="Culture">en</String>
    <String Name="AdminRequired">Administrator permissions are required to install the .NET Framework 2.0. Contact your administrator.</String>
    <String Name="InvalidPlatformWin9x">Installation of the .NET Framework 2.0 is not supported on Windows 95. Contact your application vendor.</String>
    <String Name="InvalidPlatformWinNT">Installation of the .NET Framework 2.0 is not supported on Windows NT 4.0. Contact your application vendor.</String>
    <String Name="InvalidPlatformIE">Installation of the .NET Framework 2.0 requires Internet Explorer 5.01 or greater. Contact your application vendor.</String>
    <String Name="InvalidPlatformArchitecture">This version of the .NET Framework 2.0 is not supported on a 64-bit operating system. Contact your application vendor.</String>
    <String Name="WindowsInstallerImproperInstall">Due to an error with Windows Installer, the installation of the .NET Framework 2.0 cannot proceed.</String>
    <String Name="AnotherInstanceRunning">Another instance of setup is already running. The running instance must complete before this setup can proceed.</String>
    <String Name="BetaNDPFailure">A beta version of the .NET Framework was detected on the computer. Uninstall any previous beta versions of .NET Framework before continuing.</String>
    <String Name="GeneralFailure">A failure occurred attempting to install the .NET Framework 2.0.</String>
    <String Name="DotNetFXExe">http://go.microsoft.com/fwlink/?LinkId=37283</String>
    <String Name="InstMsiAExe">http://go.microsoft.com/fwlink/?LinkId=37285</String>
    <String Name="Msi30Exe">http://go.microsoft.com/fwlink/?LinkId=37287</String>
</Strings>
```

## <a name="see-also"></a>Viz také:
- [\<Balíček > – element](../deployment/package-element-bootstrapper.md)