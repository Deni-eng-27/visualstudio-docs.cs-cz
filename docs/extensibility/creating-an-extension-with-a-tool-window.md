---
title: Vytváření rozšíření pomocí panelu nástrojů | Dokumentace Microsoftu
ms.date: 3/16/2019
ms.topic: conceptual
ms.assetid: 585b0a3a-f85b-4f92-81bb-9ca499bb8a89
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b5a38c9912be87c94c79076675b5db25663fb5f0
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66345436"
---
# <a name="create-an-extension-with-a-tool-window"></a>Vytváření rozšíření pomocí panelu nástrojů

V tomto postupu se dozvíte, jak použít šablonu projektu VSIX a **vlastního panelu nástrojů** šablony položky k vytvoření rozšíření pomocí panelu nástrojů.

## <a name="prerequisites"></a>Požadavky

 Spouští se v sadě Visual Studio 2015, nenainstalujete sadu Visual Studio SDK ze služby Stažení softwaru. Je zahrnut jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).

### <a name="create-a-tool-window"></a>Vytvoření panelu nástrojů

1. Vytvořte projekt VSIX s názvem **FirstWindow**. Šablona projektu VSIX v můžete najít **nový projekt** dialogové okno tak, že "vsix".

2. Po otevření projektu přidat šablonu položky okna nástroje s názvem **MyWindow**. V **Průzkumníka řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **přidat** > **nová položka**. V **přidat novou položku** dialogové okno, přejděte na **Visual C#**  > **rozšiřitelnost** a vyberte **vlastního panelu nástrojů**. V **název** pole v dolní části okna, změňte název souboru okna nástroje, aby *MyWindow.cs*.

3. Sestavte projekt a spusťte ladění.

   Experimentální instanci sady Visual Studio se zobrazí. Další informace o experimentální instanci najdete v tématu [experimentální instanci](../extensibility/the-experimental-instance.md).

4. V experimentální instanci aplikace, přejděte na **zobrazení** > **ostatní Windows**.

   Měli byste vidět položku nabídky pro **MyWindow**. Klikněte na něj.

   Měli byste vidět okno nástroje s názvem **MyWindow** a slavným výrokem tlačítko **klikněte na mě!.**