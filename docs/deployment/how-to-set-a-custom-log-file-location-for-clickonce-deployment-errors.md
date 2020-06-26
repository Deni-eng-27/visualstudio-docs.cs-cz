---
title: Nastavení vlastního umístění souboru protokolu pro chyby nasazení ClickOnce
ms.date: 11/04/2016
ms.topic: how-to
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- troubleshooting ClickOnce deployments
- ClickOnce deployment, troubleshooting
- ClickOnce deployment, error logging
ms.assetid: 77424414-7f0e-4b99-94bb-ea130de92d09
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 05ffd1cf32f8c7ea93e63232f7026c6c926f9308
ms.sourcegitcommit: 3f491903e0c10db9a3f3fc0940f7b587fcbf9530
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/26/2020
ms.locfileid: "85382169"
---
# <a name="how-to-set-a-custom-log-file-location-for-clickonce-deployment-errors"></a>Postupy: nastavení vlastního umístění souboru protokolu pro chyby nasazení ClickOnce
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]udržuje soubory protokolu aktivace pro všechna nasazení. Tyto protokoly dokumentují všechny chyby, které se týkají instalace a inicializace [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení. Ve výchozím nastavení [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] vytvoří jeden soubor protokolu pro každou aktivaci nasazení. Tyto soubory protokolu se uloží do složky dočasných internetových souborů. Soubor protokolu pro nasazení se uživateli zobrazí, když dojde k selhání aktivace a uživatel klikne na **Podrobnosti** v dialogovém okně výsledné chyby.

 Toto chování můžete změnit pro konkrétního klienta pomocí Editoru registru (**regedit.exe**) a nastavit tak vlastní cestu k souboru protokolu. V takovém případě [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] protokoluje úspěšné a neúspěšné aktivace pro všechna nasazení v jednom souboru.

> [!CAUTION]
> Pokud používáte Editor registru nesprávně, může dojít k vážným problémům, které mohou vyžadovat přeinstalaci operačního systému. Editor registru použijte na vlastní riziko.

> [!NOTE]
> Soubor protokolu bude někdy potřeba zkrátit nebo odstranit, aby se zabránilo jeho většímu růstu.

 Následující postup popisuje, jak nastavit vlastní umístění souboru protokolu pro jednoho klienta.

### <a name="to-set-a-custom-log-file-location"></a>Nastavení vlastního umístění souboru protokolu

1. Otevřete **Regedit.exe**.

2. Přejděte k uzlu `HKCU\Software\Classes\Software\Microsoft\Windows\CurrentVersion\Deployment` .

3. Nastavte hodnotu řetězce `LogFilePath` na úplnou cestu a název souboru upřednostňovaného vlastního umístění protokolu.

     Toto umístění musí být v adresáři, ke kterému má uživatel oprávnění k zápisu. Například v systému Windows Vista vytvořte následující strukturu složek a nastavte `LogFilePath` ji na *C:\Users \\ \<username> \Documents\Logs\ClickOnce\installation.log*.

## <a name="see-also"></a>Viz také
- [Řešení potíží s nasazeními ClickOnce](../deployment/troubleshooting-clickonce-deployments.md)