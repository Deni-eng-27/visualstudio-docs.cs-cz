---
title: 'Návod: Vytvoření vlastního editoru | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], custom - create
ms.assetid: d090abb6-d99f-4083-a3db-cd16bf81ce7d
caps.latest.revision: 18
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 4b1b4e59e43a4a5aeb129464a34b96ef3f665e72
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68148870"
---
# <a name="walkthrough-creating-a-custom-editor"></a>Návod: Vytvoření vlastního editoru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Šablona projektu VSPackage můžete vytvořit jednoduchý vlastní editor v jazyce C++.  Šablona projektu VSPackage už nepodporuje projekty jazyka C# nebo Visual Basic. Další informace najdete v tématu [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
## <a name="prerequisites"></a>Požadavky  
 Chcete-li postupovat podle tohoto návodu, je nutné nainstalovat sadu Visual Studio SDK. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="the-visual-studio-package-project-template"></a>Šablona projektu balíček sady Visual Studio  
 Šablona projektu balíček Visual Studio najdete v **nový projekt** dialogového okna ve složce rozšíření jazyka C++  
  
### <a name="to-create-a-vspackage-using-the-visual-studio-package-template"></a>Chcete-li vytvořit pomocí šablony Visual Studio balíčku VSPackage  
  
1. Vytvořte projekt pomocí šablony Visual Studio balíček.  
  
2. Vyberte **vlastního editoru** možnost a klikněte na tlačítko **Další**. **Možnosti editoru** zobrazí se stránka.  
  
3. Zadejte název v editoru **název editoru** pole. Zadejte příponu souboru, který chcete přidružit v editoru v **přípona souboru** pole. Editor je k dispozici pro soubory s touto příponou. Přípona souboru je zaregistrována pro sadu Visual Studio pouze, ne pro Windows. Zadejte název souboru výchozí pro nové dokumenty vytvořené v editoru v **výchozí název souboru** pole.  
  
4. Klikněte na tlačítko **Dokončit** k vytvoření vašeho balíčku VSPackage v zadané složce.  
  
### <a name="to-test-your-custom-editor"></a>K otestování vlastního editoru  
  
1. Na **souboru** nabídky, přejděte k **nový** a potom klikněte na tlačítko **souboru**.  
  
2. V **nainstalované šablony** podokně **nový soubor** dialogovém okně vyberte soubor šablony a pak ho zadejte, které jste právě zaregistrovali.  
  
3. Klikněte na tlačítko **otevřít** k zobrazení a úpravě dokumentu.  
  
     Editor podporuje operace vyjmutí a vložení, najít a nahradit a otevřít a zatížení.  
  
## <a name="see-also"></a>Viz také  
 [Balíčky VSPackage](../extensibility/internals/vspackages.md)
