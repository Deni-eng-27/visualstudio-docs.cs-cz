---
title: Přidávání přepínačů příkazového řádku | Microsoft Docs
ms.date: 11/04/2016
ms.topic: how-to
helpviewer_keywords:
- command-line switches, adding
- command-line switches, retrieving
- IVsAppCommandLine::GetOption method
- command line, switches
ms.assetid: 8bbbd87e-76fe-4fb5-8ef9-65f5e31967cf
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bb4abf5352ac6ad78852bd3224df0b22784470db
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85903477"
---
# <a name="add-command-line-switches"></a>Přidat přepínače příkazového řádku
Můžete přidat přepínače příkazového řádku, které se použijí pro VSPackage při spuštění *devenv.exe* . Slouží <xref:Microsoft.VisualStudio.Shell.ProvideAppCommandLineAttribute> k deklaraci názvu přepínače a jeho vlastností. V tomto příkladu je přidán přepínač MySwitch pro podtřídu VSPackage s názvem **AddCommandSwitchPackage** bez argumentů a automaticky načtený rozhraní VSPackage.

```csharp
[ProvideAppCommandLine("MySwitch", typeof(AddCommandSwitchPackage), Arguments = "0", DemandLoad = 1)]
```

 Pojmenované parametry jsou uvedeny v následujících popisech.

|Název|Popis|
|-|-|
| Arguments | Počet argumentů pro přepínač. Může být "*" nebo seznam argumentů. |
| Výzvu DemandLoad | Pokud je tato hodnota nastavená na hodnotu 1, načtěte VSPackage automaticky, jinak nastavte na 0. |
| HelpString | Řetězec nebo ID prostředku v řetězci, který se má zobrazit v **devenv/?** |
| Název | Přepínač. |
| PackageGuid | Identifikátor GUID balíčku |

 První hodnota argumentu je obvykle 0 nebo 1. Pomocí speciální hodnoty * lze označit, že celý zbytek příkazového řádku je argumentem. To může být užitečné pro scénáře ladění, kdy uživatel musí předat řetězec příkazu ladicího programu.

 Hodnota výzvu DemandLoad je buď `true` (1), nebo `false` (0) značí, že se VSPackage má načíst automaticky.

 Hodnota HelpString je ID prostředku řetězce, který se zobrazí v **devenv/?** Zobrazení help. Tato hodnota by měla být ve formátu "#nnn", kde NNN je celé číslo. Hodnota řetězce v souboru prostředků by měla končit znakem nového řádku.

 Hodnota name je název přepínače.

 Hodnota PackageGuid je identifikátor GUID balíčku, který implementuje tento přepínač. Rozhraní IDE používá tento identifikátor GUID k nalezení VSPackage v registru, pro který je použit přepínač příkazového řádku.

## <a name="retrieve-command-line-switches"></a>Načtení přepínačů příkazového řádku
 Po načtení balíčku můžete načíst přepínače příkazového řádku, a to provedením následujících kroků.

1. V implementaci balíčku VSPackage <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> zavolejte na, `QueryService` <xref:Microsoft.VisualStudio.Shell.Interop.SVsAppCommandLine> aby se získalo <xref:Microsoft.VisualStudio.Shell.Interop.IVsAppCommandLine> rozhraní.

2. Zavolejte <xref:Microsoft.VisualStudio.Shell.Interop.IVsAppCommandLine.GetOption%2A> k načtení přepínačů příkazového řádku, které zadal uživatel.

   Následující kód ukazuje, jak zjistit, zda uživatel zadal přepínač příkazového řádku MySwitch:

```csharp
IVsAppCommandLine cmdline = (IVsAppCommandLine)GetService(typeof(SVsAppCommandLine));

int isPresent = 0;
string optionValue = "";

cmdline.GetOption("MySwitch", out isPresent, out optionValue);
```

 Je vaší zodpovědností kontrolovat přepínače příkazového řádku při každém načtení balíčku.

## <a name="see-also"></a>Viz také
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsAppCommandLine>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A>
- [Devenv – přepínače příkazového řádku](../ide/reference/devenv-command-line-switches.md)
- [Nástroj CreatePkgDef](../extensibility/internals/createpkgdef-utility.md)
- [. Soubory pkgdef](https://devblogs.microsoft.com/visualstudio/whats-a-pkgdef-and-why/)
