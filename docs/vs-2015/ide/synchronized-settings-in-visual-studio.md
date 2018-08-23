---
title: Synchronizovaná nastavení v sadě Visual Studio | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Environment.RoamingSettings
ms.assetid: a3d2ea29-be5d-4012-9820-44b06adbb7dd
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1e0facac569671c880004d1fc1a7aa29487e7926
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670310"
---
# <a name="synchronized-settings-in-visual-studio"></a>Synchronizovaná nastavení v sadě Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [synchronizovat nastavení v sadě Visual Studio](https://docs.microsoft.com/visualstudio/ide/synchronized-settings-in-visual-studio).  
  
Při použití stejného účtu individuálního nastavení pro přihlášení k sadě Visual Studio na víc počítačích nastavení ve výchozím nastavení synchronizované na všech počítačích.  
  
## <a name="synchronized-settings"></a>Synchronizovaná nastavení  
 Ve výchozím nastavení jsou synchronizována následující nastavení.  
  
-   Nastavení vývoje (je nutné vybrat sadu nastavení při prvním spuštění sady Visual Studio, ale můžete výběr můžete kdykoli změnit. Další informace najdete v tématu [přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).)  
  
-   Následující možnosti **nástroje &#124; možnosti** stránky:  
  
    -   **Motiv** a nabídek na malá a velká písmena nastavení, **prostředí**, **Obecné** stránky Možnosti  
  
    -   Všechna nastavení na **prostředí**, **písma a barvy** stránky Možnosti  
  
    -   Všechny klávesové zkratky, na **prostředí**, **klávesnice** stránky Možnosti  
  
    -   Všechna nastavení na **prostředí, karty a Windows** stránky Možnosti  
  
    -   Všechna nastavení na **prostředí**, **spuštění** stránky Možnosti  
  
    -   Všechna nastavení na **textový Editor** možnosti stránky  
  
-   Všechna nastavení v Návrháři XAML možnosti stránky  
  
-   Aliasy příkazu definované uživatelem. Další informace o definici aliasů příkazu naleznete v tématu [aliasy příkazů aplikace Visual Studio](../ide/reference/visual-studio-command-aliases.md).  
  
-   Rozložení oken uživatelem definované v **okno &#124; spravovat rozložení oken** stránky  
  
## <a name="turning-synchronized-settings-off-for-a-particular-computer"></a>Zapnutí synchronizované nastavení vypnout pro určitý počítač  
 Synchronizovaná nastavení pro sadu Visual Studio jsou ve výchozím nastavení zapnutá. Synchronizovaná nastavení v počítači můžete vypnout tak, že přejdete **nástroje &#124; možnosti &#124; prostředí &#124; synchronizovaná nastavení** stránky a zrušení zaškrtnutí políčka.  Například pokud se rozhodnete nesynchronizovat nastavení sady Visual Studio v počítači A, změny nastavení v počítači provedeny DNT nezobrazí v počítači B nebo počítač C. počítačích B a C bude pokračovat pro synchronizaci mezi sebou, ale ne s počítači A.  
  
## <a name="synchronizing-settings-across-visual-studio-family-products-and-editions"></a>Synchronizace nastavení mezi produkty řady Visual Studio a edice  
 Nastavení dají synchronizovat do všech libovolná edice sady Visual Studio 2015, včetně edice Express a komunity. Nastavení jsou také synchronizovat napříč produkty řady Visual Studio, jako je například prolnutí. Všechny tyto produkty řady však může mít svůj vlastní nastavení, která se nesdílejí s Visual Studio. Například se nastavení specifické pro Blend v počítači A sdílet pomocí programu Blend v počítači B, ale ne s Visual Studio na počítači A a B.  
  
> [!WARNING]
>  Nastavení nejsou synchronizovány mezi Visual Studio 2013 a Visual Studio 2015. Při prvním otevření sady Visual Studio 2015, nastavení ze sady Visual Studio 2013 se migrují, ale proto se nedají migrovat zpět na Visual Studio 2013, po který.  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení integrovaného vývojového prostředí](../ide/personalizing-the-visual-studio-ide.md)



