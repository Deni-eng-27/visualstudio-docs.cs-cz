---
title: "Na virtuálním počítači Azure pomocí sady Visual Studio | Microsoft Docs"
description: "Další informace o použití sady Visual Studio na virtuální počítač Azure"
ms.date: 01/30/2018
ms.technology: vs-acquisition
ms.topic: article
helpviewer_keywords:
- azure services
- virtual machine; VM
- installation
- visual studio
author: PhilLee-MSFT
ms.author: phillee
manager: sacalla
ms.workload:
- multiple
ms.openlocfilehash: 6db5de6156472e1374075cb602f7ecabc92526e2
ms.sourcegitcommit: d6327b978661c0a745bf4b59f32d8171607803a3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/01/2018
---
# <a id="top"></a> Bitové kopie sady visual Studio na platformě Azure
Pomocí sady Visual Studio spuštěné v předkonfigurované Azure virtuálního počítače (VM) je nejjednodušší a nejrychlejší způsob, jak přechod od nic k prostředí vývoj nahoru a spuštěna.  Bitové kopie systému s různými konfiguracemi sady Visual Studio jsou k dispozici v [Azure Marketplace](https://portal.azure.com/). Stačí spustit virtuální počítač a vypnout můžete přejít.

Nové do Azure? [Vytvořit bezplatný účet Azure](https://azure.microsoft.com/free).

## <a name="what-configurations-and-versions-are-available"></a>Jaké konfigurace a verzí jsou k dispozici?
V Azure Marketplace najít Image pro nejnovější hlavní verze: Visual Studio 2017 a Visual Studio 2015.  Pro každou hlavní verzi, uvidíte původně vydaná (neboli "RTW') verze a"nejnovější"aktualizovaných verzí.  Pro každý z těchto různé verze najít edice Visual Studio Enterprise a Visual Studio Community.

|               Prodejní verze              |        Edice      |    Verze produktu    |
|:------------------------------------------:|:---------------------:|:---------------------:|
| Visual Studio 2017 - nejnovější (verze 15,5) | Enterprise, Community |     Verze 15.5.3    |
|         Visual Studio 2017 - RTW           | Enterprise, Community |     Verze 15.0.7    |
|   Visual Studio 2015 – nejnovější (Update 3)   | Enterprise, Community | Verze 14.0.25431.01 |
|         Visual Studio 2015 - RTW           | Žádné           |    Platnost pro obsluhu          |

> [!NOTE]
> V souladu s Microsoft obsluhy zásady, původně vydaná (neboli "RTW') verze sady Visual Studio 2015 vypršela pro obsluhu.  Visual Studio 2015 Update 3 je proto jenom zbývající verze nabízí pro produktovou řadu sady Visual Studio 2015.

Další informace najdete v tématu [zásad údržby Visual Studio](https://www.visualstudio.com/en-us/productinfo/vs-servicing-vs).

## <a name="what-features-are-installed"></a>Jaké funkce jsou nainstalovány?
Každý image obsahuje funkci doporučené nastavení pro tento edicí sady Visual Studio.  Obecně platí že instalační program obsahuje:

* Všechny dostupné úlohy, včetně doporučených volitelné součásti této úlohy
* .NET 4.6.2 a .NET 4.7 sady SDK, cílení balíčky a nástroje pro vývojáře
* Visual F#
* GitHub rozšíření pro Visual Studio
* Technologie LINQ to SQL nástroje

Toto je příkazového řádku, který používáme k instalaci sady Visual Studio, při vytváření bitové kopie:

```
    vs_enterprise.exe --allWorkloads --includeRecommended --passive ^
       add Microsoft.Net.Component.4.7.SDK ^
       add Microsoft.Net.Component.4.7.TargetingPack ^ 
       add Microsoft.Net.Component.4.6.2.SDK ^
       add Microsoft.Net.Component.4.6.2.TargetingPack ^
       add Microsoft.Net.ComponentGroup.4.7.DeveloperTools ^
       add Microsoft.VisualStudio.Component.FSharp ^
       add Component.GitHub.VisualStudio ^
       add Microsoft.VisualStudio.Component.LinqToSql
```

Pokud obrázky neobsahují funkce sady Visual Studio, kterou požadujete, zadejte tuto zpětnou vazbu prostřednictvím nástroje zpětnou vazbu (pravém horním rohu stránky).

## <a name="what-size-vm-should-i-choose"></a>Zvolte jakou velikost virtuálního počítače
Zajištění nového virtuálního počítače je snadné a Azure nabízí celou řadu velikostí virtuálních počítačů.  Stejně jako u jakékoli hardwaru akvizice, budete chtít vyvážit výkonu a nákladů.  Vzhledem k tomu, že Visual Studio je výkonný vícevláknové aplikace, budete chtít velikost virtuálního počítače, který obsahuje alespoň dva procesory a 7 GB paměti.  Další informace o nejnovější velikosti počítačů najdete v tématu [velikosti pro systém Windows virtuálních počítačů v Azure](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/sizes).

S Azure není neměnné vaše první vybrat – počáteční volbu můžete znovu vyvážit, změna velikosti virtuálního počítače.  Buď můžete zřídit nový virtuální počítač s více odpovídající velikost, nebo můžete změnit velikost vašeho stávajícího virtuálního počítače na jiný základní hardware.  Další informace najdete v tématu [Změna velikosti virtuálního počítače Windows](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/resize-vm).

## <a name="after-i-get-the-vm-running-then-what"></a>Po získat virtuální počítač spuštěn, poté co?
Visual Studio odpovídá modelu "vám přináší vlastní licence" v Azure.  Ano podobně jako instalace na speciální hardware, jeden z první kroků je licencování instalace Visual Studia.  Po přihlášení pomocí účtu Microsoft, který je spojen s předplatným Visual Studio můžete odemknout Visual Studio nebo Visual Studio s kódem product key můžete odemknout s počátečním nákupu.  Další informace najdete v tématu [přihlášení k sadě Visual Studio](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio) a [jak odemknout Visual Studio](https://docs.microsoft.com/en-us/visualstudio/ide/how-to-unlock-visual-studio).

## <a name="after-i-build-out-the-dev-vm-how-do-i-save-capture-it-for-future-or-team-use"></a>Po I sestavení na dev virtuální počítač, jak lze uložit (snímek) pro budoucí nebo použijte team?

Spektrum vývojových prostředí je velký a skutečné náklady spojené s vytváření složitějších prostředí.  Bez ohledu na vašem prostředí configuration Azure vám ovšem zachování této investice snadno ukládání/zachytáváním virtuální počítač perfektně nakonfigurované jako "Základní bitová kopie' pro budoucí použití – pro sebe nebo pro ostatní členové týmu.  Potom při dalším spuštění nového virtuálního počítače, zřídit ze základní bitovou kopii, nikoli bitovou kopii Marketplace.

Jako rychlý přehled, budete muset nástroj sysprep a vypnutí spuštění virtuálního počítače, pak *zachycení (obrázek 1)* virtuální počítač jako bitovou kopii prostřednictvím uživatelského rozhraní portálu Azure.  Azure uloží `.vhd` soubor, který obsahuje bitovou kopii v účtu úložiště dle vlastního výběru.  Potom nová bitová kopie objeví jako prostředek obrázku v seznamu prostředků vaše předplatné.

<img src="media/capture-vm.png" alt="Capture an image through the Azure portal’s UI" style="border:3px solid Silver; display: block; margin: auto;"><center>*(Obrázek 1) Zaznamenejte bitovou kopii prostřednictvím uživatelského rozhraní portálu Azure.*</center>

Další informace najdete v tématu [zachycení virtuálního počítače na bitovou kopii](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/capture-image-resource).

  **Upozornění:** nezapomeňte sysprep virtuální počítač!  Pokud tento krok přeskočíte, Azure nemůže zřídit virtuální počítač z bitové kopie.

> [!NOTE]
> Stále platit náklady pro úložiště bitové kopie, ale, že je pravděpodobně přírůstkové náklady zanedbatelný ve srovnání s náklady na lidských zdrojů pro opětovné sestavení virtuálního počítače od začátku – pro každou osobu ve vašem týmu, který potřebuje virtuální počítač.  Například stojí několik odběru k vytvoření a uložení 127 GB image dobu jednoho měsíce, který je opakovaně použitelné všichni členové týmu.  Tyto náklady jsou však zanedbatelný ve srovnání s hodiny, kdy každý zaměstnanec investují vytváří a ověřit správnou konfiguraci dev pole pro vlastní použití.

Kromě toho vývojářských úloh nebo technologie potřebovat další škálování – jako jsou typy konfigurací vývoj a konfigurací s více počítači.  Azure DevTest Labs můžete použít k vytvoření _recepty_ který automatizovat vytváření vašeho zlaté Image a ke správě zásad pro váš tým je spuštěných virtuálních počítačů.  [Pomocí Azure DevTest Labs pro vývojáře](https://docs.microsoft.com/en-us/azure/devtest-lab/devtest-lab-developer-lab) je nejlepší zdroj pro další informace o DevTest Labs.

## <a name="next-steps"></a>Další kroky
Teď, když víte o předem nakonfigurovaná bitové kopie sady Visual Studio, dalším krokem je vytvoření nového virtuálního počítače:

* [Vytvoření virtuálního počítače prostřednictvím portálu Azure](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/quick-create-portal)
* [Virtuální počítače s Windows – přehled](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/overview)