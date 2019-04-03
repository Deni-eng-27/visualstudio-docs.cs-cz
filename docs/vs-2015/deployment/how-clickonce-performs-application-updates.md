---
title: Jak ClickOnce provádí aktualizaci aplikací | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- updates, ClickOnce
- ClickOnce deployment, updates
- deploying applications [ClickOnce], application updates
ms.assetid: d54313c2-cf0c-420d-b151-99953a95f0bb
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d2e8a3c1054219bb7d5b0f9a9ef5e710786344e4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54767068"
---
# <a name="how-clickonce-performs-application-updates"></a>Jak ClickOnce provádí aktualizaci aplikací
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Informace o verzi souboru, zadaný v manifestu nasazení aplikace ClickOnce využívající rozhodnout, jestli se má aktualizovat soubory aplikace. Po zahájení aktualizace ClickOnce pomocí techniky označované jako *soubor opravy* aby se zabránilo redundantní stahování souborů aplikace.  
  
## <a name="file-patching"></a>Oprava souborů  
 Při aktualizaci aplikace ClickOnce všechny soubory pro novou verzi aplikace nebude stahovat Pokud soubory se změnily. Místo toho porovná podpisy hodnoty hash souborů zadaných v manifestu aplikace pro aktuální aplikaci proti podpisy v manifestu pro novou verzi. Pokud se podpisy souboru liší, ClickOnce, soubory ke stažení na novou verzi. Pokud se podpisy shodují, soubor nebyl změněn z jedné verze na další. V tomto případě ClickOnce zkopíruje existující soubor a používá ho v nové verzi aplikace. Tento postup brání ClickOnce museli stáhnout celý aplikaci znovu spustit, i v případě, že pouze jeden nebo dva soubory se změnily.  
  
 Soubor opravy také funguje pro sestavení, které se stáhnou na vyžádání pomocí <xref:System.Deployment.Application.ApplicationDeployment.DownloadFileGroup%2A> a <xref:System.Deployment.Application.ApplicationDeployment.DownloadFileGroupAsync%2A> metody.  
  
 Pokud používáte sadu Visual Studio ke kompilaci vaší aplikace, vygeneruje se nové podpisy hodnoty hash pro všechny soubory pokaždé, když se je znovu sestavit celý projekt. V takovém případě všechna sestavení se stáhne do klienta, i když možná změnily pouze několik sestavení.  
  
 Oprava souborů pro soubory, které jsou označeny jako data a uloženy v adresáři dat nefunguje. Tyto budou staženy vždy bez ohledu na hodnoty hash podpisu souboru. Další informace o do adresáře dat, naleznete v tématu [Přístup k lokálním a vzdáleným datům v aplikacích ClickOnce](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md).  
  
## <a name="see-also"></a>Viz také  
 [Výběr strategie aktualizace ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md)   
 [Výběr strategie nasazení ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md)
