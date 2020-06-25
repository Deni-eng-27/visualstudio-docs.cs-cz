---
title: Konfigurace projektu cloudové služby Azure
description: Naučte se konfigurovat projekt cloudové služby Azure v aplikaci Visual Studio v závislosti na vašich požadavcích na daný projekt.
author: ghogen
manager: jillfra
assetId: 609d6965-05cc-47b1-82dc-c76a92d4f295
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: how-to
ms.date: 03/06/2017
ms.author: ghogen
ms.openlocfilehash: 1776aebbe827295cbc7902f72417bc57e03a4196
ms.sourcegitcommit: 1d4f6cc80ea343a667d16beec03220cfe1f43b8e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85280632"
---
# <a name="configure-an-azure-cloud-service-project-with-visual-studio"></a>Konfigurace projektu cloudové služby Azure v sadě Visual Studio
Můžete nakonfigurovat projekt cloudové služby Azure v závislosti na vašich požadavcích na daný projekt. Můžete nastavit vlastnosti projektu pro následující kategorie:

- **Publikování cloudové služby do Azure** – vlastnost můžete nastavit tak, aby se zajistilo, že existující cloudová služba nasazená do Azure nebude omylem odstraněna.
- **Spuštění nebo ladění cloudové služby v místním počítači** – můžete vybrat konfiguraci služby, kterou chcete použít, a určit, jestli chcete spustit emulátor úložiště Azure.
- **Ověřit balíček cloudové služby, když je vytvořený** – můžete se rozhodnout považovat všechna upozornění za chyby, abyste měli jistotu, že se balíček cloudové služby nasadí bez jakýchkoli problémů.

## <a name="steps-to-configure-an-azure-cloud-service-project"></a>Postup konfigurace projektu cloudové služby Azure
1. Otevřete nebo vytvořte projekt cloudové služby v aplikaci Visual Studio

1. V **Průzkumník řešení**klikněte pravým tlačítkem myši na projekt a v místní nabídce vyberte možnost **vlastnosti**.

1. Na stránce Vlastnosti projektu vyberte kartu **vývoj** .

    ![Nabídka vlastností projektu](./media/vs-azure-tools-configuring-an-azure-project/solution-explorer-project-properties-menu.png)

1. **Před odstraněním existujícího nasazení** na **hodnotu true**nastavte výzvu. Toto nastavení vám pomůže zajistit, že už nechtěně neodstraníte stávající nasazení v Azure.

1. Vyberte požadovanou **konfiguraci služby** a určete, která konfigurace služby se má použít při místním spuštění nebo ladění cloudové služby. Další informace o tom, jak změnit konfiguraci služby pro roli, najdete v tématu [jak nakonfigurovat role pro cloudovou službu Azure pomocí sady Visual Studio](./vs-azure-tools-configure-roles-for-cloud-service.md).

1. Nastavte **emulátor úložiště Azure** na **hodnotu true** , pokud chcete spustit emulátor úložiště Azure při místním spuštění nebo ladění cloudové služby.

1. Nastavte **považovat upozornění za chyby** na **hodnotu true** , abyste se ujistili, že nemůžete publikovat, pokud dojde k chybám ověření balíčku.

1. Pokud chcete zajistit, aby webová role používala stejný port pokaždé, když se spustí místně v IIS Express, nastavte **použít porty webového projektu** na **hodnotu true** .

1. Na panelu nástrojů sady Visual Studio vyberte **Uložit**.

## <a name="next-steps"></a>Další kroky
- [Konfigurace projektu Azure pomocí více konfigurací služby](vs-azure-tools-multiple-services-project-configurations.md)
