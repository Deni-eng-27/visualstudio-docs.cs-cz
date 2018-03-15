---
title: "Rychlý úvod: použijte sadu Visual Studio k vytvoření první aplikace Node.js | Microsoft Docs"
description: "V tento rychlý start můžete vytvořit aplikaci Node.js v sadě Visual Studio"
ms.custom: 
ms.date: 11/15/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: 
ms.topic: quickstart
ms.devlang: javascript
ms.assetid: b0e4ebed-1a01-41ef-aad1-4d8465ce5322
author: mikejo5000
ms.author: mikejo
manager: ghogen
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: 8597d7ee61820afdd8fcfdbff9cdb5be8dfaa61c
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2018
---
# <a name="quickstart-use-visual-studio-to-create-your-first-nodejs-app"></a>Rychlý úvod: Použití Visual Studio k vytvoření první aplikace Node.js
V tento úvod 5 až 10 minut v sadě Visual Studio integrované vývojové prostředí (IDE) vytvoříte jednoduchou webovou aplikaci Node.js. Pokud jste ještě nenainstalovali Visual Studio, nainstalovat zdarma [zde](http://www.visualstudio.com).  

## <a name="create-a-project"></a>Vytvoření projektu
Nejdřív vytvoříte projekt Node.js webové aplikace.

1. Pokud nemáte runtime Node.js již nainstalována, nainstalovat verzi LTS [Node.js](https://nodejs.org/en/download/) webu.

    Obecně platí Visual Studio automaticky rozpozná nainstalované runtime Node.js. Pokud nezjistí instalované verzi můžete nakonfigurovat projekt tak, aby odkazovaly nainstalovaný modul runtime.

1. Open Visual Studio 2017.  

1. V horní nabídce vyberte příkaz **soubor** > **nový** > **projektu...** .  

1. V **nový projekt** dialogové okno, v levém podokně rozbalte **JavaScript**, zvolte **Node.js**. V prostředním podokně vyberte **prázdné Node.js webové aplikace**, zvolte **OK**.   

     Pokud nevidíte **prázdné Node.js webové aplikace** projektu šablony, klikněte na tlačítko **otevřete instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno. Spustí instalační program Visual Studio. Vyberte **Node.js vývoj** zatížení, zvolte **upravit**.  

     ![Node.js zatížení v instalační program VS](../ide/media/quickstart-nodejs-workload.png)  

    Visual Studio vytvoří a nového řešení a otevře projektu. *Server.js* se otevře v editoru v levém podokně.

## <a name="explore-the-ide"></a>Prozkoumejte rozhraní IDE  

1. Podívejte se na **Průzkumníku řešení** v pravém podokně.

   ![Průzkumník řešení](../ide/media/quickstart-nodejs-solution-explorer.png)  

  - Zvýrazněná tučným písmem je váš projekt pomocí názvu, který jste zadali **nový projekt** dialogové okno. Na disku tento projekt je reprezentována .njsproj soubor ve složce projektu.

  - Na nejvyšší úrovni je řešení, které ve výchozím nastavení má stejný název jako projektu. Řešení, reprezentována soubor .sln na disku, je kontejner pro jednu nebo více souvisejících s projekty.

  - Uzel npm zobrazuje všechny balíčky nainstalované npm. Pravým tlačítkem na uzel npm vyhledat a nainstalovat balíčky npm pomocí dialogového okna.

1. Pokud chcete nainstalovat balíčky npm nebo node.js příkazy z příkazového řádku, klikněte pravým tlačítkem na uzel projektu a zvolte **sem otevřete příkazový řádek**.

   ![Node.js příkazového řádku](../ide/media/quickstart-nodejs-command-prompt.png) 

1. V *server.js* souboru v editoru (levé podokno), zvolte `http.createServer` a potom stiskněte klávesu **F12** nebo zvolte **přejít k definici** z nabídky kontextu (klikněte pravým tlačítkem). Tento příkaz má definici `createServer` funkce v index.d.ts.  

   ![Přejít k definici kontextové nabídky](../ide/media/quickstart-nodejs-gotodefinition.png)  

1. Získali zpět do *server.js*, pak v tomto řádku kódu, umístěte kurzor na konci řetězce `res.end('Hello World\n');`a upravit ji tak, aby vypadá takto:

    `res.end('Hello World\n' + res.connection.`

    Místo pro zadání `connection.`, IntelliSense poskytuje možnosti pro automatické dokončování položku kódu.

   ![Automatické dokončování IntelliSense](../ide/media/quickstart-nodejs-intellisense.png)  

1. Zvolte **Místní_port**a pak zadejte `);` dokončit příkaz tak, aby vypadá takto:

    `res.end('Hello World\n' + res.connection.localPort);`

## <a name="run-the-application"></a>Spuštění aplikace
1. Stiskněte klávesu **Ctrl + F5** (nebo **ladění > Spustit bez ladění**) ke spuštění aplikace. Aplikace se otevře v prohlížeči.  

1. V okně prohlížeče se zobrazí "Hello World" a číslem místního portu.

1. Zavřete webový prohlížeč.  

Blahopřejeme k dokončení tento rychlý start! Věříme, že jste se naučili chvíli o prostředí Visual Studio IDE. Pokud chcete pustíte hlubší do jeho možnosti, pokračujte prosím se v kurzu **kurzy** části obsahu.  

## <a name="next-steps"></a>Další kroky 

- Projděte [kurzu Node.js a Express](../nodejs/tutorial-nodejs.md)  
- Projděte [kurzu Node.js a reagují](../nodejs/tutorial-nodejs-with-react-and-jsx.md)  