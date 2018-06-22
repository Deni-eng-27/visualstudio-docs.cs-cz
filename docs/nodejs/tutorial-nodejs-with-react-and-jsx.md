---
title: Vytvoření aplikace Node.js a React
description: V tomto kurzu vytvoříte aplikaci pomocí nástrojů Node.js Tools for Visual Studio.
ms.custom: mvc
ms.date: 05/23/2018
ms.technology: vs-nodejs
ms.topic: tutorial
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: douge
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: 17e91ac47b4e8a6a2d94caa523309bc0cfe9dd7e
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/20/2018
ms.locfileid: "36281362"
---
# <a name="tutorial-create-a-nodejs-and-react-app-in-visual-studio"></a>Kurz: Vytvoření aplikace Node.js a React v sadě Visual Studio
Visual Studio vám umožňuje snadno vytvořit projekt Node.js a využívat IntelliSense a další integrované funkce, které podporují Node.js. V tomto kurzu pro Visual Studio vytvoříte projekt webové aplikace Node.js ze šablony sady Visual Studio. Pak vytvoříte jednoduchou aplikaci pomocí Reactu.

V tomto kurzu se naučíte:
> [!div class="checklist"]
> * Vytvořit projekt Node.js
> * Přidat balíčky npm
> * Přidat do aplikace kód React
> * Transpilovat JSX
> * Připojit ladicí program

## <a name="prerequisites"></a>Požadavky

* Je nutné mít nainstalovanou sadu Visual Studio 2017 a úlohu Vývoj aplikací Node.js.

    Pokud jste ještě nenainstalovali Visual Studio, přejděte k [Visual Studio stáhne](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) stránky instalaci zdarma.

    Pokud potřebujete nainstalovat úlohu, ale Visual Studio už máte, klikněte v dialogovém okně **Nový projekt** v levém podokně na odkaz **Otevřít instalační program pro Visual Studio**. Spustí se instalační program pro Visual Studio. Zvolte úlohu **Vývoj aplikací Node.js** a pak zvolte **Změnit**.

* Je nutné mít nainstalovaný modul runtime Node.js.

    V tomto kurzu byla testována s verze 8.11.2.

    Pokud ho nemáte nainstalovaný, nainstalujte si verzi LTS z webu [Node.js](https://nodejs.org/en/download/). Obecně platí, že Visual Studio automaticky rozpozná nainstalovaný modul runtime Node.js. Pokud se nainstalovaný modul runtime nerozpozná, můžete projekt nakonfigurovat na stránce vlastností pomocí odkazu na nainstalovaný modul runtime (po vytvoření projektu klikněte pravým tlačítkem na uzel projektu a zvolte **Vlastnosti**).

## <a name="create-a-project"></a>Vytvoření projektu
Nejprve vytvoříte projekt webové aplikace Node.js.

1. Otevřete Visual Studio 2017.

1. V horním řádku nabídek zvolte **Soubor** > **Nový** > **Projekt**.

1. V dialogovém okně **Nový projekt** v levém podokně rozbalte položku **JavaScript** a zvolte **Node.js**. V prostředním podokně zvolte **Prázdná webová aplikace Node.js**, zadejte název **NodejsWebAppBlank** a zvolte **OK**.

     Pokud se šablona projektu **Prázdná webová aplikace Node.js** nezobrazuje, je nutné nejprve nainstalovat úlohu Vývoj aplikací Node.js.

    Visual Studio vytvoří nové řešení a otevře příslušný projekt.

    ![Projekt Node.js v Průzkumníku řešení](../nodejs/media/tutorial-nodejs-react-project-structure.png)

    - Projekt je zvýrazněný tučným písmem a má název, který jste zadali v dialogovém okně **Nový projekt**. V systému souborů je tento projekt reprezentovaný souborem *.njsproj* ve složce projektu. Vlastnosti a proměnné prostředí přidružené k projektu můžete nastavit tak, že kliknete pravým tlačítkem na projekt a zvolíte **Vlastnosti**. Je možné provádět zpětné převody umožňující práci v jiných nástrojích pro vývoj, protože soubor projektu neprovádí vlastní změny ve zdroji projektu Node.js.

    - Na nejvyšší úrovni je řešení, které má ve výchozím nastavení stejný název jako příslušný projekt. Řešení, reprezentované na disku souborem *.sln*, je kontejner pro jeden nebo více souvisejících projektů.

    - Uzel npm zobrazuje všechny nainstalované balíčky npm. Po kliknutí pravým tlačítkem na uzel npm lze vyhledat a nainstalovat balíčky npm pomocí dialogového okna.

    - Soubory projektu, například *server.js*, se zobrazují pod uzlem projektu. *Server.js* je spouštěcí soubor projektu.

## <a name="add-npm-packages"></a>Přidání balíčků npm

Tato aplikace vyžaduje ke správnému fungování řadu modulů npm.

* react
* react-dom
* express
* cesta
* ts-loader
* typescript
* webpack
* webpack-cli

1. V Průzkumníku řešení (pravé podokno) klikněte pravým tlačítkem na uzel **npm** v projektu a zvolte **Nainstalovat nové balíčky npm**.

    V dialogovém okně **Nainstalovat nové balíčky npm** můžete zvolit instalaci nejnovější verze balíčků nebo určit konkrétní verzi. Pokud zvolíte instalaci nejnovější verze těchto balíčků, ale při dalším postupu dojde k neočekávaným chybám, bude asi potřeba nainstalovat přesně ty verze balíčků, které jsou uvedené dále v tomto postupu.

1. V dialogovém okně **Nainstalovat nové balíčky npm** vyhledejte balíček react a kliknutím na **Nainstalovat balíček** ho nainstalujte.

    ![Instalace balíčků npm](../nodejs/media/tutorial-nodejs-react-install-packages.png)

    Klikněte na tlačítko **výstup** okna zobrazíte průběh o instalaci balíčku (vyberte **Npm** v **zobrazit výstup z** pole). Po dokončení instalace se tento balíček zobrazí pod uzlem **npm**.

    Soubor *package.json* tohoto projektu se aktualizuje informacemi o novém balíčku, včetně verze tohoto balíčku.

1. Místo hledání a přidávání zbývajících balíčků po jednom pomocí uživatelského rozhraní vložte následující kód do souboru package.json. Nahraďte v něm oddíl `dependencies` tímto kódem:

    ```js
    "dependencies": {
      "express": "4.16.2",
      "path": "0.12.7",
      "react": "16.4.0",
      "react-dom": "16.4.0",
      "ts-loader": "4.0.1",
      "typescript": "2.7.2",
      "webpack": "4.1.1",
      "webpack-cli": "2.0.11"
    }
    ```

1. Klikněte pravým tlačítkem na **npm** uzlu ve vašem projektu a zvolte **aktualizovat balíčky npm**.

    Klikněte **výstup** okna zobrazíte průběh k instalaci balíčků. To může trvat několik minut a okamžitě se nemusí zobrazovat výsledky.

    Tady jsou moduly npm, které se po instalaci zobrazí v Průzkumníku řešení.

    ![Balíčky npm](../nodejs/media/tutorial-nodejs-react-npm-modules.png)

    > [!NOTE]
    > Pokud chcete balíčky npm nainstalovat raději pomocí příkazového řádku, klikněte pravým tlačítkem na uzel projektu a zvolte **Otevřít tady příkazový řádek**. K instalaci balíčků použijte standardní příkazy Node.js.

## <a name="add-project-files"></a>Přidání souborů projektu

V tomto postupu do projektu přidáte čtyři nové soubory.

* *app.tsx*
* *webpack-config.js*
* *index.html*
* *tsconfig.json*

Nové soubory projektu pro tuto jednoduchou aplikaci přidáte do kořenu projektu. (U většiny aplikací se soubory obvykle přidávají do podsložek a odkazy s relativní cestou se podle toho upraví.)

1. V Průzkumníku řešení klikněte pravým tlačítkem na projekt **NodejsWebAppBlank** a zvolte **Přidat** > **Nová položka**.

1. V dialogovém okně **Přidat novou položku** vyberte **Soubor TypeScript JSX**, zadejte název *app.tsx* a klikněte na **OK**.

1. Opakováním tohoto postupu přidejte *webpack config.js*. Místo souboru TypeScript JSX, zvolte **soubor JavaScript**.

1. Opakováním stejného postupu do projektu přidejte *index.html*. Místo souboru JavaScript zvolte **Soubor HTML**.

1. Opakováním stejného postupu do projektu přidejte *tsconfig.json*. Místo souboru JavaScript zvolte **Konfigurační soubor JSON pro TypeScript**.

## <a name="add-app-code"></a>Přidání kódu aplikace

1. Otevřete *server.js* a nahraďte kód následujícím kódem:

    ```javascript
    'use strict';
    var path = require('path');
    var express = require('express');

    var app = express();

    var staticPath = path.join(__dirname, '/');
    app.use(express.static(staticPath));

    // Allows you to set port in the project properties.
    app.set('port', process.env.PORT || 3000);

    var server = app.listen(app.get('port'), function() {
        console.log('listening');
    });
    ```

   Uvedený kód spouští Node.js jako server vaší webové aplikace přes Express. Tento kód nastaví port na číslo, které je nakonfigurované ve vlastnostech projektu (ve výchozím nastavení je ve vlastnostech nakonfigurovaný port 1337). Vlastnosti projektu otevřete tak, že v Průzkumníku řešení kliknete pravým tlačítkem na příslušný projekt a zvolíte **Vlastnosti**.

1. Otevřete *app.tsx* a přidejte následující kód:

    ```javascript
    declare var require: any

    var React = require('react');
    var ReactDOM = require('react-dom');

    class Hello extends React.Component {
        render() {
            return (
                <h1>Welcome to React!!</h1>
            );
        }
    }

    ReactDOM.render(<Hello />, document.getElementById('root'));
    ```

    Uvedený kód používá k zobrazení jednoduché zprávy syntaxi JSX a React.

1. Otevřete *index.html* a nahraďte oddíl **body** následujícím kódem:

    ```html
    <body>
        <div id="root"></div>
        <!-- scripts -->
        <script src="./dist/app-bundle.js"></script>
    </body>
    ```

    Tato stránka HTML načte *app-bundle.js* s kódem JSX a React, který bude transpilovaný na prostý JavaScript. Momentálně je soubor *app-bundle.js* prázdný. V další části nakonfigurujete možnosti pro transpilaci tohoto kódu.

## <a name="configure-webpack-and-typescript-compiler-options"></a>Konfigurace webpacku a možností kompilátoru TypeScriptu

V předchozím postupu jste do projektu přidali *webpack-config.js*. Dále přidáte kód pro konfiguraci webpacku. Přidáte jednoduchou konfiguraci webpacku, která určuje vstupní soubor (*app.tsx*) a výstupní soubor (*app-bundle.js*) pro sbalení a transpilaci JSX na prostý JavaScript. Pro transpilaci můžete nakonfigurovat také některé možnosti kompilátoru TypeScriptu. Tento kód představuje základní konfiguraci, která slouží k seznámení s webpackem a kompilátorem TypeScriptu.

1. V Průzkumníku řešení otevřete *webpack-config.js* a přidejte následující kód.

    ```json
    module.exports = {
        devtool: 'source-map',
        entry: "./app.tsx",
        mode: "development",
        output: {
            filename: "./app-bundle.js"
        },
        resolve: {
            extensions: ['.Webpack.js', '.web.js', '.ts', '.js', '.jsx', '.tsx']
        },
        module: {
            rules: [
                {
                    test: /\.tsx$/,
                    exclude: /(node_modules|bower_components)/,
                    use: {
                        loader: 'ts-loader'
                    }
                }
            ]
        }
    }
    ```

    Kód pro konfiguraci webpacku určuje, že k transpilaci JSX se má použít zavaděč TypeScriptu.

1. Otevřete *tsconfig.json* a nahraďte následující kód, který určuje možnosti kompilátoru TypeScript ve výchozím kódu:

    ```json
    {
      "compilerOptions": {
        "noImplicitAny": false,
        "module": "commonjs",
        "noEmitOnError": true,
        "removeComments": false,
        "sourceMap": true,
        "target": "es5",
        "jsx": "react"
      },
      "exclude": [
        "node_modules"
      ],
      "files": [
        "app.tsx"
      ]
    }
    ```

    Jako zdrojový soubor je určený *app.tsx*.

## <a name="transpile-the-jsx"></a>Transpilace JSX

1. V Průzkumníku řešení klikněte pravým tlačítkem na uzel projektu a zvolte **Otevřít tady příkazový řádek**.

1. V příkazovém řádku zadejte následující příkaz:

    `node_modules\.bin\webpack app.tsx --config webpack-config.js`

    V okně příkazového řádku se zobrazí výsledek.

    ![Spuštění webpacku](../nodejs/media/tutorial-nodejs-react-run-webpack.png)

    Pokud se místo uvedeného výstupu zobrazují nějaké chyby, je potřeba je před použitím aplikace odstranit. Příčinou těchto chyb může být skutečnost, že se vaše verze balíčků npm liší od verzí používaných v tomto kurzu. Jednou možností, jak chyby odstranit, je použití přesně těch verzí, které jsou uvedené v dřívějším postupu. Pokud jsou některé z těchto verzí balíčků zastaralé a způsobují chyby, může být k odstranění chyb potřeba nainstalovat novější verze.

1. V Průzkumníku řešení klikněte pravým tlačítkem na uzel projektu a zvolte **Přidat** > **Existující složka**, pak zvolte složku *dist* a klikněte na **Vybrat složku**.

    Visual Studio přidá do projektu složku *dist*, která obsahuje *app-bundle.js* a *app-bundle.js.map*.

1. Otevřete *app-bundle.js* a zobrazte transpilovaný kód jazyka JavaScript.

1. Pokud se zobrazí výzva k novému načtení externě změněných souborů, klikněte na **Ano všem**.

    ![Načtení změněných souborů](../nodejs/media/tutorial-nodejs-react-reload-files.png)

Vždycky, když provedete změny v *app.tsx*, je nutné znovu spustit příkaz webpack.

## <a name="run-the-app"></a>Spuštění aplikace

1. Ujistěte se, že jako aktuální cíl ladění je vybraný Chrome.

    ![Výběr Chromu jako cíle ladění](../nodejs/media/tutorial-nodejs-react-debug-target.png)

1. Ke spuštění aplikace stiskněte **F5** (**Ladit** > **Spustit ladění**) nebo tlačítko se zelenou šipkou.

    Otevře se okno konzoly Node.js, které zobrazuje port, na kterém ladicí program naslouchá.

    Visual Studio spustí danou aplikaci spuštěním spouštěcího souboru *server.js*.

    ![Spuštění Reactu v prohlížeči](../nodejs/media/tutorial-nodejs-react-running-react.png)

1. Zavřete okno prohlížeče.

1. Zavřete okno konzoly.

## <a name="set-a-breakpoint-and-run-the-app"></a>Nastavení zarážky a spuštění aplikace

1. V souboru *server.js* kliknutím do mezery vedle okraje nalevo od deklarace `staticPath` nastavte zarážku:

    ![Nastavení zarážky](../nodejs/media/tutorial-nodejs-react-set-breakpoint.png)

    Zarážky jsou základní a nejjednodušší funkcí spolehlivého ladění. Zarážka určuje, kde má Visual Studio spuštěný kód pozastavit, abyste mohli zkontrolovat hodnoty proměnných či chování paměti, nebo abyste zjistili, jestli se nějaká větev kódu spouští.

1. Ke spuštění aplikace stiskněte **F5** (**Ladit** > **Spustit ladění**).

    Ladicí program se pozastaví na zarážce, kterou jste nastavili (aktuální příkaz je označený žlutě). Teď můžete stav aplikace zkontrolovat tak, že přesunete ukazatel myši nad proměnné v aktuálním rozsahu a použijete okna ladicího programu, například okna **Místní hodnoty** a **Kukátko**.

1. Pokud chcete pokračovat v aplikaci, stiskněte **F5**.

1. Pokud chcete použít nástroje Chrome Developer Tools, stiskněte **F12**. Pomocí těchto nástrojů můžete prozkoumat model DOM a provádět interakce s aplikací pomocí konzoly jazyka JavaScript.

1. Zavřete webový prohlížeč a konzolu.

## <a name="set-and-hit-a-breakpoint-in-the-client-side-react-code"></a>Nastavení a použití zarážky v kódu React na straně klienta

V předchozí části jste připojili ladicí program ke kódu Node.js na straně serveru. K připojení ladicího programu ze sady Visual Studio a používání zarážek v kódu React na straně klienta se v ladicím programu vyžaduje pomoc s identifikací správného procesu. Tady je jedna možnost, jak to udělat.

1. Zavřete všechna okna Chromu.

1. Otevřete příkaz **Spustit** z tlačítka Windows **Start** (klikněte na něj pravým tlačítkem a zvolte **Spustit**) a zadejte následující příkaz:

    `chrome.exe --remote-debugging-port=9222`

    Spustí se Chrome s povoleným laděním.

1. Přepněte do sady Visual Studio a nastavte zarážku v kódu *app-bundle.js* na funkci `render()`, jak je znázorněno na následujícím obrázku:

    ![Nastavení zarážky](../nodejs/media/tutorial-nodejs-react-set-breakpoint-client-code.png)

1. Jako cíl ladění je v sadě Visual Studio vybraný Chrome. Stisknutím **Ctrl**+**F5** (**Ladit** > **Spustit bez ladění**) spusťte aplikaci v prohlížeči.

    Aplikace se otevře na nové kartě prohlížeče.

1. Zvolte **Ladit** > **Připojit k procesu**.

1. V dialogovém okně **Připojit k procesu** v poli **Připojit k** zvolte **Webkit kód** a zadáním slova **chrome** do pole pro filtr vyfiltrujte výsledky hledání.

1. Vyberte proces Chrome se správným portem hostitele (v tomto příkladu 1337) a klikněte na **Připojit**.

    ![Připojení k procesu](../nodejs/media/tutorial-nodejs-react-attach-to-process.png)

    Pokud se v sadě Visual Studio otevřely Průzkumník modelu DOM a konzola jazyka JavaScript, je ladicí program správně připojený. Tyto ladicí nástroje se podobají nástrojům Chrome Developer Tools a nástrojům F12 pro Edge.

    > [!NOTE]
    > Pokud se ladicí program nepřipojí a zobrazí se zpráva „Nelze připojit k procesu. Operace není v aktuálním stavu platná“, zavřete před spuštěním Chromu v režimu ladění všechny instance Chromu pomocí Správce úloh. Můžou být spuštěná rozšíření Chromu, která brání plnému režimu ladění.

1. Kód se zarážkou se už spustil, a proto aktualizujte stránku prohlížeče, aby narazil na zarážku.

    Při pozastavení můžete v ladicím programu zkontrolovat stav aplikace tak, že přesunete ukazatel myši nad proměnné a použijete okna ladicího programu. Můžete v ladicím programu procházet kód pomocí krokování (**F5**, **F10** a **F11**).

    V závislosti na vašem prostředí a stavu prohlížeče můžete narazit na zarážku v souboru *app-bundle.js* nebo v jeho namapovaném umístění v souboru *app.tsx*. V obou případech můžete procházet kód pomocí krokování a zkoumat proměnné.

    * Pokud potřebujete proniknout do kódu v *app.tsx* a nedaří se vám to, připojte ladicí program pomocí dialogového okna **Připojit k procesu**, jak bylo popsáno v předchozím postupu. Otevřete dynamicky generovaném *app.tsx* soubor v Průzkumníku řešení otevřením **dokumentů skriptu** > **app.tsx**zarážku a aktualizovat stránku v prohlížeči (nastavit bod přerušení na řádku kódu, který umožňuje zarážky, například `return` příkaz nebo `var` deklarace).

        Když potřebujete proniknout do kódu v *app.tsx* a nedaří se vám to, můžete také zkusit použít příkaz `debugger;` v *app.tsx* nebo nastavit zarážky v nástrojích Chrome Developer Tools.

    * Pokud potřebujete proniknout do kódu v *app-bundle.js* a nedaří se vám to, odeberte soubor zdrojového mapování *app-bundle.js.map*.

    > [!TIP]
    > Po prvním připojení k procesu podle tohoto postupu se v sadě Visual Studio 2017 můžete rychle znovu připojit ke stejnému procesu tak, že zvolíte **Ladit** > **Znovu připojit k procesu**.

## <a name="next-steps"></a>Další kroky

V tomto kurzu jste se naučili vytvořit aplikaci Node.js a React, transpilovat JSX a provést ladění. Další informace o nástrojích Node.js Tools for Visual Studio najdete na wiki stránce.

> [!div class="nextstepaction"]
> [Node.js Tools for Visual Studio](https://github.com/Microsoft/nodejstools)
