---
title: Dialogové okno Upřesnit nastavení zabezpečení
ms.date: 06/27/2018
ms.technology: vs-ide-deployment
ms.topic: reference
f1_keywords:
- vs.err.debug_in_zone_no_hostproc
helpviewer_keywords:
- Advanced Security Settings dialog box
ms.assetid: 2e7aefe9-6d20-4f3e-b257-aee1ebcc6f5d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e1fcc3d09e43fc5358cbe507c5045c16cc9f8cf9
ms.sourcegitcommit: 85d66dc9fea3fa49018263064876b15aeb6f9584
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/24/2019
ms.locfileid: "68461866"
---
# <a name="advanced-security-settings-dialog-box"></a>dialogové okno Upřesnit nastavení zabezpečení

Toto dialogové okno umožňuje zadat nastavení zabezpečení související s laděním v zóně.

![Dialogové okno Upřesnit nastavení zabezpečení v aplikaci Visual Studio](../media/advanced-security-settings.png)

Chcete-li získat přístup k tomuto dialogovému oknu, vyberte uzel projektu v **Průzkumník řešení**a potom v nabídce **projekt** klikněte na příkaz **vlastnosti**. Když se zobrazí **Návrhář projektu** , klikněte na kartu **zabezpečení** . Na stránce **zabezpečení** vyberte **Povolit nastavení zabezpečení ClickOnce**, klikněte na **Toto je aplikace s částečným vztahem důvěryhodnosti**a pak klikněte na **Upřesnit**.

## <a name="uielement-list"></a>UIElement – seznam

**Udělit aplikaci přístup k jejímu původnímu umístění**

Pokud zaškrtnete toto políčko, aplikace bude mít přístup k webu nebo ke sdílené složce na serveru, na které je publikovaná. Ve výchozím nastavení je tato možnost vybraná.

**Ladit tuto aplikaci, jako kdyby byla stažena z následující adresy URL**

Pokud je nutné, aby aplikace získala přístup k webu nebo ke sdílené složce na serveru, která odpovídá **instalační adrese URL** zadané na stránce **publikování** , zadejte tuto adresu URL sem. Tato možnost je k dispozici pouze v případě, že je vybrána možnost **udělit aplikaci přístup k jejímu webu původu** .

## <a name="see-also"></a>Viz také:

- [Stránka Zabezpečení, Návrhář projektu](../../ide/reference/security-page-project-designer.md)