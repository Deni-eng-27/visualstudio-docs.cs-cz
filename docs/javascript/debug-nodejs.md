---
title: Ladění JavaScriptu nebo aplikace TypeScriptu
description: Visual Studio poskytuje podporu pro ladění aplikací JavaScript a TypeScript v aplikaci Visual Studio.
ms.date: 11/01/2019
ms.topic: conceptual
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: jillfra
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: 0405488f6f456f22711498e81789881ffc5a0a8a
ms.sourcegitcommit: 308a2bdbea81df78bffc3a01afce4ab13131fabc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2019
ms.locfileid: "73912994"
---
# <a name="debug-a-javascript-or-typescript-app-in-visual-studio"></a>Ladění JavaScriptu nebo aplikace TypeScriptu v aplikaci Visual Studio

Pomocí sady Visual Studio můžete ladit kód JavaScript a TypeScript. Můžete nastavit a spustit zarážky, připojit ladicí program, kontrolovat proměnné, zobrazit zásobník volání a používat další funkce ladění.

> [!TIP]
> Pokud jste ještě nenainstalovali Visual Studio, navštivte stránku [ke stažení pro Visual Studio](https://visualstudio.microsoft.com/downloads/) a nainstalujte si ji zdarma. V závislosti na typu vývoje aplikací budete možná muset nainstalovat **vývojovou úlohu Node. js** pomocí sady Visual Studio.

## <a name="debug-server-side-script"></a>Ladění skriptu na straně serveru

1. Otevřete projekt v sadě Visual Studio tak, že otevřete soubor JavaScriptu na straně serveru (například *Server. js*), kliknete na hřbet na levé straně a nanastavíte zarážku:

    ![Nastavení zarážky](../javascript/media/tutorial-nodejs-react-set-breakpoint.png)

    Zarážky jsou základní a nejjednodušší funkcí spolehlivého ladění. Zarážka určuje, kde má Visual Studio spuštěný kód pozastavit, abyste mohli zkontrolovat hodnoty proměnných či chování paměti, nebo abyste zjistili, jestli se nějaká větev kódu spouští.

1. Pokud chcete aplikaci spustit, stiskněte klávesu **F5** **(ladění**  > **Spustit ladění**).

    Ladicí program se pozastaví na zarážce, kterou jste nastavili (aktuální příkaz je označený žlutě). Teď můžete stav aplikace zkontrolovat tak, že přesunete ukazatel myši nad proměnné v aktuálním rozsahu a použijete okna ladicího programu, například okna **Místní hodnoty** a **Kukátko**.

1. Pokud chcete pokračovat v aplikaci, stiskněte **F5**.

1. Pokud chcete použít Vývojářské nástroje nebo nástroje F12, stiskněte klávesu **F12**. Pomocí těchto nástrojů můžete prozkoumat model DOM a provádět interakce s aplikací pomocí konzoly jazyka JavaScript.

## <a name="debug-client-side-script"></a>Ladění skriptu na straně klienta

::: moniker range=">=vs-2019"
Visual Studio poskytuje podporu ladění na straně klienta jenom pro Chrome a Microsoft Edge (chrom). V některých scénářích ladicí program automaticky narazí na zarážky v kódu JavaScript a TypeScript a v vložených skriptech v souborech HTML. Informace o ladění skriptu na straně klienta v aplikacích ASP.NET najdete v příspěvku na blogu [ladění JavaScriptu na webu Microsoft Edge a v](https://devblogs.microsoft.com/visualstudio/debug-javascript-in-microsoft-edge-from-visual-studio/) tomto [příspěvku pro Google Chrome](https://devblogs.microsoft.com/aspnet/client-side-debugging-of-asp-net-projects-in-google-chrome).
::: moniker-end
::: moniker range="vs-2017"
Visual Studio poskytuje podporu ladění na straně klienta jenom pro Chrome a Internet Explorer. V některých scénářích ladicí program automaticky narazí na zarážky v kódu JavaScript a TypeScript a v vložených skriptech v souborech HTML. Pro ladění skriptů na straně klienta v aplikacích ASP.NET se podívejte na Blogový příspěvek pro [ladění projektů ASP.NET na straně klienta v Google Chrome](https://devblogs.microsoft.com/aspnet/client-side-debugging-of-asp-net-projects-in-google-chrome/).
::: moniker-end

Pro jiné aplikace než ASP.NET postupujte podle kroků popsaných tady.

### <a name="prepare-your-app-for-debugging"></a>Příprava aplikace pro ladění

Pokud je váš zdroj minifikovaného nebo vytvořen pomocí nástroje pro vyvýšení, jako je TypeScript nebo Babel, je pro nejlepší ladění nutné použít [zdrojové mapy](#generate_source_maps) . Bez map zdrojového kódu můžete ladicí program připojit ke spuštěnému skriptu na straně klienta. Je však možné pouze nastavit a spustit zarážky v souboru minifikovaného nebo provedený soubor, nikoli v původním zdrojovém souboru. Například v aplikaci Vue. js se skript minifikovaného předává jako řetězec do příkazu `eval` a neexistuje žádný způsob, jak tento kód efektivně Krokovat pomocí ladicího programu sady Visual Studio, pokud nepoužíváte zdrojové mapy. Ve složitějších scénářích ladění můžete místo toho použít také nástroje Chrome Vývojářské nástroje nebo F12 pro Microsoft Edge.

Nápovědu k vygenerování zdrojových mapování najdete v tématu [generování zdrojových mapování pro ladění](#generate_source_maps).

### <a name="prepare_the_browser_for_debugging"></a>Příprava prohlížeče pro ladění

::: moniker range=">=vs-2019"
V tomto scénáři použijte Microsoft Edge (chrom), aktuálně pojmenovaný **Microsoft Edge beta** , v integrovaném vývojovém prostředí (IDE) nebo Chrome.
::: moniker-end
::: moniker range="vs-2017"
V tomto scénáři použijte Chrome.
::: moniker-end

1. Zavřete všechna okna pro cílový prohlížeč.

   Jiné instance prohlížeče můžou zabránit otevírání prohlížeče s povoleným laděním. (Rozšíření prohlížeče můžou běžet a bránit úplnému režimu ladění, takže možná budete muset otevřít Správce úloh a najít neočekávané instance Chromu.)

   ::: moniker range=">=vs-2019"
   V případě Microsoft Edge (chrom) vypněte také všechny instance aplikace Chrome. Vzhledem k tomu, že oba prohlížeče používají základ kódu Chromu, dává to nejlepší výsledky.
   ::: moniker-end

2. Spusťte prohlížeč s povoleným laděním.

    ::: moniker range=">=vs-2019"
    Od sady Visual Studio 2019 můžete nastavit příznak `--remote-debugging-port=9222` při spuštění prohlížeče tak, že vyberete **Procházet s...** > z panelu nástrojů **ladění** a pak vyberete **Přidat**a pak nastavíte příznak v poli **argumenty** . Použijte jiný popisný název prohlížeče, jako je například **Edge s laděním** nebo **Chrome s laděním**. Podrobnosti najdete v [poznámkách k verzi](/visualstudio/releases/2019/release-notes-v16.2).

    ![Nastavte prohlížeč tak, aby se otevřel s povoleným laděním.](../javascript/media/tutorial-nodejs-react-edge-with-debugging.png)

    Alternativně otevřete příkaz **Run** z tlačítka **Start** systému Windows (klikněte pravým tlačítkem myši a vyberte možnost **Spustit**) a zadejte následující příkaz:

    `msedge --remote-debugging-port=9222`

    ani

    `chrome.exe --remote-debugging-port=9222`
    ::: moniker-end

    ::: moniker range="vs-2017"
    Otevřete příkaz **Spustit** z tlačítka Windows **Start** (klikněte na něj pravým tlačítkem a zvolte **Spustit**) a zadejte následující příkaz:

    `chrome.exe --remote-debugging-port=9222`
    ::: moniker-end

    Spustí se prohlížeč s povoleným laděním.

    Aplikace ještě není spuštěná, takže získáte prázdnou stránku prohlížeče.

### <a name="attach-the-debugger-to-client-side-script"></a>Připojení ladicího programu ke skriptu na straně klienta

Chcete-li připojit ladicí program ze sady Visual Studio a zarážky volání v kódu na straně klienta, ladicí program potřebuje k identifikaci správného procesu. Tady je jedna možnost, jak to udělat.

1. Přepněte do sady Visual Studio a pak nastavte zarážku ve zdrojovém kódu, což může být soubor JavaScriptu, soubor TypeScript nebo soubor JSX. (Nastavte zarážku na řádek kódu, který umožňuje zarážky, jako je například návratový příkaz nebo deklarace var.)

    ![Nastavení zarážky](../javascript/media/tutorial-nodejs-react-set-breakpoint-client-code.png)

    Chcete-li najít konkrétní kód v souboru s předaným souborem, použijte **kombinaci kláves Ctrl**+**F** (**upravit** > **Najít a nahradit** > **Rychlé hledání**).

    Pro kód na straně klienta pro volání zarážky v souboru TypeScript nebo souboru JSX obvykle vyžaduje použití [zdrojových mapování](#generate_source_maps). Zdrojové mapování musí být správně nakonfigurované, aby podporovalo ladění v aplikaci Visual Studio.

2. Vyberte cílový prohlížeč jako cíl ladění v aplikaci Visual Studio a potom stiskněte **klávesu Ctrl**+**F5** (**ladění** > **Spustit bez ladění**) pro spuštění aplikace v prohlížeči.

    ::: moniker range=">=vs-2019"
    Pokud jste vytvořili konfiguraci prohlížeče s popisným názvem, vyberte jako cíl ladění.
    ::: moniker-end

    Aplikace se otevře na nové kartě prohlížeče.

3. Zvolte **Ladit** > **Připojit k procesu**.

    > [!TIP]
    > Od aplikace Visual Studio 2017 se po prvním připojení k procesu pomocí následujícího postupu můžete rychle znovu připojit ke stejnému procesu výběrem možnosti **ladit** > znovu **připojit k procesu**.

4. V dialogovém okně **připojit k procesu** Získejte filtrovaný seznam instancí prohlížeče, ke kterým se můžete připojit.

    ::: moniker range=">=vs-2019"
    V aplikaci Visual Studio 2019 vyberte správný ladicí program pro cílový prohlížeč, **JavaScript (Chrome)** nebo **JavaScript (Microsoft Edge-chrom)** v poli **připojit k** , do pole Filtr zadejte **Chrome** nebo **Edge** a vyfiltrujte ho. výsledky hledání
    ::: moniker-end
    ::: moniker range="vs-2017"
    V aplikaci Visual Studio 2017 v poli **připojit k** vyberte **WebKit kód** , do pole Filtr zadejte **Chrome** a vyfiltrujte výsledky hledání.
    ::: moniker-end

5. V tomto příkladu vyberte proces prohlížeče se správným hostitelským portem (localhost) a vyberte **připojit**.

    Port (například 1337) se může také zobrazit v poli **název** , abyste si mohli vybrat správnou instanci prohlížeče.

    ::: moniker range=">=vs-2019"
    Následující příklad ukazuje, jak to vypadá v prohlížeči Microsoft Edge (chrom).

    ![Připojení k procesu](../javascript/media/tutorial-nodejs-react-attach-to-process-edge.png)
    ::: moniker-end
    ::: moniker range="vs-2017"
    ![Připojení k procesu](../javascript/media/tutorial-nodejs-react-attach-to-process.png)

    Pokud se v sadě Visual Studio otevřely Průzkumník modelu DOM a konzola jazyka JavaScript, je ladicí program správně připojený. Tyto ladicí nástroje jsou podobné nástrojům Chrome Vývojářské nástroje a F12 pro Microsoft Edge.
    ::: moniker-end

    > [!TIP]
    > Pokud se ladicí program nepřipojí a zobrazí se zpráva "nepovedlo se spustit adaptér ladění" nebo "nelze se připojit k procesu". Operace není v aktuálním stavu platná. pomocí Správce úloh systému Windows zavřete všechny instance cílového prohlížeče před spuštěním prohlížeče v režimu ladění. Rozšíření prohlížeče můžou být spuštěná a zabraňují úplnému režimu ladění.

6. Vzhledem k tomu, že kód se zarážkou již mohl být proveden, aktualizujte stránku prohlížeče. V případě potřeby proveďte akci, která způsobí spuštění kódu se zarážkou.

    Při pozastavení můžete v ladicím programu zkontrolovat stav aplikace tak, že přesunete ukazatel myši nad proměnné a použijete okna ladicího programu. Můžete v ladicím programu procházet kód pomocí krokování (**F5**, **F10** a **F11**). Další informace o funkcích základního ladění naleznete v tématu [první pohled na ladicí program](../debugger/debugger-feature-tour.md).

    Zarážku můžete obdržet v souboru *. js* nebo ve zdrojovém souboru, v závislosti na typu aplikace, krocích, které jste použili dříve, a dalších faktorech, jako je například stav prohlížeče. V obou případech můžete procházet kód pomocí krokování a zkoumat proměnné.

   * Pokud potřebujete přerušit kód ve zdrojovém souboru TypeScript, JSX nebo *. Vue* a nemůžete ho provést, ujistěte se, že je správně nastavené prostředí, jak je popsáno v části [řešení potíží](#troubleshooting_source_maps) .

   * Pokud potřebujete přerušit kód v souboru JavaScriptu (například *App-Bundle. js*) a nemůžete ho provést, odeberte zdrojový soubor mapování souboru *filename. js. map*.

### <a name="troubleshooting_source_maps"></a>Řešení potíží se zarážkami a zdrojovými mapami

Pokud potřebujete přerušit kód ve zdrojovém souboru TypeScript nebo JSX a nemůžete ho provést, použijte příkaz **připojit k procesu** , jak je popsáno v předchozích krocích pro připojení ladicího programu. Ujistěte se, že je prostředí správně nastavené:

* Zavřeli jste všechny instance prohlížeče, včetně rozšíření Chrome (pomocí Správce úloh), abyste mohli spustit prohlížeč v režimu ladění.
      
* Ujistěte se, že jste [spustili prohlížeč v režimu ladění](#prepare_the_browser_for_debugging).

* Ujistěte se, že váš zdrojový soubor mapování obsahuje správnou relativní cestu ke zdrojovému souboru a že neobsahuje nepodporované předpony, jako je například *Webpack:///* , což brání ladicímu programu sady Visual Studio najít zdrojový soubor. Například odkaz, jako je *Webpack:///.app.TSX* , může být opraven na *./app.TSX*. To můžete provést ručně ve zdrojovém souboru mapování (což je užitečné pro testování) nebo pomocí vlastní konfigurace sestavení. Další informace najdete v tématu [generování zdrojových mapování pro ladění](#generate_source_maps).

Případně, pokud potřebujete přerušit kód ve zdrojovém souboru (například *App. TSX*) a nemůžete ho provést, zkuste použít příkaz `debugger;` ve zdrojovém souboru nebo nastavte zarážky v vývojářské nástroje Chrome (nebo v nástrojích F12 pro Microsoft Edge).

## <a name="generate_source_maps"></a>Generovat zdrojové mapování pro ladění

Visual Studio má možnost používat a generovat zdrojové mapy ve zdrojových souborech JavaScriptu. To se často vyžaduje v případě, že je váš zdroj minifikovaného nebo vytvořen pomocí proBabelho, jako je TypeScript nebo. Dostupné možnosti závisí na typu projektu.

* Projekt TypeScript v aplikaci Visual Studio vygeneruje ve výchozím nastavení zdroje mapování. Další informace najdete v tématu [Konfigurace zdrojů mapování pomocí souboru tsconfig. JSON](#configure_source_maps).

* V projektu JavaScriptu můžete generovat zdrojová mapování pomocí sady prostředků, jako je například Webpack, a kompilátoru, jako je například kompilátor TypeScript (nebo Babel), které můžete přidat do projektu. Pro kompilátor TypeScript musíte také přidat soubor *tsconfig. JSON* a nastavit možnost kompilátoru `sourceMap`. Příklad, který ukazuje, jak to provést pomocí základní konfigurace sady Webpack, najdete v tématu [Vytvoření aplikace v Node. js s odpověďmi](../javascript/tutorial-nodejs-with-react-and-jsx.md).

> [!NOTE]
> Pokud začínáte se zdrojovými mapami, přečtěte si [Úvod do zdrojového mapování JavaScriptu](https://www.html5rocks.com/en/tutorials/developertools/sourcemaps/) , než budete pokračovat. 

Pro konfiguraci rozšířených nastavení pro zdrojové mapy použijte buď *tsconfig. JSON* , nebo nastavení projektu v projektu TypeScript, ale ne obojí.

Chcete-li povolit ladění pomocí sady Visual Studio, je nutné zkontrolovat, zda jsou odkazy na zdrojový soubor ve vygenerovaném zdrojovém mapování správné (to může vyžadovat testování). Například pokud používáte sadu Webpack, odkazy ve zdrojovém souboru mapování zahrnují předponu *Webpack:///* , která zabrání sadě Visual Studio najít zdrojový soubor TYPESCRIPT nebo JSX. Konkrétně při opravě tohoto pro účely ladění musí být odkaz na zdrojový soubor (například *App. TSX*) změněn z nějakého typu *Webpack:///./app.TSX* na něco jako *./app.TSX*, což umožňuje ladění ( cesta je relativní vzhledem ke zdrojovému souboru). Následující příklad ukazuje, jak můžete nakonfigurovat mapování zdrojů v nástroji Webpack, což je jeden z nejběžnějších to software instalující, aby fungoval se sadou Visual Studio.

(Jenom pro Webpack) Pokud nastavujete zarážku na TypeScript souboru JSX (spíše než soubor s příponou JavaScriptu), musíte aktualizovat konfiguraci sady Webpack. Například v *Webpack-config. js*může být nutné nahradit následující kód:

```javascript
  output: {
    filename: "./app-bundle.js", // This is an example of the filename in your project
  },
```

s tímto kódem:

```javascript
  output: {
    filename: "./app-bundle.js", // Replace with the filename in your project
    devtoolModuleFilenameTemplate: '[resource-path]'  // Removes the webpack:/// prefix
  },
```

Toto je nastavení jenom pro vývoj, které umožňuje ladění kódu na straně klienta v aplikaci Visual Studio.

U složitých scénářů občas nástroje prohlížeče (**F12**) fungují nejlépe pro ladění, protože nevyžadují změny vlastních předpon.

### <a name="configure_source_maps"></a>Konfigurace zdrojových mapování pomocí souboru tsconfig. JSON

Pokud do projektu přidáte soubor *tsconfig. JSON* , Visual Studio považuje kořen adresáře za projekt TypeScript. Chcete-li přidat soubor, klikněte pravým tlačítkem myši na projekt v Průzkumník řešení a pak zvolte **přidat > nová položka > konfigurační soubor TYPESCRIPT JSON**. Do vašeho projektu se přidá soubor *tsconfig. JSON* podobný následujícímu.

```json
{
  "compilerOptions": {
    "noImplicitAny": false,
    "noEmitOnError": true,
    "removeComments": false,
    "sourceMap": true,
    "target": "es5"
  },
  "exclude": [
    "node_modules",
    "wwwroot"
  ]
}
```

#### <a name="compiler-options-for-tsconfigjson"></a>Možnosti kompilátoru pro tsconfig. JSON

* **inlineSourceMap**: vygenerujte jeden soubor se zdrojovými mapami místo vytvoření samostatného zdrojového mapování pro každý zdrojový soubor.
* **inlineSources**: emituje zdroj společně se zdrojovými mapami v rámci jednoho souboru; vyžaduje, aby byl nastaven *inlineSourceMap* nebo *sourceMap* .
* **mapRoot**: Určuje umístění, kde má ladicí program najít soubory zdrojového mapování ( *. map*) místo výchozího umístění. Tento příznak použijte v případě, že soubory run-time *. map* musí být v jiném umístění než soubory *. js* . Zadané umístění je vložené ve zdrojovém mapování pro přesměrování ladicího programu do umístění souborů *. map* .
* **sourceMap**: vygeneruje odpovídající soubor *. map* .
* **sourceRoot**: Určuje umístění, kde by měl ladicí program najít soubory TypeScript místo zdrojových umístění. Tento příznak použijte v případě, že se zdroje za běhu musí nacházet v jiném umístění, než je umístění v době návrhu. Zadané umístění je vložené ve zdrojovém mapování pro přesměrování ladicího programu na místo, kde jsou umístěny zdrojové soubory.

Další podrobnosti o možnostech kompilátoru najdete v [možnostech kompilátoru](https://www.typescriptlang.org/docs/handbook/compiler-options.html) na stránce v příručce TypeScript.

### <a name="configure-source-maps-using-project-settings-typescript-project"></a>Konfigurace zdrojových mapování pomocí nastavení projektu (projekt TypeScript)

Můžete také nakonfigurovat nastavení mapování zdrojového kódu pomocí vlastností projektu kliknutím pravým tlačítkem myši na projekt a následným výběrem **Vlastnosti projektu > >m ladění TypeScript Build >** .

Tato nastavení projektu jsou k dispozici.

* **Generovat zdrojové mapy** (ekvivalentem **sourceMap** v souboru *tsconfig. JSON*): vygeneruje odpovídající soubor *. map* .
* **Zadat kořenový adresář zdrojových mapování** (ekvivalentem **mapRoot** v souboru *tsconfig. JSON*): Určuje umístění, kde by měl ladicí program najít soubory map místo vygenerovaných umístění. Tento příznak použijte v případě, že soubory run-time *. map* musí být umístěny v jiném umístění než soubory. js. Zadané umístění je vložené ve zdrojovém mapování pro přesměrování ladicího programu na místo, kde jsou umístěny soubory map.
* **Zadejte kořenový adresář souborů TypeScriptu** (ekvivalentní **sourceRoot** ve *tsconfig. JSON*): Určuje umístění, kde by měl ladicí program najít soubory TypeScript místo zdrojových umístění. Tento příznak použijte v případě, že zdrojové soubory za běhu musí být v jiném umístění než v době návrhu. Zadané umístění je vložené ve zdrojovém mapování pro přesměrování ladicího programu na místo, kde jsou umístěny zdrojové soubory.

## <a name="debug-javascript-in-dynamic-files-using-razor-aspnet"></a>Ladění JavaScriptu v dynamických souborech pomocí Razor (ASP.NET)

::: moniker range=">=vs-2019"
Od sady Visual Studio 2019 poskytuje Visual Studio podporu ladění pro Chrome a jenom Microsoft Edge (chrom).
::: moniker-end
::: moniker range="vs-2017"
Visual Studio poskytuje podporu ladění pro Chrome a Internet Explorer.
::: moniker-end

V souborech vygenerovaných pomocí syntaxe Razor (cshtml, VBHTML) ale nemůžete automaticky narazit zarážky. Existují dva přístupy, které můžete použít k ladění tohoto typu souboru:

* **Umístěte příkaz `debugger;`, kde chcete přerušit**: způsobí to, že dynamický skript zastaví provádění a spustí ladění ihned během vytváření.
* **Načíst stránku a otevřít dynamický dokument v sadě Visual Studio**: budete muset otevřít dynamický soubor během ladění, nastavit zarážku a aktualizovat stránku, aby fungovala Tato metoda. V závislosti na tom, jestli používáte Chrome nebo Internet Explorer, najdete soubor pomocí jedné z následujících strategií:

   Pro Chrome použijte **Průzkumník řešení > dokumentů skriptů > YourPageName**.

    > [!NOTE]
    > Pokud používáte Chrome, může se zobrazit zpráva **žádný zdroj není k dispozici mezi \<script > značek**. To je v pořádku, stačí pokračovat v ladění.

   ::: moniker range=">=vs-2019"
   Pro Microsoft Edge (chrom) použijte stejný postup jako Chrome.
   ::: moniker-end

   ::: moniker range="vs-2017"
   Pro Internet Explorer použijte **Průzkumník řešení > dokumentů skriptu > Windows Internet Explorer > YourPageName**.
   ::: moniker-end

Další informace najdete v tématu [ladění projektů ASP.NET na straně klienta v Google Chrome](https://devblogs.microsoft.com/aspnet/client-side-debugging-of-asp-net-projects-in-google-chrome/).
