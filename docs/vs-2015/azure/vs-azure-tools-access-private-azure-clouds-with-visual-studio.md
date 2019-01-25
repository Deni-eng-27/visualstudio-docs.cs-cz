---
title: Přístup k privátní cloudy Azure
description: Zjistěte, jak získat přístup k prostředkům privátního cloudu s použitím sady Visual Studio.
author: ghogen
manager: jillfra
assetId: 9d733c8d-703b-44e7-a210-bb75874c45c8
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/13/2017
ms.author: ghogen
ms.openlocfilehash: ab0b6167a91f6cf6f5aecdcbcfb03bab62b96b6b
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54771553"
---
# <a name="accessing-private-azure-clouds-with-visual-studio"></a>Přístup k privátní cloudy Azure pomocí sady Visual Studio

Ve výchozím nastavení Visual Studio podporuje koncové body REST cloudu Azure. V tomto článku se dozvíte, jak pro použití certifikátu privátního cloudu a přístup k interakci s privátního cloudu ze sady Visual Studio.

1. Na portálu Azure pro privátní cloud stáhněte si soubor nastavení publikování nebo kontaktujte správce pro soubor nastavení publikování. (Tento soubor má příponu `.publishsettings`.)

1. V sadě Visual Studio **Průzkumníka serveru**, klikněte pravým tlačítkem myši **Azure** uzel a vyberte možnost **spravovat a filtrovat předplatná**.

    ![Spravovat předplatná příkaz](./media/vs-azure-tools-access-private-azure-clouds-with-visual-studio/IC790778.png)

1. V **spravovat předplatná Microsoft Azure** dialogového okna, vyberte **certifikáty** kartu a potom vyberte **Import**.

    ![Import certifikátů Azure](./media/vs-azure-tools-access-private-azure-clouds-with-visual-studio/IC790779.png)

1. V **předplatná Microsoft Azure Import** dialogového okna, vyberte **Procházet**.

    ![Procházet tlačítko v dialogovém okně Importovat předplatná Microsoft Azure](./media/vs-azure-tools-access-private-azure-clouds-with-visual-studio/browse-button.png)

1. V **otevřít** dialogové okno, přejděte do adresáře, kam jste uložili soubor nastavení publikování, vyberte soubor a pak vyberte **otevřít**.

    ![Vybrat soubor nastavení publikování](./media/vs-azure-tools-access-private-azure-clouds-with-visual-studio/select-publish-settings-file.png)

1. Po vrácení do **předplatná Microsoft Azure Import** dialogového okna, vyberte **Import**.

    ![Importovat soubor nastavení publikování](./media/vs-azure-tools-access-private-azure-clouds-with-visual-studio/IC790780.png)

    Certifikáty jsou importovány ze souboru nastavení publikování do sady Visual Studio, a teď můžete pracovat s prostředky privátního cloudu.
