---
title: 'Postupy: nastavení umístění souboru vlastního protokolu pro chyby nasazení ClickOnce | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 647eed5145d9d80f9fc62249763726a5940a7345
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-set-a-custom-log-file-location-for-clickonce-deployment-errors"></a>Postupy: Nastavení vlastního umístění souboru protokolu pro chyby nasazení ClickOnce
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] udržuje aktivační soubory protokolu pro všechna nasazení. Tyto protokoly dokumentu všechny chyby týkající se instalace a inicializace [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení. Ve výchozím nastavení [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] vytvoří jeden soubor protokolu pro každou aktivaci nasazení. Ukládá tyto soubory protokolu ve složce dočasných souborů Internetu. Soubor protokolu pro nasazení se zobrazí uživateli, když dojde k selhání aktivace a uživatel klikne na **podrobnosti** v dialogové okno chyby.  
  
 Toto chování můžete změnit pro konkrétního klienta pomocí Editoru registru (**regedit.exe**) Chcete-li nastavit cestu k souboru vlastního protokolu. V takovém případě [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] protokoly aktivace úspěchů a neúspěchů pro všechna nasazení v jednom souboru.  
  
> [!CAUTION]
>  Pokud Editor registru používán správně, může způsobit vážné problémy, které mohou vyžadovat přeinstalaci operačního systému. Pomocí Editoru registru na vlastní nebezpečí.  
  
> [!NOTE]
>  Je potřeba zkrátit nebo odstranit v souboru protokolu příležitostně zabránit příliš zvětšují.  
  
 Následující postup popisuje, jak nastavit vlastního umístění souboru protokolu pro jednoho klienta.  
  
### <a name="to-set-a-custom-log-file-location"></a>Chcete-li nastavit vlastního umístění souboru protokolu  
  
1.  Otevřete **Regedit.exe**.  
  
2.  Přejděte na uzel `HKCU\Software\Classes\Software\Microsoft\Windows\CurrentVersion\Deployment`.  
  
3.  Nastavte hodnotu řetězce `LogFilePath` úplná cesta a název souboru vašeho upřednostňovaného vlastní umístění protokolu.  
  
     Tímto umístěním musí být v adresáři, do které má uživatel oprávnění k zápisu. Například v systému Windows Vista, vytvořte následující strukturu složek a nastavení `LogFilePath` na C:\Users\\< uživatelské jméno\>\Documents\Logs\ClickOnce\installation.log.  
  
## <a name="see-also"></a>Viz také  
 [Řešení potíží s nasazením ClickOnce](../deployment/troubleshooting-clickonce-deployments.md)