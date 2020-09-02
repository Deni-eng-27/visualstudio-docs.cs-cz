---
title: Přehled Diagnostika grafiky | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: ddd429d9-ac70-4ac4-9e69-299c6ea2df09
caps.latest.revision: 32
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 2dc0d0bf4efd8c30d874a24e94d3933d2eef713a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "68186548"
---
# <a name="overview-of-visual-studio-graphics-diagnostics"></a>Přehled diagnostiky grafiky sady Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio *Diagnostika grafiky* je sada nástrojů pro zaznamenávání a analýzu problémů s výkonem a výkonem v aplikacích Direct3D. Diagnostika grafiky můžete použít pro aplikace, které běží místně na počítači s Windows, v emulátoru zařízení s Windows nebo na vzdáleném počítači nebo zařízení.

## <a name="using-graphics-diagnostics-to-debug-rendering-problems"></a>Použití Diagnostiky grafiky k ladění problémů s vykreslováním
 Ladění problémů s vykreslováním v aplikaci s bohatou grafikou není tak přímočaré jako spuštění ladicího programu a krokování kódu. V každém snímku jsou produkovány stovky tisíc jedinečných pixelů podle komplexní sady stavu, dat, parametrů a kódu. Z těchto pixelů může problém, který chcete diagnostikovat, vykazovat pouze několik málo pixelů. A aby věci byly ještě složitější, kód, který generuje každý pixel, je spouštěn na specializovaném hardwaru, který paralelně zpracovává stovky pixelů. Tradiční nástroje a techniky ladění, které je obtížné využít i v kódu s malým počtem vláken, jsou v případě velkého množství dat neúčinné.

 Nástroje Diagnostika grafiky v nástroji [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] jsou navržené tak, aby vám pomohly najít problémy s vykreslováním, počínaje vizuálními artefakty, které indikují problém, a pak se k zdroji problému zaměří jenom na relevantní kód shaderu, fáze zřetězení, volání remíz, prostředky a stav zařízení – ve vlastním zdrojovém kódu aplikace.

## <a name="directx-version-compatibility"></a>Kompatibilita verzí DirectX
 Diagnostika grafiky podporuje aplikace, které používají Direct3D 12, Direct3D 11 a Direct3D 10, a poskytuje omezené podpory pro aplikace, které používají Direct2D. Nepodporuje aplikace, které používají starší verze rozhraní Direct3D, DirectDraw nebo jiné grafické rozhraní API.

### <a name="windows-10-and-direct3d-12"></a>Windows 10 a Direct3D 12
 Windows 10 zavádí další verzi rozhraní Direct3D, *Direct3D 12*, která je podstatně odlišná od Direct3D 10 a Direct3D 11. Tyto rozdíly přinášejí rozhraní DirectX zpátky k modernímu grafickému hardwaru a zajišťují jeho úplný potenciál, ale také přináší velké změny rozhraní API a zajišťují větší zodpovědnost na programátorovi za účelem správy životností a kolizí prostředků. Skvělé nástroje pro ladění jsou klíčové k tomu, aby programátorům grafiky usnadnili tento přechod, takže Diagnostika grafiky v aplikaci Visual Studio 2015 podporuje Direct3D12 přímo od začátku. Navzdory rozdílům Diagnostika grafiky s Direct3D 12 udržuje paritu funkcí s Diagnostika grafiky s Direct3D 11,2 a aktuální výjimkou funkce analýzy snímků. Brzy se doplní podpora analýzy snímků v Direct3D 12, za kterou následují nové diagnostické nástroje, které vám pomohou vyřešit nové druhy chyb, se kterými se můžete setkat v Direct3D 12.

 Windows 10 také udržuje podporu pro předchozí verze rozhraní Direct3D a her a aplikací, které je využívají. Diagnostika grafiky v aplikaci Visual Studio 2015 nadále podporuje Direct3D 10 a Direct3D 11 ve Windows 10 a také Windows 8.1.

### <a name="windows-81-and-direct3d-112"></a>Windows 8.1 a Direct3D 11,2
 V [!INCLUDE[win81](../includes/win81-md.md)] rozhraní DirectX 11,2 zavádí nové funkce, které zahrnují podporu pro zachycení informací grafiky prostřednictvím jejího modulu runtime. [!INCLUDE[win81](../includes/win81-md.md)] používá nový záznam založený na běhu – známý jako *robustní zachytávání*– výhradně pro všechny verze rozhraní DirectX, které [!INCLUDE[win81](../includes/win81-md.md)] podporuje. Robustní zachycení podporuje také nové funkce Direct3D 11,2.

### <a name="limited-direct2d-support"></a>Omezená podpora rozhraní Direct2D
 Protože Direct2D je rozhraní API uživatelského režimu, které navazuje na Direct3D, můžete Diagnostiku grafiky použít k ladění problémů s vykreslováním v aplikacích, které využívají Direct2D. Protože jsou však zaznamenány pouze základní události rozhraní Direct3D namísto událostí rozhraní Direct2D na vyšší úrovni, události Direct2D se na seznamu událostí grafiky nezobrazí. A protože vztah mezi událostmi rozhraní Direct2D a výslednými událostmi rozhraní Direct3D není vždy jasný, použití Diagnostiky grafiky k ladění problémů s vykreslováním v aplikacích, které používají Direct2D, není vždy přímočaré. Nadále můžete Diagnostiku grafiky použít k získání informací o problémech s vykreslováním na nízké úrovni v aplikacích, které používají rozhraní Direct2D.

## <a name="graphics-diagnostics-features-in-visual-studio"></a>Funkce Diagnostika grafiky v aplikaci Visual Studio
 Diagnostika grafiky má vyhrazené rozhraní – okno analyzátor grafiky – pro diagnostiku problémů s vykreslováním, ale také přidá některé nástroje do rozhraní sady Visual Studio.

### <a name="the-graphics-toolbar-visual-studio"></a>Panel nástrojů grafika (Visual Studio)
 Panel nástrojů grafika poskytuje rychlý přístup k příkazům Diagnostika grafiky.

 Tlačítko **Spustit diagnostiku** spustí aplikaci v části Diagnostika grafiky. Když je aplikace spuštěná v Diagnostika grafiky, zachytávání je povolené tlačítko **zachytit další vykreslený snímek** .

### <a name="diagnostics-capture-interface"></a>Rozhraní pro zachycení diagnostiky
 Když aplikaci spouštíte v rámci Diagnostika grafiky, Visual Studio zobrazí rozhraní diagnostiky relace, které můžete použít k zachycení rámců a také zobrazení aktuálního procesoru a zatížení GPU. Zobrazí se zatížení CPU a GPU, které vám usnadní identifikaci snímků, které je vhodné zachytit v důsledku jejich vlastností výkonu, nikoli při vykreslování chyb.

 Nejedná se o jediný způsob, jak zachytit snímky, i když. Můžete také zachytit rámce pomocí programového digitalizačního rozhraní nebo pomocí programu pro zachycení příkazového řádku dxcap.exe.

 Další informace najdete v tématu [informace o zachytávání grafiky](../debugger/capturing-graphics-information.md) .

### <a name="gpu-usage"></a>Využití GPU
 Diagnostika grafiky může také Profilovat výkon aplikace Direct3D. Vzhledem k tomu, že se data profilace budou zkosit pomocí zaznamenávání podrobností o grafických událostech, je to oddělené od zachytávání snímků, které se mají prozkoumat pomocí analyzátoru grafiky.

 Další informace najdete v tématu [použití GPU](../debugger/gpu-usage.md) .

### <a name="directx-control-panel"></a>Ovládací panel rozhraní DirectX
 Ovládací panel rozhraní DirectX je součástí rozhraní DirectX, které můžete použít ke změně způsobu, jakým se rozhraní DirectX chová – například povolit verzi ladění runtime komponent rozhraní DirectX a výběr druhu zpráv ladění, které jsou zaznamenány, a zakázat použití určitých funkcí hardwaru grafiky k emulaci hardwaru s méně funkcemi. Tato úroveň kontroly nad rozhraním DirectX vám může pomoct ladit a testovat vaši aplikaci DirectX. Ovládací panel rozhraní DirectX zobrazíte ze sady Visual Studio.

##### <a name="to-open-the-directx-control-panel"></a>Otevření ovládacího panelu rozhraní DirectX

- Na panelu nabídek vyberte položku **ladění**, **Grafika**, **ovládací panel rozhraní DirectX**.

## <a name="graphics-analyzer"></a>Analyzátor grafiky
 Analyzátor grafiky sady Visual Studio je vyhrazené rozhraní pro zkoumání problémů s vykreslením a výkonem v rámcích, které jste už zachytili. V analyzátoru grafiky najdete několik nástrojů, které vám pomůžou prozkoumat a pochopit chování při vykreslování vaší aplikace. Každý nástroj zveřejňuje různé druhy informací o kontrolovaném snímku a nástroje jsou navrženy tak, aby se v souladu s intuitivním zúžením na zdroj problému s vykreslováním využívaly, od jeho vzhledu v framebuffer.

 Na tomto obrázku je znázorněno typické rozložení nástrojů v analyzátoru grafiky.

 ![Všechna okna ladicího programu grafiky](../debugger/media/graphicsdebuggerwindows.png "GraphicsDebuggerWindows")

### <a name="the-graphics-toolbar-graphics-analyzer"></a>Panel nástrojů grafika (analyzátor grafiky)
 Panel nástrojů grafika poskytuje rychlý přístup k okenm nástrojů analyzátoru grafiky.

 ![Panel nástrojů grafika v režimu diagnostiky grafiky](../debugger/media/vsg-toolbar.png "vsg_toolbar")

### <a name="graphics-log-document"></a>Dokument protokolu grafiky
 V analyzátoru grafiky je dokument s grafickým protokolem nejvýraznějším oknem nástrojů. Toto okno reprezentuje všechny rámce, které jste si poznamenali, spuštěním vaší aplikace v části Diagnostika grafiky. Z tohoto místa můžete vybrat jiný rámec pro kontrolu nebo výběr konkrétního pixelu, který chcete prošetřit nástrojem Historie pixelů. Obrázek framebuffer zobrazený v tomto dokumentu se změní tak, aby odrážel aktuálně vybranou událost, abyste viděli, jak je framebuffer ovlivněn v čase.

 [Dokument protokolu grafiky](../debugger/graphics-log-document.md) je zároveň vstupním bodem nástroje pro analýzu snímků, který vám pomůže pochopit výkon rámce změnou způsobu, jakým jsou nakonfigurovány určité aspekty vykreslování, a poskytuje výsledky srovnávacích testů pro porovnání s původní.

### <a name="event-list"></a>Seznam událostí
 Grafické události označují jednotlivá volání rozhraní Direct3D API a uživatelsky definovanou událost.

 [Seznam událostí](../debugger/graphics-event-list.md) zobrazuje všechny události grafiky, které byly zaznamenány během prozkoumávání rámce. Abychom vám pomohli najít, co je důležité, lze seznam událostí zobrazit hierarchicky – s posledními změnami stavu pod následným voláním vykreslování – nebo jako časová osa. Události jsou navíc barevně kódované v závislosti na frontě, do které patří, a můžete seznam filtrovat tak, aby obsahoval jenom události, které vás zajímají.

 Když v seznamu vyberete událost, zbývající nástroje pro analýzu grafiky odrážejí stav rámce v době této události. Tímto způsobem můžete vidět účinek libovolné události v GPU. Například můžete zobrazit okamžitý účinek jakéhokoli volání remíz na framebuffer, i když je překryto následnými voláními vykreslování. Některé události mají také hypertextové odkazy, které můžete použít, chcete-li zobrazit další podrobnosti o jeho parametrech nebo souvisejících objektech prostředků.

### <a name="pipeline-stages"></a>Fáze zřetězení
 Každé volání vykreslování ve vaší aplikaci projde kanálem grafiky poskytovaným rozhraním Direct3D. V každé fázi kanálu se výstup z předchozí fáze transformuje pomocí malého programu, který se nazývá shader, a pak se předává do další fáze, dokud není nakonec vykreslen na obrazovku. K mnoha chybám vykreslování dochází na hranici mezi fázemi kanálu, když je výstupní formát jiný než v další fázi, nebo když kterákoli z fází jednoduše vytváří nesprávné výsledky. Za normálních okolností dostanete jenom konečné výsledky, jako byste to viděli na obrazovce, a nemůžete snadno zjistit, kde v kanálu došlo k chybě.

 Okno [fáze zřetězení](../debugger/graphics-pipeline-stages.md) vizualizuje výsledek každé fáze nezávisle, takže můžete snadněji určit, ve které fázi se problém s vykreslováním zobrazuje poprvé. Jakmile určíte, kterou fázi máte, můžete spustit ladění jeho shaderu přímo z okna fáze zřetězení.

### <a name="graphics-state"></a>Stav grafiky
 Operace vykreslování závisí na hodně stavu, který je obvykle rozložen mezi více objektů. Mnoho druhů problémů s vykreslováním je způsobeno chybně nakonfigurovaným stavem.

 Okno [stav](../debugger/graphics-state.md) shromažďuje informace o stavu jednotlivých volání remíz na jednom místě, aby bylo snazší je najít a také zvýrazňuje změny stavu, ke kterým došlo od předchozího volání metody Draw.

### <a name="pixel-history"></a>Historie pixelů
 Na složitých snímcích není běžné, že pixel bude v jednom snímku několikrát vystínovat. V některých případech je dřívější barva právě přepsána, ale v jiných časech jsou barvy kombinovány, aby byly dosaženy účinky, jako je transparentnost. Pokud výsledek kombinace těchto dohromady nemá správný vzhled, nemůžete snadno zjistit, jestli je jedna z barev nesprávná, nebo pokud dojde k potížím s způsobem, kterým byly kombinovány. Jinak může dojít k chybějícímu objektu, protože jeho příspěvek k obrazovému bodu byl z nějakého důvodu zamítnut.

 Okno [Historie pixelů](../debugger/graphics-pixel-history.md) vizualizuje kompletní historii shaderu každého pixelu v rámci, včetně odmítnutých příspěvků. U příspěvků, které nebyly odmítnuty, se zobrazí nezpracované výsledky shaderu a způsob, jakým byly všechny nové barvy zkombinovány s předchozími. S těmito informacemi je mnohem snazší najít zdroj chyb v pixelech, které se míchají do výsledků shaderu, nebo pokud chybí vykreslený objekt, protože jeho podíl na pixelu byl nesprávně odmítnut.

### <a name="event-call-stack"></a>Zásobník volání událostí
 Kód shaderu není jediným zdrojem problémů s vykreslováním v aplikaci Direct3D, někdy ale zdrojový kód vaší aplikace předává špatný parametr nebo nekonfiguruje rozhraní Direct3D poměrně vpravo. Jeden druh chyby, kterou dříve provedla Historie pixelů, vám může pomáhat při hledání, když dojde k chybě vykresleného objektu, protože všechny jeho pixely byly odmítnuty. Tento druh chyby se obvykle stává, když jste nesprávně nakonfigurovali nastavení, jako je například ta, která řídí, jak se provádí test hloubky, a obvykle můžete najít chybu někde v zásobníku volání chybějícího volání vykreslování objektu.

 Okno [zásobník volání události](../debugger/graphics-event-call-stack.md) zobrazí úplný zásobník volání každé události grafiky v seznamu událostí a dokonce vám umožní přejít na zdrojový kód vaší aplikace, pokud jsou k dispozici informace o ladění. Toto je výkonný nástroj pro následující chybu, ze které se zobrazí chyba, na které se nachází ve zdrojovém kódu vaší aplikace, na GPU.

### <a name="object-table"></a>Tabulka objektů
 Každý snímek vykreslící aplikaci je pravděpodobně zajištěn stovkami nebo dokonce tisíci objektů prostředků. Tyto můžou zahrnovat vyrovnávací paměti a cíle vykreslování, textury, vyrovnávací paměti vrcholů, vyrovnávací paměti pro index, obecné vyrovnávací paměti – téměř všechny členy rozhraní Direct3D jsou objekty.

 V [tabulce objekt](../debugger/graphics-object-table.md) se zobrazí všechny objekty, které existují v době události Graphics vybrané v seznamu událostí. Vzhledem k tomu, že většina objektů v typických aplikacích je textur, je seznam událostí optimalizovaný tak, aby zobrazoval podrobnosti týkající se obrázků na první pohled. Sloupec typ obsahuje informace o tom, jaký typ objektu je v každém řádku, a sloupec Format dále zobrazuje dílčí typ nebo verzi objektu. Zobrazí se také další podrobnosti. Některé objekty mají také hypertextové odkazy, které můžete použít, chcete-li zobrazit objekt se specializovaným prohlížečem, jako jsou textury (můžete zobrazit texturu jako obrázek), nebo vyrovnávací paměti (můžete si vybrat, jak prohlížeč vyrovnávací paměti analyzuje a zobrazuje nezpracované bajty vyrovnávací paměti definováním formátu vyrovnávací paměti).

### <a name="frame-analysis"></a>Analýza snímků
 Grafiku vaší aplikace nemusíte jenom opravovat – musí být také rychlá. Dokonce i na méně výkonném zařízení, jako jsou přenosné počítače s integrovanými grafikami nebo mobilními telefony. A pořád musí vypadat dobře.

 Nástroj [Analýza snímků](../debugger/graphics-frame-analysis.md) zkoumá možné optimalizace výkonu tím, že automaticky změní způsob, jakým aplikace využívá Direct3D, a poskytuje srovnávací výsledky pro porovnání. Například analýza snímků může povolit mapování MIP na každou texturu, což by mohlo odhalovat textury, které by mohly mít výhodu mapování MIP, ale momentálně je nepovoluje. V případě hardwaru, který je podporuje, analyzuje rámec také informace shromažďované z čítačů výkonu GPU. Tato úroveň informací může identifikovat problémy s výkonem na úrovni hardwaru, například vysoké množství blokovaných nebo neúspěšných přístupů do mezipaměti.

 Analýza snímků ale nestačí jenom o tom, jak rychle začít – díky tomu získáte maximální výkon, který vám umožní dostat se k nejmenšímu množství vizuální kvality. V některých případech se může stát, že při zobrazení na malé obrazovce telefonu nedosahuje stejný dopad na velký displej, kde by jednodušší efekt vypadal stejně jako dobrý, aniž by se vyčerpala baterie. Automatické změny a srovnávací testy, které poskytuje funkce Analýza grafiky, vám pomůžou najít rovnováhu, která je pro vaši aplikaci pro celou řadu zařízení nejvhodnější.

## <a name="see-also"></a>Viz také
 [Nástroj pro zachycení příkazového řádku](../debugger/command-line-capture-tool.md) [HLSL ladicí program](../debugger/hlsl-shader-debugger.md)
