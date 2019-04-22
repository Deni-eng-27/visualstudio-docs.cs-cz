---
title: Automatizace instalace pomocí souboru odpovědí.
description: Zjistěte, jak vytvořit soubor odpovědi JSON, která pomáhá automatizovat instalaci sady Visual Studio
ms.date: 03/30/2019
ms.custom: seodec18
ms.topic: conceptual
helpviewer_keywords:
- response file
- automate
- installation
- command-line
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: eb822a275f55b8c0f833f0c284aba2fd663a27fd
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2019
ms.locfileid: "58790573"
---
# <a name="how-to-define-settings-in-a-response-file"></a>Definování nastavení v souboru odpovědí.

Správci, kteří si nasadí sady Visual Studio můžete určit soubor odpovědí s použitím `--in` parametr, jako v následujícím příkladu:

```cmd
vs_enterprise.exe --in customInstall.json
```

Soubory odpovědí jsou [JSON](http://json-schema.org/) soubory, jejichž obsah zrcadlí argumenty příkazového řádku.  Obecně platí, že pokud parametr příkazového řádku nepřijímá žádné argumenty (například `--quiet`, `--passive`atd), hodnota v souboru odpovědí musí být true nebo false.  Pokud má argument (například `--installPath <dir>`), hodnota v souboru odpovědí by měl být řetězec.  Pokud má argument a může být více než jednou v příkazovém řádku (například `--add <id>`), měla by být pole řetězců.

Parametry, které jsou určeny na příkazový řádek přepsání nastavení ze souboru odpovědí s výjimkou při parametry trvat více vstupů (například `--add`). Pokud máte více vstupů, vstupy zadané na příkazovém řádku jsou sloučeny s nastavení ze souboru odpovědí.

## <a name="setting-a-default-configuration-for-visual-studio"></a>Nastavuje se výchozí konfigurace pro sadu Visual Studio

Pokud jste vytvořili mezipaměť rozložení sítě se `--layout`, počáteční `response.json` soubor se vytvoří v rozložení. Pokud vytvoříte částečné rozložení, tento soubor odpovědí obsahuje úlohy a jazyky, které byly součástí rozložení.  Spuštění instalačního programu z tohoto rozložení automaticky používá tento soubor response.json vybere úlohy a komponenty, které jsou součástí rozložení.  Uživatelé mohou stále zaškrtněte nebo zrušte všechny úlohy v nastavení uživatelského rozhraní před instalací sady Visual Studio.

Správci, kteří vytvářejí rozložení můžete upravit `response.json` souboru v rozložení a výchozí nastavení, které jejich uživatelům zobrazit při instalaci sady Visual Studio z rozložení ovládacího prvku.  Například, pokud správce chce, aby se určité úlohy a komponenty, které jsou ve výchozím nastavení nainstalované, mohou nakonfigurovat `response.json` souboru je přidat.

Při spuštění instalačního programu sady Visual Studio ze složky rozložení, ho _automaticky_ používá soubor odpovědí ve složce rozložení.  Není nutné použít `--in` možnost.

Můžete aktualizovat `response.json` soubor, který je vytvořen ve složce aplikace offline rozložení pro definování výchozí nastavení pro uživatele, kteří si nainstalují z tohoto rozložení.

> [!WARNING]
> Je velmi důležité ponechat existující vlastnosti, která byla definována při vytváření rozložení.

Základní `response.json` soubor v rozložení by měl vypadat podobně jako v následujícím příkladu, s tím rozdílem, že by měl obsahovat hodnotu pro produkt a kanál, který chcete nainstalovat:

::: moniker range="vs-2017"

```json
{
  "installChannelUri": ".\\ChannelManifest.json",
  "channelUri": "https://aka.ms/vs/15/release/channel",
  "installCatalogUri": ".\\Catalog.json",
  "channelId": "VisualStudio.15.Release",
  "productId": "Microsoft.VisualStudio.Product.Enterprise"
}
```

::: moniker-end

::: moniker range="vs-2019"

```json
{
  "installChannelUri": ".\\ChannelManifest.json",
  "channelUri": "https://aka.ms/vs/16/release/channel",
  "installCatalogUri": ".\\Catalog.json",
  "channelId": "VisualStudio.16.Release",
  "productId": "Microsoft.VisualStudio.Product.Enterprise"
}
```

::: moniker-end

Při vytvoření nebo aktualizaci rozložení, je také vytvoří soubor response.template.json.  Tento soubor obsahuje všechny úlohy, komponenty a jazyků, které lze použít.  Tento soubor je k dispozici jako šablona pro co může být součástí vlastní instalace.  Správci mohou používat tento soubor jako výchozí bod pro vlastní odpovědi souboru.  Odeberte ID pro takové věci, které nechcete k instalaci a uložit v souboru odpovědí.  Neupravujte soubor response.template.json nebo vaše změny budou ztraceny, jakmile dojde k aktualizaci rozložení.

## <a name="example-layout-response-file-content"></a>Obsah souboru odezvy příklad rozložení

Následující příklad nainstaluje Visual Studio Enterprise s šest běžné úlohy a komponenty a jazyky angličtinu a francouzštinu uživatelského rozhraní. V tomto příkladu můžete použít jako šablonu; Stačí změňte úlohy a komponenty na ty, které chcete nainstalovat:

::: moniker range="vs-2017"

```json
{
  "installChannelUri": ".\\ChannelManifest.json",
  "channelUri": "https://aka.ms/vs/15/release/channel",
  "installCatalogUri": ".\\Catalog.json",
  "channelId": "VisualStudio.15.Release",
  "productId": "Microsoft.VisualStudio.Product.Enterprise",

  "installPath": "C:\\VS2017",
  "quiet": false,
  "passive": false,
  "includeRecommended": true,
  "norestart": false,

  "addProductLang": [
    "en-US",
    "fr-FR"
    ],

    "add": [
        "Microsoft.VisualStudio.Workload.ManagedDesktop",
        "Microsoft.VisualStudio.Workload.Data",
        "Microsoft.VisualStudio.Workload.NativeDesktop",
        "Microsoft.VisualStudio.Workload.NetWeb",
        "Microsoft.VisualStudio.Workload.Office",
        "Microsoft.VisualStudio.Workload.Universal",
        "Component.GitHub.VisualStudio"
    ]
}
```

::: moniker-end

::: moniker range="vs-2019"

```json
{
  "installChannelUri": ".\\ChannelManifest.json",
  "channelUri": "https://aka.ms/vs/16/release/channel",
  "installCatalogUri": ".\\Catalog.json",
  "channelId": "VisualStudio.16.Release",
  "productId": "Microsoft.VisualStudio.Product.Enterprise",

  "installPath": "C:\\VS2019",
  "quiet": false,
  "passive": false,
  "includeRecommended": true,
  "norestart": false,

  "addProductLang": [
    "en-US",
    "fr-FR"
    ],

    "add": [
        "Microsoft.VisualStudio.Workload.ManagedDesktop",
        "Microsoft.VisualStudio.Workload.Data",
        "Microsoft.VisualStudio.Workload.NativeDesktop",
        "Microsoft.VisualStudio.Workload.NetWeb",
        "Microsoft.VisualStudio.Workload.Office",
        "Microsoft.VisualStudio.Workload.Universal",
        "Component.GitHub.VisualStudio"
    ]
}
```

::: moniker-end

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [ID úloh a komponent sady Visual Studio](workload-and-component-ids.md)
