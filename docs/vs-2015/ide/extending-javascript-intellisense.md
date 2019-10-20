---
title: Rozšíření JavaScriptu IntelliSense | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- JavaScript, intellisense object
- extending JavaScript IntelliSense
- customizing JavaScript IntelliSense
- JavaScript, extending IntelliSense
- IntelliSense [JavaScript], extending
ms.assetid: 004e1ab6-bd7a-4327-9e01-89b9be96ba2f
caps.latest.revision: 43
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: bf16b6fdc307e11875f30cfad6e4bb35580b0b04
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72665755"
---
# <a name="extending-javascript-intellisense"></a>Rozšíření JavaScript IntelliSense
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Funkce rozšíření JavaScript IntelliSense umožňuje přizpůsobit výsledky technologie IntelliSense v editoru JavaScriptu pro knihovny třetích stran. To může zlepšit prostředí vývojářů, kteří používají tyto knihovny.

 Služba jazyka JavaScript poskytuje funkce IntelliSense pro knihovny JavaScriptu třetích stran, které jsou přidány do projektu. Pro většinu knihoven je dokončování příkazů k dispozici automaticky pomocí jazykové služby. Následující ilustrace znázorňuje příklad dokončování příkazů:

 ![Příklad dokončování příkazů](../ide/media/js-intellisense-completion.png "js_intellisense_completion")

 Pokud vaše knihovna obsahuje popisy proměnných, funkcí a objektů ve standardních značkách komentářů JavaScriptu (//), automaticky ve výchozím nastavení výhodně přináší funkce rozšiřitelnosti IntelliSense, které poskytují popisné informace v místním okně, které zobrazí napravo od prvků v seznamu pro doplňování nebo při zadání otevírací závorky ve volání funkce. Komentáře v místním okně obsahují popis člena. Následující příklad ukazuje rozbalovací okno pro seznam dokončení.

 ![Příklad okna&#45;rychlé informace – rozevírací seznam](../ide/media/js-intellisense-quickinfo.png "js_intellisense_quickinfo")

 Chcete-li dále vylepšit prostředí pro vývojáře, můžete v místním okně poskytnout vývojářům informace o typu. Informace o typu můžete zadat pomocí [komentářů dokumentace XML](../ide/xml-documentation-comments-javascript.md) jazyka JavaScript namísto standardních značek komentářů. Komentáře k dokumentaci XML přidáte pomocí značek komentářů se třemi lomítky (///) a definované sady elementů XML.

 Alternativně můžete zadat informace o typu pomocí rozšíření JavaScript IntelliSense. Tato funkce umožňuje přizpůsobit výsledky technologie IntelliSense vytvořením rozšíření JavaScriptu a jejich přidáním do kontextu skriptu. V rozšíření, které je souborem JavaScriptu, se přihlásíte k odběru událostí, které jsou zpřístupněny objektem `intellisense` jazykové služby. Rozšíření JavaScript IntelliSense je preferované řešení pro knihovny, pokud vzor chování v knihovně brání službě jazyka JavaScript v poskytnutí požadované úrovně podpory technologie IntelliSense, a pokud alternativa k deklarativnímu XML Také je potřeba komentovat dokumentaci. Přizpůsobením výsledků technologie IntelliSense můžete vytvořit prvotřídní prostředí IntelliSense bez ohledu na vzory chování, které by mohly omezit výchozí možnosti jazykové služby. Další informace najdete v tématu [dokončování příkazů pro identifikátory](../ide/statement-completion-for-identifiers.md).

## <a name="adding-an-extension-to-the-script-context"></a>Přidání rozšíření do kontextu skriptu
 Aby bylo rozšíření technologie IntelliSense spuštěno, je nutné jej přidat do kontextu aktuálního skriptu. Toto rozšíření lze automaticky přidat do kontextu skriptu pomocí mechanismu automatického zjišťování, nebo můžete ručně přidat rozšíření do kontextu skriptu pomocí referenčních skupin nebo direktivy Reference.

 Mechanismus automatického zjišťování umožňuje, aby služba jazyka automaticky nalezla rozšíření, která následují jako knihovna názvů souborů *Library*. js, která se nachází ve stejném adresáři jako knihovna, do které rozšíření vztahuje. Například platné rozšíření pro knihovnu jQuery by bylo jQuery. IntelliSense. js. U více restriktivních rozšíření jQuery můžete použít názvy souborů, například jQuery 1.7.1. IntelliSense. js (rozšíření pro konkrétní verzi) nebo jQuery. UI. IntelliSense. js (rozšíření pro vymezenou knihovnu jQuery). Nejvíc omezující verze rozšíření se používá, pokud je pro danou knihovnu nalezeno více rozšíření.

 Chcete-li použít rozšíření pro všechny soubory projektu JavaScriptu, je možné, že místo toho chcete přidat rozšíření do referenční skupiny. Existuje několik typů referenčních skupin, včetně implicitních odkazů a těch, které obsahují odkazy na vyhrazené pracovní procesy. Chcete-li přidat rozšíření, je obvykle nutné přidat soubor jako implicitní referenční skupinu, buď **implicitně (Windows)** , **implicitní (Web)** . Implicitní odkazy jsou v oboru pro každý soubor. js otevřený v editoru kódu. Když použijete tuto metodu, musíte přidat rozšíření i soubor, který přípona doplňuje.

 Stránku **IntelliSense** v dialogovém okně **Možnosti** použijte k přidání rozšíření jako referenční skupiny. Stránku **IntelliSense** můžete otevřít výběrem možnosti **nástroje**, možnosti na řádku nabídek a následným výběrem **Možnosti** **textový editor**, **JavaScript**, **IntelliSense**, **odkazy**. Další informace o referenčních skupinách naleznete v tématu [JavaScript IntelliSense](../ide/javascript-intellisense.md) and [Options, textový editor, JavaScript, IntelliSense](../ide/reference/options-text-editor-javascript-intellisense.md).

 Chcete-li použít rozšíření pro určitou sadu souborů, použijte direktivu Reference. Když použijete tuto metodu, musíte odkazovat na rozšíření i na soubor, který rozšíření doplňuje. Informace o použití direktivy Reference naleznete v tématu [JavaScript IntelliSense](../ide/javascript-intellisense.md).

## <a name="handling-intellisense-events"></a>Zpracování událostí IntelliSense
 Funkce rozšiřitelnosti umožňuje přizpůsobit výsledky technologie IntelliSense pomocí přihlášení k odběru událostí, jako je například událost `statementcompletion` `intellisense` objektu služby jazyka. Následující příklad ukazuje jednoduché rozšíření, které je používáno službou jazyka ke skrytí členů, které začínají podtržítkem z dokončování příkazů. Tento kód je obsažen v underscorefilter. js a je ve složce \\ \\*Instalační cesta \JavaScript\References sady Visual Studio*.

```javascript
intellisense.addEventListener('statementcompletion', function (event) {
    if (event.targetName === "this") return;

    var filterRegex;

    if (event.target === undefined || event.target === window)
        filterRegex = /^_.*\d{2,}/;
    else
        filterRegex = /^_.*/;

    event.items = event.items.filter(function (item) {
        return !filterRegex.test(item.name);
    });
});
```

 V předchozím kódu rozšíření kontroluje [vlastnost TargetName](#TargetName) a vlastnosti [cílové vlastnosti](#Target) objektu události `statementcompletion` tak, aby vyloučil objekty, jako jsou `this` a `window`, a aby se zajistilo, že platný seznam dokončení příkazu může být přiřazen. Pokud je možné identifikovat seznam dokončení, rozšíření aktualizuje kolekci [vlastností položky](#Items) dokončování příkazů vyfiltrováním členů, které začínají podtržítkem.

 Další příklady najdete ve složce \\ \\*Instalační cesta \JavaScript\References sady Visual Studio*. Soubor showPlainComments. js v této složce obsahuje příklady použití jiných událostí k zajištění výchozí podpory technologie IntelliSense pro standardní značky komentářů jazyka JavaScript (//). Podobně jako underscorefilter. js je showPlainComments. js již k dispozici jako funkční rozšíření a výsledné informace technologie IntelliSense lze zobrazit při použití značek komentářů v kódu pro proměnné, funkce a objekty. Další příklady naleznete v tématu [Příklady kódu](#CodeExamples).

> [!WARNING]
> Pokud upravíte soubory rozšíření, které jsou součástí sady Visual Studio, můžete zakázat technologii JavaScript IntelliSense nebo funkci podporovanou rozšířením.

 V kódu rozšíření můžete vytvořit obslužné rutiny pro následující typy událostí pomocí `addEventListener`:

- `statementcompletion`, který přidá obslužnou rutinu pro událost dokončení příkazu. Dokončování příkazů poskytuje seznam členů pro konkrétní typ, který se zobrazí po zadání speciálního znaku, jako je například tečka (.), nebo seznam identifikátorů, které se zobrazí při psaní nebo po stisknutí kombinace kláves CTRL + J. Obslužná rutina obdrží objekt události typu `CompletionEvent`, který podporuje následující členy: [vlastnost Items](#Items), [vlastnost target](#Target), [vlastnost TargetName](#TargetName)a [vlastnost oboru](#Scope).

- `signaturehelp`, který přidá obslužnou rutinu pro informace o parametrech technologie IntelliSense. Informace o parametrech poskytují informace o počtu, názvech a typech parametrů vyžadovaných funkcí. Obslužná rutina obdrží objekt události typu `SignatureHelpEvent`, který podporuje následující členy: [vlastnost target](#Target), [Vlastnost parentObject](#ParentObject), [Vlastnost functionComments](#FunctionComments), vlastnost [functionHelp](#FunctionHelp).

- `statementcompletionhint`, který přidá obslužnou rutinu pro rychlé informace technologie IntelliSense. Okno rychlé informace zobrazuje úplnou deklaraci identifikátorů ve vašem kódu. Obslužná rutina obdrží objekt události typu `CompletionHintEvent`, který podporuje následující členy: [Vlastnost completionItem](#CompletionItem)a [vlastnost symbolHelp](#SymbolHelp).

  Příklady, které zobrazují funkce technologie IntelliSense, jako je dokončování příkazů, informace o parametrech a rychlé informace, naleznete v tématu [Using IntelliSense](../ide/using-intellisense.md).

> [!NOTE]
> V jazyce JavaScript rychlé informace odkazuje na automaticky otevírané okno, které se zobrazí napravo od seznamu pro doplňování. Rychlé informace nelze vyvolat ručně.

## <a name="intellisenseObject"></a>IntelliSense – objekt
 V následující tabulce jsou uvedeny funkce, které jsou k dispozici pro objekt `intellisense`. Objekt `intellisense` je k dispozici pouze v době návrhu.

|Funkce|Popis|
|--------------|-----------------|
|`addEventListener(type, handler);`|Přidá obslužnou rutinu události pro událost IntelliSense.<br /><br /> `type` je řetězcová hodnota. Platné hodnoty zahrnují `statementcompletion`, `signaturehelp` a `statementcompletionhint`.<br /><br /> `handler` je funkce obslužné rutiny události, která přijímá objekt události jednoho z následujících typů:<br /><br /> -    `CompletionEvent`, který se používá pro událost `statementcompletion`.<br />-    `SignatureHelpEvent`, který se používá pro událost `signaturehelp`.<br />-    `CompletionHintEvent`, který se používá pro událost `statementcompletionhint`.<br /><br /> Příklady použití této funkce naleznete v tématu [Příklady kódu](#CodeExamples).|
|`annotate(obj, doc);`|Určuje dokumentaci pro objekt zkopírováním dokumentačních komentářů z jednoho objektu na jiný objekt.<br /><br /> `obj` určuje objekt, ke kterému se má kopírovat dokumentace.<br /><br /> `doc` určuje objekt, ze kterého se má kopírovat dokumentace.<br /><br /> Příklad, který ukazuje, jak používat tuto funkci, najdete v tématu [Přidání poznámek IntelliSense](#Annotations).|
|`getFunctionComments(func);`|Vrátí komentáře pro zadanou funkci.<br /><br /> `func` Určuje funkci, pro kterou jsou vraceny komentáře.<br /><br /> Parametr `func` můžete nastavit pomocí `completionItem.value`.<br /><br /> Vrácený objekt `functionComments` obsahuje následující členy: `above`, `inside` a `paramComment`. Další informace najdete v tématu vlastnost [functionComments](#FunctionComments) .<br /><br /> `getFunctionComments` lze volat pouze v rámci jedné z obslužných rutin událostí registrovaných `addEventListener`.<br /><br /> Příklad, který ukazuje, jak používat tuto funkci, naleznete v tématu \\ \\ \JavaScript\References\showPlainComments.js.*instalace sady Visual Studio*.|
|`logMessage(msg);`|Odesílá diagnostické zprávy do okna výstup.<br /><br /> `msg` je řetězec, který obsahuje zprávu.<br /><br /> Příklad, který ukazuje, jak používat tuto funkci, najdete v tématu [posílání zpráv do okno výstup](#Logging).|
|`nullWithCompletionsOf(value);`|Vrací speciální hodnotu null, pro kterou je seznam pro doplňování určen objektem předaným v parametru `value`.<br /><br /> `value` určuje seznam dokončení pro vrácenou hodnotu. `value` může být libovolný typ.<br /><br /> Návratová hodnota null je v době návrhu považována za null, ale seznam dokončení pro vrácenou hodnotu je stejný jako seznam dokončení pro parametr `value`.<br /><br /> Jedním z použití této funkce je poskytnout technologii IntelliSense pro návratovou hodnotu, pokud je návratový typ předvídatelný za běhu, ale návratová hodnota je `null` v době návrhu.|
|`redirectDefinition(func, definition);`|Instruuje IntelliSense, aby místo původní funkce Func použil poskytnutou funkci definice, a to v případě, že je požadován parametr help nebo **Přejít k definici** .<br /><br /> `func` určuje cílovou funkci.<br /><br /> `definition` Určuje funkci, která se má použít místo cílové funkce pro informace o parametrech a **Přejít k definici**.|
|`setCallContext(func, thisArg);`|Nastaví kontext volání neboli obor pro určenou funkci.<br /><br /> `func` Určuje funkci, pro kterou chcete nastavit obor.<br /><br /> `thisArg` je literál objektu, na který může odkazovat klíčové slovo `this` na, které určuje nový obor člena. Můžete zahrnout argumenty, které se mají předat tomuto parametru, například `intellisense.setCallContext(func, { thisArg: "", args: [23,2] });`<br /><br /> `setCallContext` poskytuje chování podobné jako `Function.prototype.bind`, s tím rozdílem, že se používá pouze pro podporu technologie IntelliSense v době návrhu. Můžete použít `setCallContext` k nastavení rozsahu funkce, pokud potřebujete simulovat volání kódu, který není jinak dostupný, takže při volání funkce bude volání funkce zahrnovat správný rozsah a argumenty.|
|`undefinedWithCompletionsOf(value);`|Vrací speciální nedefinovanou hodnotu, pro kterou je seznam dokončení určen objektem předaným v parametru `value`.<br /><br /> `value` určuje seznam dokončení pro vrácenou hodnotu. `value` může být libovolný typ.<br /><br /> Nedefinovaná návratová hodnota je považována za nedefinovanou v době návrhu, ale seznam dokončení pro vrácenou hodnotu je stejný jako seznam dokončení pro parametr `value`.<br /><br /> Jedním z těchto funkcí je poskytnout IntelliSense pro návratovou hodnotu, pokud je návratový typ předvídatelný za běhu, ale návratová hodnota není definována v době návrhu.|
|`version()`|Vrátí verzi sady Visual Studio.|

## <a name="event-members"></a>Členové události
 V následujících částech jsou popsány členové, kteří jsou zpřístupněni v objektu události pro následující události: `statementcompletion`, `signaturehelp` a `statementcompletionhint`.

### <a name="CompletionItem"></a>Vlastnost completionItem
 Vrátí identifikátor, který je znám jako položka dokončení, pro kterou je automaticky otevírané okno rychlé informace požadováno. Tato vlastnost je k dispozici pro objekt `statementcompletionhint` události a vlastnost [Items](#Items) objektu události `statementcompletion`.

 Návratová hodnota: objekt `completionItem`

 Níže jsou uvedené členy objektu `completionItem`:

- `name`. Čtení i zápis při použití v kolekci `items`; v opačném případě jen pro čtení. Vrátí řetězec identifikující položku dokončení.

- `kind`. Čtení i zápis při použití v kolekci `items`; v opačném případě jen pro čtení. Vrátí řetězec, který představuje typ položky dokončení. Možné hodnoty jsou metoda, pole, vlastnost, parametr, proměnná a vyhrazené.

- `glyph`. Čtení i zápis při použití v kolekci `items`; v opačném případě jen pro čtení. Vrátí řetězec, který představuje ikonu, která se zobrazí v seznamu pro doplňování. Možné hodnoty pro `glyph` použít následující formát: vs:*GlyphType*, kde *GlyphType* odpovídá jazykově nezávislému členu v <xref:Microsoft.VisualStudio.Language.Intellisense.StandardGlyphGroup> výčtu. @No__t_0 je například jedna možná hodnota pro `glyph`. Pokud `glyph` není nastavena, vlastnost `kind` určuje výchozí ikonu.

- `parentObject`. Jen pro čtení. Vrátí nadřazený objekt.

- `value`. Jen pro čtení. Vrátí objekt, který představuje hodnotu položky dokončení.

- `comments`. Jen pro čtení. Vrátí řetězec, který obsahuje komentáře, které jsou nad polem nebo proměnnou.

- `scope`. Jen pro čtení. Vrátí rozsah položky dokončení. Možné hodnoty jsou globální, místní, parametr a člen.

### <a name="Items"></a>Items – vlastnost
 Získá nebo nastaví pole položek dokončování příkazů. Každý prvek v poli je objekt [vlastnosti completionItem](#CompletionItem) . Vlastnost `items` je k dispozici pro objekt události `statementcompletion`.

 Návratová hodnota: pole

### <a name="FunctionComments"></a>Vlastnost functionComments
 Vrátí komentáře pro funkci. Tato vlastnost je k dispozici pro objekt `signaturehelp` události.

 Návratová hodnota: objekt `comments`

 Níže jsou uvedené členy objektu `comments`:

- `above`. Vrátí komentáře nad funkcí.

- `inside`. Vrátí komentáře uvnitř funkce, obvykle ve formátu VSDoc.

- `paramComments`. Vrátí pole reprezentující komentáře pro každý parametr ve funkci. Mezi členy pole patří:

  - `name`. Vrátí řetězec představující název parametru.

  - `comment`. Vrátí řetězec, který obsahuje komentář k parametru.

### <a name="FunctionHelp"></a>Vlastnost functionHelp
 Vrátí nápovědu pro funkci. Tato vlastnost je k dispozici pro objekt `signaturehelp` události.

 Návratová hodnota: objekt `functionHelp`

 Níže jsou uvedené členy objektu `functionHelp`:

- `functionName`. Čtení a zápis Vrátí řetězec, který obsahuje název funkce.

- `signatures`. Čtení a zápis Získá nebo nastaví pole signatur funkcí. Každý prvek v poli je objekt `signature`. Některé vlastnosti `signature`, jako je například `locid`, odpovídají běžným atributům [dokumentačních komentářů XML](../ide/xml-documentation-comments-javascript.md) .

  Mezi členy objektu `signature` patří:

  - `description`. Čtení a zápis Vrátí řetězec, který popisuje funkci.

  - `locid`. Čtení a zápis Vrátí identifikátor řetězce, který obsahuje informace o lokalizaci funkce.

  - `helpKeyword`. Čtení a zápis Vrátí řetězec, který obsahuje klíčové slovo help.

  - `externalFile`. Čtení a zápis Vrátí řetězec, který představuje soubor, který obsahuje ID člena.

  - `externalid`. Čtení a zápis Vrátí řetězec, který představuje ID člena funkce.

  - `params`. Čtení a zápis Získá nebo nastaví pole parametrů pro funkci. Každý prvek v poli parameters je objekt `parameter`, který obsahuje vlastnosti, které odpovídají následujícím atributům prvku [\<param >](../ide/param-javascript.md) :

    - `name`. Čtení a zápis Vrátí řetězec, který představuje název parametru.

    - `type`. Čtení a zápis Vrátí řetězec, který představuje typ parametru.

    - `elementType`. Čtení a zápis Pokud je typ `Array`, vrátí řetězec, který představuje typ prvků v poli.

    - `description`. Čtení a zápis Vrátí řetězec, který popisuje parametr.

    - `locid`. Čtení a zápis Vrátí identifikátor řetězce, který obsahuje informace o lokalizaci funkce.

    - `optional`. Čtení a zápis Vrátí řetězec, který označuje, zda je parametr volitelný. `true` označuje, že parametr je nepovinný.  `false` označuje, že není.

  - `returnValue`. Čtení a zápis Získá nebo nastaví návratovou hodnotu objektu s vlastnostmi, které odpovídají následujícím atributům [\<returns >](../ide/returns-javascript.md) elementu:

    - `type`. Čtení a zápis Vrátí řetězec, který představuje návratový typ.

    - `elementType`. Čtení a zápis Pokud je typ `Array`, vrátí řetězec, který představuje typ prvků v poli.

    - `description`. Čtení a zápis Vrátí řetězec, který popisuje vrácenou hodnotu.

    - `locid`. Čtení a zápis Vrátí identifikátor řetězce, který obsahuje informace o lokalizaci funkce.

    - `helpKeyword`. Čtení a zápis Vrátí řetězec, který obsahuje klíčové slovo help.

    - `externalFile`. Čtení a zápis Vrátí řetězec, který představuje soubor, který obsahuje ID člena.

    - `externalid`. Čtení a zápis Vrátí řetězec, který představuje ID člena funkce.

### <a name="ParentObject"></a>Vlastnost parentObject
 Vrátí nadřazený objekt členské funkce. Například pro `document.getElementByID` `parentObject` vrátí objekt `document`. Tato vlastnost je k dispozici pro objekt `signaturehelp` události.

 Návratová hodnota: Object

### <a name="Target"></a>Cílová vlastnost
 Vrátí objekt, který představuje položku nalevo od znaku triggeru, což je tečka (.). V případě funkcí `target` vrátí funkci, pro kterou jsou požadovány informace o parametrech. Tato vlastnost je k dispozici pro objekty událostí `statementcompletion` a `signaturehelp`.

 Návratová hodnota: Object

### <a name="TargetName"></a>cílový_název – vlastnost
 Vrátí řetězec, který představuje cíl. Například pro "This." `targetName` vrátí "This". Pro "A. B" (Pokud je kurzor po "B"), `targetName` vrátí "B". Tato vlastnost je k dispozici pro objekt `statementcompletion` události.

 Návratová hodnota: řetězec

### <a name="SymbolHelp"></a>Vlastnost symbolHelp
 Vrátí položku dokončení, pro kterou je místní okno s informacemi o rychlém zobrazení požadováno. Tato vlastnost je k dispozici pro objekt `statementcompletionhint` události.

 Návratová hodnota: objekt `symbolHelp`.

 Některé vlastnosti objektu `symbolHelp`, například `locid`, odpovídají běžným atributům [dokumentačních komentářů XML](../ide/xml-documentation-comments-javascript.md) .

 Níže jsou uvedené členy objektu `symbolHelp`:

- `name`. Čtení a zápis Vrátí řetězec, který obsahuje název identifikátoru.

- `symbolType`. Čtení a zápis Vrátí řetězec, který představuje typ symbolu. Možné hodnoty zahrnují neznámý typ Boolean, číslo, řetězec, objekt, funkce, pole, datum a regulární výraz.

- `symbolDisplayType`. Čtení a zápis Vrátí řetězec, který obsahuje název typu, který se má zobrazit. Pokud `symbolDisplayType` není nastavená, použije se `symbolType`.

- `elementType`. Čtení a zápis Pokud je `symbolType` `Array`, vrátí řetězec, který představuje typ prvků v poli.

- `scope`. Čtení a zápis Vrátí řetězec, který představuje rozsah symbolu. Mezi možné hodnoty patří globální, místní, parametr a člen.

- `description`. Čtení a zápis Vrátí řetězec, který obsahuje popis symbolu.

- `locid`. Čtení a zápis Vrátí identifikátor řetězce, který obsahuje informace o lokalizaci o symbolu.

- `helpKeyword`. Čtení a zápis Vrátí řetězec, který obsahuje klíčové slovo help.

- `externalFile`. Čtení a zápis Vrátí řetězec, který představuje soubor, který obsahuje ID člena.

- `externalid`. Čtení a zápis Vrátí řetězec, který představuje ID člena symbolu.

- `functionHelp`. Čtení a zápis Vrátí [Vlastnost functionHelp](#FunctionHelp), která může obsahovat informace, pokud je funkce `symbolType`.

### <a name="Scope"></a>Vlastnost oboru
 Vrátí rozsah dokončení události. Možné hodnoty pro rozsah dokončení jsou globální a členy. Tato vlastnost je k dispozici pro objekt `statementcompletion` události.

 Návratová hodnota: řetězec

## <a name="debugging-intellisense-extensions"></a>Ladění rozšíření technologie IntelliSense
 Nemůžete ladit rozšíření, ale můžete použít funkci [objektu technologie IntelliSense](#intellisenseObject) k odeslání informací do okna výstup aplikace Visual Studio. Příklad, který ukazuje, jak používat tuto funkci, najdete v tématu [posílání zpráv do okno výstup](#Logging) dále v tomto tématu. Aby `logMessage` fungoval, musí být v rozšíření registrována aspoň jedna obslužná rutina události.

## <a name="CodeExamples"></a>Příklady kódu
 Tato část obsahuje příklady kódu, které ukazují, jak používat rozhraní API pro rozšiřitelnost technologie IntelliSense. Existují i jiné způsoby, jak tato rozhraní API používat. Další příklady najdete v následujících souborech ve složce \\ \\*Instalační cesta \JavaScript\References sady Visual Studio*. Jedná se o pracovní příklady, které používá služba jazyka JavaScript.

- underscoreFilter. js. Tento kód skrývá soukromé členy z IntelliSense. Obsahuje obslužné rutiny událostí pro událost `statementcompletion`.

- showPlainComments. js. Tento kód poskytuje podporu technologie IntelliSense pro standardní komentáře. Obsahuje obslužné rutiny událostí pro `signaturehelp` a `statementcompletionhint` události.

### <a name="Annotations"></a>Přidávání poznámek IntelliSense
 Následující postup ukazuje, jak poskytnout podporu dokumentace technologie IntelliSense pro knihovnu třetí strany bez změny přímo v knihovně. K tomu můžete použít `intellisense.annotate` v rozšíření.

 Aby tento příklad fungoval, potřebujete následující soubory JavaScriptu v projektu:

- demoLib. js je soubor projektu, který představuje knihovnu třetí strany.

- demoLib. IntelliSense. js, což je rozšíření technologie IntelliSense. Tento soubor není nutné zahrnout do projektu, ale musí být ve stejné složce jako exampleLib. js.

- stráveného. js je soubor projektu, který představuje kód aplikace.

##### <a name="to-add-an-intellisense-annotation"></a>Přidání anotace IntelliSense

1. Do demoLib. js přidejte následující kód.

    ```javascript
    function someFunc(a) { };
    var rectangle;

    ```

2. Do demoLib. IntelliSense. js přidejte následující kód.

    ```javascript
    intellisense.annotate(someFunc, function (a) {
        /// <signature>
        /// <summary>Description of someFunc</summary>
        /// <param name="a">Param a</param>
        /// </signature>
    });

    intellisense.annotate(window, {
        // This is a comment on a global variable named rectangle.
        rectangle: undefined
    });
    ```

3. Přidejte následující direktivu Reference jako první řádek v stráveného. js. Zde použitá cesta označuje, že soubory JavaScriptu jsou ve stejné složce.

    ```javascript
    /// <reference path="demoLib.js" />

    ```

4. V stráveného. js zadejte následující kód. V rozšíření zobrazeném jako informace o parametrech technologie IntelliSense se zobrazí dokumentační komentáře XML.

     ![Příklad znázorňující použití technologie IntelliSense. opatřit poznámkami](../ide/media/js-intellisense-annotate-paraminfo.png "js_intellisense_annotate_paraminfo")

5. V stráveného. js zadejte následující kód. Při psaní se zobrazí standardní komentáře v rozšíření zobrazené jako rychlé informace technologie IntelliSense.

     ![Příklad znázorňující použití technologie IntelliSense. opatřit poznámkami](../ide/media/js-intellisense-annotations.png "js_intellisense_annotations")

### <a name="Logging"></a>Posílání zpráv do okno Výstup
 Následující postup ukazuje, jak odeslat zprávy do okna výstup. Můžete odesílat zprávy, které vám pomohou ladit rozšíření technologie IntelliSense.

 Aby tento příklad fungoval, potřebujete následující soubory JavaScriptu v projektu:

- exampleLib. js je soubor projektu, který představuje knihovnu třetí strany.

- exampleLib. IntelliSense. js, což je rozšíření technologie IntelliSense. Tento soubor není nutné zahrnout do projektu, ale musí být ve stejné složce jako exampleLib. js.

- stráveného. js je soubor projektu, který představuje kód aplikace.

##### <a name="to-send-a-message-to-the-output-window"></a>Odeslání zprávy do okna výstup

1. Do exampleLib. js přidejte následující kód.

    ```javascript
    var someVar = {
        a: 1,
        b: 'hello'
    };
    ```

2. Do exampleLib. IntelliSense. js přidejte následující kód.

    ```javascript
    intellisense.addEventListener('statementcompletion', function (e) {
        // Prints out statement completion info: Either (1) the member
        // list, if the trigger character was typed, or (2) the
        // statement completion identifiers.
        // e.target represents the object left of the trigger character.
        intellisense.logMessage(
            e.target ? 'member list requested, target: ' + e.targetName : 'statement completion for current scope requested');

        // Prints out all statement completion items.
        e.items.forEach(function (item) {
            intellisense.logMessage('[completion item] ' + item.name + ', kind:' + item.kind + ', scope:' + item.scope + ', value:' + item.value);
        });
    });
    ```

3. Přidejte následující direktivu Reference jako první řádek v stráveného. js. Zde použitá cesta označuje, že soubory JavaScriptu jsou ve stejné složce.

    ```javascript
    /// <reference path="exampleLib.js" />

    ```

4. V okně výstup vyberte v seznamu **Zobrazit výstup z** možnost **JavaScript Language Service** . (Chcete-li zobrazit okno výstup, vyberte možnost **výstup** z nabídky zobrazení.)

5. V stráveného. js zadejte následující kód. Když zadáte, zobrazí se v okně výstup zprávy ze služby jazyka. První zpráva v okně výstup označuje, že bylo vyžádáno dokončování příkazů pro aktuální obor.

    ```javascript
    some
    ```

     Následuje částečný pohled na výstup, který byste měli vidět.

    ```scr
    03:16:14.3113: statement completion for current scope requested
    03:16:14.3113: [completion item] break, kind:reserved, scope:undefined, value:undefined
    03:16:14.3113: [completion item] case, kind:reserved, scope:undefined, value:undefined
    03:16:14.3113: [completion item] catch, kind:reserved, scope:undefined, value:undefined

    …
    ```

6. V okně výstup klikněte na tlačítko **Vymazat vše** .

7. Zadejte následující kód. První zpráva v okně výstup označuje, že byl požadován seznam členů.

    ```javascript
    someVar.
    ```

     Tady je částečný pohled na výstup, který byste měli vidět:

    ```scr
    03:17:43.4032: member list requested, target: someVar
    03:17:43.4032: [completion item] a, kind:field, scope:member, value:1
    03:17:43.4032: [completion item] b, kind:field, scope:member, value:hello
    03:17:43.4032: [completion item] constructor, kind:method, scope:member, value:

    …
    ```

### <a name="Icons"></a>Změna ikon technologie IntelliSense
 Následující postup ukazuje, jak ve výchozím nastavení měnit ikony zobrazené technologií IntelliSense. To může být užitečné, když poskytujete informace IntelliSense o konceptech specifických pro knihovnu, jako jsou například obory názvů, třídy, rozhraní a výčty.

 Dostupné hodnoty ikon najdete v tématu <xref:Microsoft.VisualStudio.Language.Intellisense.StandardGlyphGroup>.

 Aby tento příklad fungoval, potřebujete následující soubory JavaScriptu v projektu:

- exampleLib. js je soubor projektu, který represens knihovnu třetí strany.

- exampleLib. IntelliSense. js, což je rozšíření technologie IntelliSense. Tento soubor není nutné zahrnout do projektu, ale musí být ve stejné složce jako exampleLib. js.

- stráveného. js je soubor projektu, který představuje kód aplikace.

##### <a name="to-change-the-icons"></a>Změna ikon

1. Do exampleLib. js přidejte následující kód.

    ```javascript
    function Namespace(name) {
        this._isNamespace = true;
        window[name] = this;
    };

    function Enum(values) {
        var e = Object.create(values);
        e._isEnum = true;
        return e;
    };

    var SomeNamespace = new Namespace('SomeNamespace');
    // A constructor function is considered a class.
    SomeNamespace.SomeClass1 = function () { }
    SomeNamespace.Enum1 = new Enum({ VALUE1: 0, VALUE2: 1 });
    ```

2. Do exampleLib. IntelliSense. js přidejte následující kód.

    ```javascript
    intellisense.addEventListener('statementcompletion', function (e) {
        e.items.forEach(function (item) {
            // Detect a namespace by using the _isNamespace flag.
            if (item.value && item.value._isNamespace) {
                item.glyph = 'vs:GlyphGroupNamespace';
                }

            if (item.parentObject && item.parentObject._isNamespace) {
                // The item is a member of a namespace.

                // All constructor functions that are part of a namespace
                // are considered classes.
                // A constructor function starts with
                // an uppercase letter by convention.
                if (typeof item.value == 'function' && (item.name[0].toUpperCase()
                    == item.name[0])) {
                    item.glyph = 'vs:GlyphGroupClass';
                }

                // Detect an enumeration by using the _isEnum flag.
                if (item.value && item.value._isEnum) {
                    item.glyph = 'vs:GlyphGroupEnum';
                }
            }
        });
    });

    intellisense.addEventListener('statementcompletionhint', function (e) {
        if (e.completionItem.value) {
            if (e.completionItem.value._isNamespace) {
                e.symbolHelp.symbolDisplayType = 'Namespace';
            }
            if (e.completionItem.value._isEnum) {
                e.symbolHelp.symbolDisplayType = 'Enum';
            }
        }
    });
    ```

3. Přidejte následující direktivu Reference jako první řádek v stráveného. js. Zde použitá cesta označuje, že soubory JavaScriptu jsou ve stejné složce.

    ```javascript
    /// <reference path="exampleLib.js" />

    ```

4. V stráveného. js zadejte následující kód. Když zadáte, uvidíte, že se ikona pro obor názvů změnila na "{}", jak je použito v C#.

     ![Příklad ukazující použití vlastnosti glyf](../ide/media/js-intellisense-glyph-namespace.png "js_intellisense_glyph_namespace")

5. V stráveného. js zadejte následující kód. Při psaní se zobrazí nová ikona výčtu pro člena Enum1 a nová ikona třídy pro člena SomeClass1.

     ![Příklad ukazující použití vlastnosti glyf](../ide/media/js-intellisense-glyph-class-enum.png "js_intellisense_glyph_class_enum")

### <a name="Overriding"></a>Zamezení běhových efektů na výsledcích technologie IntelliSense
 Služba jazyka JavaScript spouští kód, aby dynamicky poskytovala informace IntelliSense. V důsledku toho může chování za běhu v některých případech narušovat požadované výsledky. Následující postup ukazuje, jak přepsat výsledky technologie IntelliSense v případě, že chování za běhu vede k nesprávnému IntelliSense.

 Aby tento příklad fungoval, potřebujete následující soubory JavaScriptu v projektu:

- exampleLib. js je soubor projektu, který představuje knihovnu třetí strany.

- exampleLib. IntelliSense. js, což je rozšíření technologie IntelliSense. Tento soubor není nutné zahrnout do projektu, ale musí být ve stejné složce jako exampleLib. js.

- stráveného. js je soubor projektu, který představuje kód aplikace.

##### <a name="to-avoid-run-time-effects-on-intellisense-results"></a>Aby nedocházelo k důsledkům běhu na výsledcích technologie IntelliSense

1. Do exampleLib. js přidejte následující kód.

    ```javascript
    function after(count, func) {
        return function () {
            if (--times < 1) {
                return func.apply(this, arguments);
            }
        };
    };
    ```

     V předchozím kódu zabalená funkce ignoruje počáteční volání na základě hodnoty `count` a nevrátí výsledky.

2. Přidejte následující direktivu Reference jako první řádek v stráveného. js. Zde použitá cesta označuje, že soubory JavaScriptu jsou ve stejné složce.

    ```javascript
    /// <reference path="exampleLib.js" />

    ```

3. V stráveného. js zadejte následující kód. Seznam identifikátorů se zobrazí namísto technologie IntelliSense, protože zabalená funkce nikdy není volána, což znamená, že funkce `throttled` nevrátí žádné výsledky.

     ![Příklad přepsání výsledků technologie IntelliSense](../ide/media/js-intellisense-override.png "js_intellisense_override")

4. Do exampleLib. IntelliSense. js přidejte následující kód. Tím se změní chování při návrhu tak, aby se pro zabalenou funkci zobrazila IntelliSense, jak očekáváte.

    ```javascript
    window.after = function (count, func) {
        // Just return func.
        return func;
    };
    ```

5. V stráveného. js otestujte výsledky zadáním stejného kódu, který jste zadali dříve. Tentokrát technologie IntelliSense poskytuje požadované informace.

     ![Příklad přepsání výsledků technologie IntelliSense](../ide/media/js-intellisense-override-fixed.png "js_intellisense_override_fixed")

## <a name="see-also"></a>Viz také
 [Dokončování příkazů](../ide/statement-completion-for-identifiers.md) [JavaScriptu technologie IntelliSense](../ide/javascript-intellisense.md) pro identifikátory
