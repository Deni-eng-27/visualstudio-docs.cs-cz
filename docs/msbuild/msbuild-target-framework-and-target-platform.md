---
title: Cílová architektura a cílová platforma nástroje MSBuild | Microsoft Docs
description: Naučte se, jak vytvořit projekt MSBuild pro spuštění na cílové .NET Framework verzi a cílovou platformu nebo softwarovou architekturu.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: df6517c5-edd6-4cc4-97ad-b3cdfc78e799
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d29c4e4659e8e6a5564e3fb41f54615bf29171d2
ms.sourcegitcommit: 1a36533f385e50c05f661f440380fda6386ed3c1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/30/2020
ms.locfileid: "93049098"
---
# <a name="msbuild-target-framework-and-target-platform"></a>Cílová architektura a cílová platforma nástroje MSBuild

Projekt může být sestaven pro spuštění na *cílovém rozhraní* , což je konkrétní verze .NET Framework a *cílovou platformu* , která je konkrétní softwarovou architekturou.  Můžete například cílit na aplikaci tak, aby běžela na .NET Framework 2,0 na 32 platformě, která je kompatibilní s řadou procesorů 80x86 (x86). Kombinace cílového rozhraní a cílové platformy je označována jako *cílový kontext* .

> [!IMPORTANT]
> Tento článek ukazuje starý způsob, jak zadat cílovou architekturu. Projekty ve stylu sady SDK umožňují různé TargetFramework, jako je netstandard. Další informace naleznete v tématu [cílová rozhraní](/dotnet/standard/frameworks).

## <a name="target-framework-and-profile"></a>Cílová architektura a profil

 Cílová architektura je konkrétní verze .NET Framework, na které je projekt sestaven. Specifikace cílové architektury je povinná, protože umožňuje funkce kompilátoru a odkazy na sestavení, které jsou výhradně pro tuto verzi rozhraní.

 V současné době jsou k dispozici následující verze .NET Framework pro použití:

- .NET Framework 2,0 (zahrnuté v aplikaci Visual Studio 2005)

- .NET Framework 3,0 (zahrnuté v systému Windows Vista)

- .NET Framework 3,5 (zahrnuté v aplikaci Visual Studio 2008)

- .NET Framework 4.5.2

- .NET Framework 4,6 (zahrnuté v aplikaci Visual Studio 2015)

- .NET Framework 4.6.1

- .NET Framework 4.6.2

- .NET Framework 4,7

- .NET Framework 4.7.1

- .NET Framework 4.7.2

- .NET Framework 4,8

Verze .NET Framework se od sebe liší v seznamu sestavení, která jsou dostupná pro referenci. Například nemůžete sestavovat aplikace Windows Presentation Foundation (WPF), pokud projekt necílí na .NET Framework verze 3,0 nebo vyšší.

Cílová architektura je určena ve `TargetFrameworkVersion` vlastnosti v souboru projektu. Cílovou architekturu projektu můžete změnit pomocí stránky vlastností projektu v integrovaném vývojovém prostředí (IDE) sady Visual Studio. Další informace najdete v tématu [Postup: cílení na verzi .NET Framework](../ide/visual-studio-multi-targeting-overview.md). Dostupné hodnoty pro `TargetFrameworkVersion` jsou `v2.0` ,, `v3.0` , `v3.5` `v4.5.2` , `v4.6` , `v4.6.1` , `v4.6.2` , `v4.7` ,, a `v4.7.1` `v4.7.2` `v4.8` .

```xml
<TargetFrameworkVersion>v4.0</TargetFrameworkVersion>
```

 *Cílový profil* je podmnožinou cílového rozhraní. Například profil klienta .NET Framework 4 neobsahuje odkazy na sestavení nástroje MSBuild.

 > [!NOTE]
 > Cílové profily platí pouze pro [přenosné knihovny tříd](/dotnet/standard/cross-platform/cross-platform-development-with-the-portable-class-library).

 Cílový profil je zadán ve `TargetFrameworkProfile` vlastnosti v souboru projektu. Cílový profil můžete změnit pomocí ovládacího prvku cílový – rozhraní na stránkách vlastností projektu v rozhraní IDE.

```xml
<TargetFrameworkVersion>v4.0</TargetFrameworkVersion>
<TargetFrameworkProfile>Client</TargetFrameworkProfile>
```

## <a name="target-platform"></a>Cílová platforma

 *Platforma* je kombinací hardwaru a softwaru, který definuje konkrétní běhové prostředí. Příklad:

- `x86` Určuje 32 operační systém Windows, který běží na procesoru Intel 80x86 nebo jeho ekvivalent.

- `x64` Určuje 64 operační systém Windows, který běží na procesoru Intel x64 nebo který je ekvivalentní.

- `Xbox` označuje platformu Microsoft Xbox 360.

*Cílová platforma* je konkrétní platforma, na které je projekt sestaven. Cílová platforma je určena ve `PlatformTarget` vlastnosti Build v souboru projektu. Cílovou platformu můžete změnit pomocí stránky vlastností projektu nebo **Configuration Manager** v integrovaném vývojovém prostředí.

```xml
<PropertyGroup>
   <PlatformTarget>x86</PlatformTarget>
</PropertyGroup>

```

*Cílová konfigurace* je podmnožinou cílové platformy. Například `x86` `Debug` konfigurace nezahrnuje většinu optimalizací kódu. Cílová konfigurace je určena ve `Configuration` vlastnosti Build v souboru projektu. Cílovou konfiguraci můžete změnit pomocí stránky vlastností projektu nebo **Configuration Manager** .

```xml
<PropertyGroup>
   <PlatformTarget>x86</PlatformTarget>
   <Configuration>Debug</Configuration>
</PropertyGroup>

```

## <a name="see-also"></a>Viz také

- [Cílení na více verzí](../msbuild/msbuild-multitargeting-overview.md)
