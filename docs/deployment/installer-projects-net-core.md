---
title: Instalační program pro Visual Studio projekty a .NET Core 3,1
titleSuffix: ''
ms.date: 08/18/2020
ms.topic: conceptual
helpviewer_keywords:
- installer projects
- installer projects, .NETCore
author: MSLukeWest
ms.author: lukewest
manager: MSLukeWest
monikerRange: '>= vs-2019'
ms.workload:
- multiple
ms.openlocfilehash: 86680a2b961af9182691422e02b42c6529f45639
ms.sourcegitcommit: 062615c058d2ff44751e8d0c704ccfa3c5543469
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/22/2020
ms.locfileid: "90852651"
---
# <a name="visual-studio-installer-projects-extension-and-net-core-31"></a>Rozšíření Visual Studio Installer Projects a .NET Core 3.1

Vytváření balíčků aplikací jako MSI se často provádí pomocí rozšíření Instalační program pro Visual Studio projekty.

Rozšíření si můžete stáhnout tady: [instalační program pro Visual Studio projekty](https://marketplace.visualstudio.com/items?itemName=VisualStudioClient.MicrosoftVisualStudio2017InstallerProjects)

## <a name="update-for-net-core"></a>Aktualizace pro .NET Core
.NET Core má dva různé modely pro publikování.

- Nasazení závislá na rozhraních

- Samostatně obsažené aplikace zahrnují modul runtime.

Další informace o těchto strategiích nasazení najdete v tématu [Přehled publikování aplikací .NET Core](/dotnet/core/deploying/).

### <a name="workflow-changes-for-net-core-31"></a>Změny pracovního postupu pro .NET Core 3,1

1. Vyberte **publikovat položky** namísto **primárního výstupu** , abyste získali správný výstup pro projekty .NET Core 3,1.  Pokud chcete toto dialogové okno vyvolat, vyberte **Přidat**  >  **výstup projektu...** z kontextové nabídky projektu.

    ![Výstupní skupina položek publikování v dialogovém okně Přidat výstupní skupinu projektu](../deployment/media/installer-projects-net-core-publish-items-output.png "Výběr položek publikování")

2. Chcete-li vytvořit samostatný instalační program, nastavte vlastnost **PublishProfilePath** v uzlu **publikovat položky** v projektu instalace pomocí relativní cesty k publikačnímu profilu se správnými nastaveními vlastností.

    ![Nastavení profilu publikování pro výstupní položku projektu položky publikování](../deployment/media/installer-projects-net-core-publish-profile.png "Nastavit profil publikování")

### <a name="prerequisites-for-net-core-31"></a>Předpoklady pro .NET Core 3,1

Pokud chcete, aby instalační program mohl nainstalovat potřebný modul runtime pro aplikaci .NET Core 3,1 závislou na rozhraní, můžete to provést pomocí [požadavků](../deployment/application-deployment-prerequisites.md).  V dialogovém okně Vlastnosti projektu instalačního programu otevřete dialog **požadavky...** a zobrazí se následující položky:

![Položky .NET Core v dialogovém okně požadavky](../deployment/media/installer-projects-net-core-prerequisites.png "Požadavky .NET Core")

Možnost **.NET Core Runtime...** by měla být vybraná pro konzolové aplikace, **modul runtime .NET Desktop..** . by měl být vybraný pro aplikace WPF/WinForms.

>[!NOTE]
>Tyto položky jsou přítomny počínaje verzí sady Visual Studio 2019 Update 7.

## <a name="see-also"></a>Viz také

- [Dialogové okno Požadavky](../ide/reference/prerequisites-dialog-box.md)
- [Požadavky nasazení aplikace](../deployment/application-deployment-prerequisites.md)