---
title: Oprava sady Visual Studio
titleSuffix: ''
description: Zjistěte, jak opravit instalaci sady Visual Studio 2017
ms.date: 03/30/2019
ms.custom: seodec18
ms.topic: conceptual
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: 3ba5cdf7ba627bc1d6a75368d90da5ce8a726a5e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62973206"
---
# <a name="repair-visual-studio"></a>Oprava sady Visual Studio

::: moniker range="vs-2017"

Někdy instalaci sady Visual Studio stává poškozené. Toto můžete opravit opravu.

1. Najít **instalační program sady Visual Studio** ve vašem počítači.

     Například v počítači se systémem Windows 10 Anniversary Update nebo novější, vyberte **Start**a poté přejděte k označení **V**, kde je hodnota uvedena jako **instalační program sady Visual Studio**.

   > [!NOTE]
   > V některých počítačích může instalační program sady Visual Studio uvedené pod písmenem **"M"** jako **instalační program Visual Studio**.
   >
   > Alternativně můžete najít instalační program sady Visual Studio v následujícím umístění: `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

1. Spusťte instalační program, zvolte **Další**a klikněte na tlačítko **opravit**.

    ![Opravte Visual Studio z instalačního programu sady Visual Studio](media/repair-visual-studio.png "opravte Visual Studio z instalačního programu sady Visual Studio")
    
   > [!NOTE]
   > Oprava sady Visual Studio resetuje prostředí. Místní přizpůsobení, jako jsou rozšíření vázaná na uživatele instalaci bez nutnosti zvýšení oprávnění, uživatelská nastavení a profily se odeberou. Například motivy, barvy, klávesové zkratky synchronizovaná nastavení se obnoví.
   >

   > [!TIP]
   > **Opravit** možnost se zobrazí pouze pro nainstalované instance sady Visual Studio. Pokud se nezobrazí **opravit** možnost, je pravděpodobné, že jste vybrali **Další** ve verzi, která je uvedena v instalačním programu sady Visual Studio jako "K dispozici" místo "Nainstalováno".

::: moniker-end

::: moniker range="vs-2019"

1. Najdete instalační program sady Visual Studio v počítači.

     Například v počítači se systémem Windows 10, vyberte **Start**a poté přejděte k označení **V**, kde je hodnota uvedena jako **instalační program sady Visual Studio**.

     ![Spusťte instalační program sady Visual Studio](media/vs2019-visual-studio-installer.png "spusťte instalační program sady Visual Studio")

     > [!NOTE]
     > Instalační program sady Visual Studio můžete najít také v následujícím umístění:
     >
     > `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

    Budete muset aktualizovat instalační program pokračovat. Pokud ano, postupujte podle pokynů.

1. V instalačním programu vyhledejte edici sady Visual Studio, který jste nainstalovali. Dále zvolte **Další**a klikněte na tlačítko **opravit**.

     ![Repair Visual Studio 2019](media/vs-2019/vs-installer-repair.png "Repair Visual Studio 2019")

   > [!NOTE]
   > Oprava sady Visual Studio resetuje prostředí. Místní přizpůsobení, jako jsou rozšíření vázaná na uživatele instalaci bez nutnosti zvýšení oprávnění, uživatelská nastavení a profily se odeberou. Například motivy, barvy, klávesové zkratky synchronizovaná nastavení se obnoví.
   >

   > [!TIP]
   > **Opravit** možnost se zobrazí pouze pro nainstalované instance sady Visual Studio. Pokud se nezobrazí **opravit** možnost, je pravděpodobné, že jste vybrali **Další** ve verzi, která je uvedena v instalačním programu sady Visual Studio jako "K dispozici" místo "Nainstalováno".

::: moniker-end

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [Instalace sady Visual Studio](install-visual-studio.md)
* [Aktualizace sady Visual Studio](update-visual-studio.md)
* [Odinstalace sady Visual Studio](uninstall-visual-studio.md)
* [Odstraňování problémů instalace a upgradu sady Visual Studio](troubleshooting-installation-issues.md)
