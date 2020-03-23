---
title: Publikovat do složky
ms.date: 01/22/2019
helpviewer_keywords:
- deployment, website
ms.assetid: e963fb4b-6d32-4d45-86bb-ef7e4d3028b0
author: sayedihashimi
ms.author: sayedha
manager: unniravindranathan
ms.prod: visual-studio-mac
ms.openlocfilehash: 02175180e5217a14a4464e46c75d519adab2a332
ms.sourcegitcommit: 2975d722a6d6e45f7887b05e9b526e91cffb0bcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/20/2020
ms.locfileid: "73714505"
---
# <a name="publish-a-web-app-to-a-folder-using-visual-studio-for-mac"></a>Publikování webové aplikace do složky pomocí Visual Studia pro Mac

Pomocí nástroje Publikovat můžete publikovat aplikace ASP.NET Core do složky.

## <a name="prerequisites"></a>Požadavky

- [Visual Studio 2017 pro Mac](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs4mac2017) nainstalované s povoleným ASP.NET Core.
- Projekt ASP.NET Core. Pokud ještě nemáte projekt, můžete [vytvořit nový](/visualstudio/mac/create-new-projects?view=vsmac-2017).

## <a name="publish-to-folder"></a>Publikování do složky

Pomocí Visual Studia pro Mac můžete publikovat ASP.NET projekty Core do složky pomocí nástroje Publikovat. Po publikování do složky můžete soubory přenést na webový server a dostat je do jiného prostředí. Chcete-li publikovat do složky, postupujte takto.

 1. Na panelu řešení klikněte pravým tlačítkem myši na projekt a zvolte **Publikovat**.

    ![Publikovat místní nabídku](media/publish-context-menu.png)

 2. Pokud jste tento projekt publikovali dříve, zobrazí se profil publikování v nabídce. Vyberte tento profil publikování a spusťte proces publikování.

 3. Chcete-li tento projekt poprvé publikovat do složky, vyberte **publikovat do složky.**

    ![Místní nabídka Publikovat do složky](media/publish-to-folder-context-menu.png)

 4. Zobrazí se dialogové okno **Publikovat do složky.** V tomto dialogovém okně můžete přizpůsobit složku, kde bude projekt publikován. Můžete to provést pomocí tlačítka **Procházet** nebo vložit do cesty.

 5. Po kliknutí na **publikovat** se stane několik věcí. Nejprve je vytvořen profil publikování. Profil publikování je soubor MSBuild, který je importován do projektu během procesu publikování. Obsahuje vlastnosti, které se používají během procesu publikování. Tyto soubory jsou `Properties/PublishProfiles` uloženy v `.pubxml`a mají rozšíření . Dále je spuštěn proces publikování. Průběh můžete sledovat sledováním stavového řádku ve Visual Studiu pro Mac.

    ![Stavový řádek IDE se stavem Publikovat](media/publish-to-folder-status-bar.png)

 6. Po úspěšném dokončení publikování se do složky publikování otevře okno Finderu. Nyní, když byl vytvořen profil publikování, se zobrazí v místní nabídce Publikovat.

    ![Místní nabídka Publikovat s profilem složky](media/publish-context-menu-with-folder-profile.png)

 7. Chcete-li projekt znovu publikovat se stejným nastavením, můžete kliknout na profil v kontextové nabídce publikování.

## <a name="customize-publish-options"></a>Přizpůsobení možností publikování

Chcete-li změnit název profilu publikování (který je zobrazen v místní nabídce publikování), přejmenujte soubor profilu publikování. Ujistěte se, že neměnit`.puxbml`příponu souboru ( ).

Chcete-li změnit cestu ke složce publikování, otevřete profil publikování a upravte hodnotu. `publishUrl`

Chcete-li změnit konfiguraci sestavení, `LastUsedBuildConfiguration` která se používá, změňte vlastnost v profilu publikování.