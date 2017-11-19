---
title: "Zakažte nebo přesunout do mezipaměti balíček | Microsoft Docs"
description: "Zakázat, povolit nebo přesunout do mezipaměti balíček pro nasazení v sadě Visual Studio."
ms.date: 04/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cache
- nocache
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 2429993A-3F0E-41C5-9562-FEA6AE994440
author: heaths
ms.author: heaths
manager: ghogen
ms.openlocfilehash: 768446797558dec103927f251867ab78cd3edf0a
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
---
# <a name="disable-or-move-the-package-cache"></a>Zakažte nebo přesunout do mezipaměti balíčku

Balíček mezipaměti poskytuje zdroj balíčků nainstalovaných v případě, že potřebujete opravit Visual Studio nebo jiné související produkty v případech, kdy máte bez připojení k Internetu. Některé jednotky nebo systému nastavit ups, ale nemusí chcete zachovat tyto balíčky kolem.
Instalační program stáhne je podle potřeby, takže pokud chcete uložit nebo obnovit místa na disku můžete zakázat nebo přesunout do mezipaměti balíčku.

## <a name="disable-the-package-cache"></a>Zakázání ukládání do mezipaměti balíčku

Před instalací, upravit nebo opravte Visual Studio nebo jiné produkty s novým instalačním programem, můžete spustit instalační program se `--nocache` přepnout na Instalační služby.

```
"%ProgramFiles(x86)%\Microsoft Visual Studio\Installer\vs_installer.exe" --nocache
```

Všechny operace, které můžete provést na některý z produktů odeberete všechny existující balíčky pro tento produkt a vyhnout se ukládají všechny balíčky po jejich instalaci. Pokud změníte nebo opravte Visual Studio a balíčky jsou požadované, bude ji automaticky stáhnout nebo odebrat po jejich instalaci.

Pokud chcete znovu povolit mezipaměť, předat `--cache` místo. Pouze balíčky, které jsou požadovány bude do mezipaměti, takže pokud je nutné obnovit všechny balíčky opravte Visual Studio před odpojením z vaší sítě.

```
"%ProgramFiles(x86)%\Microsoft Visual Studio\Installer\vs_installer.exe" repair --passive --norestart --cache
```

Můžete také nastavit `KeepDownloadedPayloads` [zásad registru](set-defaults-for-enterprise-deployments.md) zakázání ukládání do mezipaměti před nainstalovat, upravit nebo opravte Visual Studio.

## <a name="move-the-package-cache"></a>Přesuňte balíček mezipaměti

Obvyklé konfigurace systému je tak, aby měl Windows nainstalovanou na SSD s větší pevný disk (nebo více) pro vývoj potřebuje, jako je například zdrojového kódu, binární soubory programu a další. Pokud chcete pracovat offline místo přesunutím mezipaměti balíčku.

V současné době můžete provést jen pokud jste nastavili `CachePath` [zásad registru](set-defaults-for-enterprise-deployments.md) před nainstalovat, upravit nebo opravte Visual Studio.

## <a name="get-support"></a>Získat podporu
V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránku Tipy pro odstraňování potíží. Taky můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj v prostředí Visual Studio IDE nebo ke sdílení návrh s nám na [UserVoice](https://visualstudio.uservoice.com/forums/121579). Můžete sledovat problémy produktu v [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/)a klást otázky a odpovědi. Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím našich [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio) (vyžaduje [Githubu](https://github.com/) účtu).

## <a name="see-also"></a>Viz také

 * [Instalaci sady Visual Studio](install-visual-studio.md)
 * [Výchozí nastavení pro nasazení v podnicích](set-defaults-for-enterprise-deployments.md)
 * [Používání parametrů příkazového řádku pro instalaci sady Visual Studio](use-command-line-parameters-to-install-visual-studio.md)
