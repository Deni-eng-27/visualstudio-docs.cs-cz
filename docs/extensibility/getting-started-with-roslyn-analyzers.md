---
title: Začínáme s Roslyn analyzátorů | Microsoft Docs
ms.date: 04/02/2018
ms.technology: vs-ide-sdk
ms.topic: article
ms.assetid: 367c2ec8-3059-46a5-9d1c-57bead0419e7
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 0546604c60a310531fb101515b08bf18ed3d98e6
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/03/2018
---
# <a name="getting-started-with-roslyn-analyzers"></a>Začínáme s Roslyn analyzátory

S analyzátorů za provozu, na základě projektu kódu v sadě Visual Studio rozhraní API autoři se dají dodávat analýzy kódu pro konkrétní domény jako součást jejich balíčků NuGet. Protože tyto analyzátorů jsou zapnuté kompilátoru platformou .NET (označován kódovým "Roslyn"), může vést k upozornění do vašeho kódu jako typ i předtím, než jste dokončili řádku (žádné další čekání na sestavení kódu ke zjišťování problémů). Analyzátory můžete také surface automatické kódu oprava prostřednictvím žárovky řádku Visual Studia umožnit vám vyčištění kódu okamžitě.

## <a name="getting-started"></a>Začínáme

[Analyzátorů za provozu kódu Roslyn úvod a návod](https://msdn.microsoft.com/magazine/dn879356.aspx)

[Přidání kódu opravy návod: Zadejte uživatelé opravy pro analyzátor problémy](https://msdn.microsoft.com/magazine/dn904670.aspx)

[Úvod a návod skutečných analyzátor Talk](http://channel9.msdn.com/events/Build/2015/3-725)

[Skutečné analyzátor Roslyn World](../extensibility/roslyn-analyzers-and-code-aware-library-for-immutablearrays.md) , můžete také shlédnout jako [komunikovat](http://channel9.msdn.com/events/Build/2015/3-725)

[Několik příkladů na githubu, které jsou seskupeny do tři druhy analyzátorů](https://github.com/dotnet/roslyn/blob/master/docs/analyzers/Analyzer%20Samples.md)

[Úvod a prohlídka několik analyzátorů komunikovat](http://channel9.msdn.com/Events/dotnetConf/2015/NET-Compiler-Platform-Roslyn-Analyzers-and-the-Rise-of-Code-Aware-Libraries)

## <a name="see-also"></a>Viz také

- [Přehled Roslyn analyzátory](../code-quality/roslyn-analyzers-overview.md)
- [Další dokumentace na webu github operačních systémů](https://github.com/dotnet/roslyn/tree/master/docs/analyzers)
- [Pravidla FxCop implementuje pomocí analyzátorů Roslyn na githubu](https://github.com/dotnet/roslyn/tree/master/src/Diagnostics/FxCop)