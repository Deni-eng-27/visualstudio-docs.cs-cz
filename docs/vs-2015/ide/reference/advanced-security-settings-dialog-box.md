---
title: Upřesnit nastavení zabezpečení – dialogové okno | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vs.err.debug_in_zone_no_hostproc
- vs.err.debug_in_zone_no_hostproc:11310
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Advanced Security Settings dialog box
ms.assetid: 2e7aefe9-6d20-4f3e-b257-aee1ebcc6f5d
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 283428e4d4b2c81179d8dbd8ff6200c1d7140eae
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54758723"
---
# <a name="advanced-security-settings-dialog-box"></a>Dialogové okno Upřesnit nastavení zabezpečení
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Toto dialogové okno umožňuje zadat nastavení zabezpečení související s laděním v zóně.  
  
 Pro přístup k tomuto dialogovému oknu, vyberte uzel projektu v **Průzkumníka řešení**a potom na **projektu** nabídky, klikněte na tlačítko **vlastnosti**. Když **Návrháře projektu** se zobrazí, klikněte na tlačítko **zabezpečení** kartu. Na **zabezpečení** stránce **povolit nastavení zabezpečení ClickOnce**, klikněte na tlačítko **Toto je aplikace s částečnou důvěryhodností**a potom klikněte na tlačítko **Upřesnit**.  
  
## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní  
 **Ladit tuto aplikaci s vybranou sadou oprávnění**  
 Pokud toto políčko zaškrtnete, sadu oprávnění vybrat na **zabezpečení** stránky se používá během ladění. Ve výchozím nastavení je tato možnost vybrána.  
  
 Pro ladění v zóně zabezpečení fungovat, musí být povolena tato možnost; Navíc **povolit hostující proces sady Visual Studio** možnost (k dispozici na **ladění** stránku **Návrháře projektu**) musí být povolené.  
  
 Pro projekty aplikace WPF webového prohlížeče **Ladit tuto aplikaci s vybranou sadou oprávnění** možnost je zkontrolovaný a zakázaný.  
  
 **Udělit aplikaci přístup ke stránce jejího původu**  
 Pokud toto políčko zaškrtnete, aplikace přístup na webový server nebo sdílená složka serveru, na kterém je publikována. Ve výchozím nastavení je tato možnost vybrána.  
  
 **Ladit tuto aplikaci, jako kdyby byla stažena z následující adresy URL**  
 Pokud budete muset povolit aplikaci přístup k webu nebo sdílená složka na serveru odpovídající **adresa URL instalace** jste zadali na **publikovat** stránky, zadejte tuto adresu URL. Tato možnost je dostupná jenom v případě **udělit aplikaci přístup ke stránce jejího původu** zaškrtnuto.  
  
## <a name="see-also"></a>Viz také  
 [Stránka Zabezpečení, Návrhář projektu](../../ide/reference/security-page-project-designer.md)
