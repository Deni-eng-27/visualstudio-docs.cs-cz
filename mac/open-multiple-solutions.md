---
title: 'Postupy: otevření více řešení'
description: Naučte se, jak otevřít více než jedno řešení v Visual Studio pro Mac a jak otevřít více než jednu instanci aplikace.
author: heiligerdankgesang
ms.author: dominicn
ms.date: 11/09/2020
ms.assetid: 592BA4E3-8DEF-4FCD-8BA0-519A4CEEE03E
ms.custom: video
ms.topic: how-to
ms.openlocfilehash: e54f002141379d93a40df69ea070d5a64eba2f7d
ms.sourcegitcommit: 2cf3a03044592367191b836b9d19028768141470
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2020
ms.locfileid: "94493436"
---
# <a name="open-multiple-solutions-or-instances-of-visual-studio-for-mac"></a>Otevřete více řešení nebo instancí Visual Studio pro Mac

Ve výchozím nastavení jsou všechny aplikace na Macu, včetně Visual Studio pro Mac, aplikace s _jednou instancí_ . To znamená, že pokud je aplikace, kterou chcete použít, už otevřená (znázorněná tečkou pod ikonou v Docku), pak se znovu vybere ikona se spuštěnou instancí namísto nového. Pokud požadujete další instance aplikace, můžete si systém vyzvat, aby ho otevřel za vás, jak je popsáno v [následující části](#open-a-second-instance-of-visual-studio-for-mac).

Kromě toho, když otevřete řešení, výchozí chování je otevřít řešení v novém pracovním prostoru a zavřít aktuální pracovní prostor (v případě potřeby). Toto výchozí chování můžete přepsat tak, že zachováte otevřený aktuální pracovní prostor, jak je popsáno v části [otevření druhého řešení](#open-a-second-solution-inside-a-single-instance) .

## <a name="open-a-second-instance-of-visual-studio-for-mac"></a>Otevření druhé instance Visual Studio pro Mac

Chcete-li otevřít druhou instanci integrovaného vývojového prostředí (IDE), klikněte pravým tlačítkem myši na ikonu sady Visual Studio ve složce Dock nebo **Applications** a vyberte možnost **Nová instance**.

![Snímek obrazovky s možností nabídky nová instance na ikoně Visual studia vpravo](media/open-new-instance.png)

## <a name="open-a-second-solution-inside-a-single-instance"></a>Otevřít druhé řešení v rámci jedné instance

Pokud chcete otevřít druhé řešení společně s vaším prvním řešením, použijte následující postup:

1. Když máte vaše první řešení otevřené, vyberte **soubor**  >  **otevřít**.
2. Procházejte systémem souborů a vyhledejte existující řešení.
3. Vyberte soubor **. sln** a vyberte **Možnosti** :

    ![Snímek obrazovky Visual Studio pro Mac se zvýrazněným souborem. sln a vybranými možnostmi](media/open-multiple-solutions-image3.png)

4. Zrušte zaškrtnutí políčka **Zavřít aktuální pracovní prostor** :

    ![Snímek obrazovky dialogového okna Možnosti s nezaškrtnutým políčkem Zavřít aktuální pracovní prostor](media/open-multiple-solutions-image1.png)

5. Výběrem **otevřít** otevřete druhé řešení v okně řešení.

Případně, pokud jste řešení nedávno otevřeli, můžete použít následující postup:

1. Přejít na **File**  >  **Poslední řešení** souborů

    ![Snímek obrazovky s posledními nabídkami řešení](media/open-multiple-solutions-image2.png)

1. Podržte stisknutou klávesu **CTRL** a vyberte řešení. Tato kombinace otevře druhé řešení v okně řešení.

## <a name="related-video"></a>Související video

> [!Video https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/Visual-Studio-for-Mac-Work-With-Multiple-Solutions/player]
