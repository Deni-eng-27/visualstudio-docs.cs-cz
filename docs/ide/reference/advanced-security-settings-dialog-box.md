---
title: Upřesnit nastavení zabezpečení – dialogové okno | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.err.debug_in_zone_no_hostproc
helpviewer_keywords:
- Advanced Security Settings dialog box
ms.assetid: 2e7aefe9-6d20-4f3e-b257-aee1ebcc6f5d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a1dad7843d42aeaf0c2871f8b76c840a12cd4186
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="advanced-security-settings-dialog-box"></a>Dialogové okno Upřesnit nastavení zabezpečení
Toto dialogové okno umožňuje zadat nastavení zabezpečení související s laděním v zóně.  
  
 Pro přístup k tohoto dialogového okna, vyberte uzel projektu v **Průzkumníku řešení**a pak klikněte na **projektu** nabídky, klikněte na tlačítko **vlastnosti**. Když **Návrhář projektu** se zobrazí, klikněte na tlačítko **zabezpečení** kartě. Na **zabezpečení** vyberte **povolení nastavení zabezpečení ClickOnce**, klikněte na tlačítko **Toto je aplikace s částečnou důvěryhodností**a pak klikněte na tlačítko **Upřesnit**.  
  
## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní  
 **Tuto aplikaci s vybraným nastavením oprávnění pro ladění**  
 Pokud vyberete toto políčko, nastavení oprávnění vybrané na **zabezpečení** stránky se používá během ladění. Ve výchozím nastavení je tato možnost vybrána.  
  
 Pro ladění v zóně zabezpečení fungovat, musí být tato možnost povolená; Navíc **povolit sady Visual Studio proces hostování** možnost (k dispozici na **ladění** stránky **Návrhář projektu**) musí být povolena.  
  
 Pro aplikace WPF webového prohlížeče projekty **ladění tuto aplikaci s vybraným nastavením oprávnění** je zaškrtnuta možnost a zakázaná možnost.  
  
 **Udělit přístup k aplikaci do jeho lokality původu**  
 Pokud vyberete toto políčko, aplikaci přístup na webový server nebo sdílená složka serveru, na kterém je publikována. Ve výchozím nastavení je tato možnost vybrána.  
  
 **Ladění této aplikace, jako kdyby byly staženy z následující adresy URL**  
 Pokud budete muset povolit aplikaci pro přístup na webový server nebo sdílená složka serveru odpovídající **adresy URL instalace** jste zadali na **publikovat** stránky, zadejte tuto adresu URL. Tato možnost je dostupná jenom v případě **udělit přístup k aplikaci do jeho lokality původu** je vybrána.  
  
## <a name="see-also"></a>Viz také  
 [Stránka Zabezpečení, Návrhář projektu](../../ide/reference/security-page-project-designer.md)