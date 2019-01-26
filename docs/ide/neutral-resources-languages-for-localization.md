---
title: Neutrální jazyky zdrojů pro lokalizaci
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- localization [Visual Studio], resources
- NeutralResourcesLanguageAttribute class
- globalization [Visual Studio], resources
- resources [Visual Studio], fallback system
- culture, locating resources
- neutral resources
ms.assetid: ef064995-3b84-4698-a708-9689b7723533
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 513cd8295a3e25a171de6623ba706ce7dfb2a2e6
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54962102"
---
# <a name="neutral-resources-languages-for-localization"></a>Neutrální jazyky zdrojů pro lokalizaci

<xref:System.Resources.NeutralResourcesLanguageAttribute> Třída určuje jazykovou verzi prostředků zahrnuté v hlavním sestavení. Tento atribut se používá jako vylepšení výkonu, tak, aby <xref:System.Resources.ResourceManager> objekt neprohledává za prostředky, které jsou zahrnuty v hlavním sestavení.

 Následující kód ukazuje, jak nastavit jazyk neutrální prostředky. Kód je možné použít ve skriptu sestavení nebo v souboru AssemblyInfo.vb nebo AssemblyInfo.cs.

```vb
' Set neutral resources language for assembly.
<Assembly: NeutralResourcesLanguageAttribute("en")>
```

```csharp
// Set neutral resources language for assembly.
[assembly: NeutralResourcesLanguageAttribute("en")]
```

## <a name="see-also"></a>Viz také:

- <xref:System.Resources.ResourceManager>
- [Představení mezinárodních aplikací založených na prostředí .NET Framework](../ide/introduction-to-international-applications-based-on-the-dotnet-framework.md)
- [Hierarchická organizace zdrojů pro lokalizaci](../ide/hierarchical-organization-of-resources-for-localization.md)
- [Lokalizace aplikací](../ide/localizing-applications.md)
- [Globalizace a lokalizace aplikací](../ide/globalizing-and-localizing-applications.md)