---
title: Mapování metod v zásobníku volání při ladění
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.progression.debugwithcodemaps
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- call stacks, code maps
- Call Stack window, mapping calls
- debugging [Visual Studio], diagramming the call stack
- call stacks, mapping
- Call Stack window, visualizing
- debugging code visually
- debugging [Visual Studio], mapping the call stack
- call stacks, visualizing
- debugging, code maps
- Call Stack window, tracing calls visually
- Call Stack window, show on code map
- debugging [Visual Studio], tracing the call stack visually
- debugging [Visual Studio], visualizing the call stack
ms.assetid: d6a72e5e-f88d-46fc-94a3-1789d34805ef
caps.latest.revision: 43
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 2e8376884f72aeca2f3bf56f0d7bbc1636379a18
ms.sourcegitcommit: c150d0be93b6f7ccbe9625b41a437541502560f5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2020
ms.locfileid: "75847310"
---
# <a name="map-methods-on-the-call-stack-while-debugging-in-visual-studio"></a>Mapování metod v zásobníku volání při ladění v sadě Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vytvořte mapu kódu pro vizuální sledování zásobníku volání během ladění. Můžete si dělat poznámky na mapě ke sledování kódu činnosti tak, abyste se mohli zaměřit na hledání chyb.

 ![Ladění pomocí zásobníků volání v mapách kódu](../debugger/media/debuggermap-overview.png "DebuggerMap_Overview")

 Budete potřebovat:

- [Visual Studio Enterprise](https://www.visualstudio.com/downloads/download-visual-studio-vs)

- Kód, který lze ladit, jako je Visual C# .NET, Visual Basic .NET, C++, JavaScript nebo X ++

  Přejděte na téma: [Video: vizuální ladění díky integraci ladicího programu mapy kódu (kanál 9)](https://channel9.msdn.com/Series/Visual-Studio-2012-Premium-and-Ultimate-Overview/Visual-Studio-Ultimate-2012Debug-visually-with-Code-Map-debugger-integration) • [mapování zásobníku volání](#MapStack) • [Tvorba poznámek o kódu](#MakeNotes) • [aktualizace mapy s následujícím zásobníkem volání](#UpdateMap) • [přidání souvisejícího kódu do mapy](#AddRelatedCode) • [najít chyby pomocí mapy](#FindBugs) • [funkce Q & A](#QA)

  Podrobnosti příkazů a akcí, které můžete použít při práci s mapami kódu najdete v tématu [Procházet a uspořádání map kódu](../modeling/browse-and-rearrange-code-maps.md).

## <a name="MapStack"></a> Mapování zásobníku volání

1. Spusťte ladění. (Klávesnice: **F5**)

2. Až se vaše aplikace přejde do režimu přerušení nebo přejdete na funkci, zvolte **mapy kódu**. (Klávesnice: **Ctrl** + **Shift** +  **`** )

     ![Zvolit mapu kódu pro začátek mapování zásobníku volání](../debugger/media/debuggermap-choosecodemap.png "DebuggerMap_ChooseCodeMap")

     Aktuální aktuální zásobník volání se zobrazí oranžově na mapě nového kódu:

     ![Zobrazit zásobník volání na mapě kódu](../debugger/media/debuggermap-seeundocallstack.png "DebuggerMap_SeeUndoCallStack")

     Na mapě se automaticky aktualizovat, když budete pokračovat v ladění. Zobrazit [aktualizace mapy s následujícím zásobníkem volání](#UpdateMap).

## <a name="MakeNotes"></a> Tvorba poznámek o kódu
 Přidejte komentáře pro sledování, co se děje v kódu. Chcete-li přidat nový řádek v komentáři, stiskněte **Shift + Return**.

 ![Přidat komentář k zásobníku volání na mapě kódu](../debugger/media/debuggermap-addcomment.png "DebuggerMap_AddComment")

## <a name="UpdateMap"></a> Aktualizace mapy s následujícím zásobníkem volání.
 Spuštění vaší aplikace na další zarážku nebo krok do funkce. Mapování přidá nový zásobník volání.

 ![Aktualizovat mapu kódu pomocí dalšího zásobníku volání](../debugger/media/debuggermap-addclearcallstack.png "DebuggerMap_AddClearCallStack")

## <a name="AddRelatedCode"></a> Přidání souvisejícího kódu do mapy
 Nyní máte k dispozici mapu – co dál? Při práci s prostředími Visual C#, .NET nebo Visual Basic .NET přidejte položky, například pole, vlastnosti a jiné metody, chcete-li sledovat, co se děje v kódu.

 Poklepejte na metodu a zobrazte její definici kódu tak, nebo použijte místní nabídku pro metodu. (Klávesnice: Vyberte metodu na mapě a stiskněte klávesu **F12**)

 ![Přejít na definici kódu pro metodu na mapě kódu](../debugger/media/debuggermap-gotocodedefinition.png "DebuggerMap_GoToCodeDefinition")

 Přidejte položky, které chcete sledovat na mapě.

 ![Zobrazit pole v metodě v mapě kódu zásobníku volání](../debugger/media/debuggermap-showfields.png "DebuggerMap_ShowFields")

> [!NOTE]
> Ve výchozím nastavení přidávání položek do mapy také přidá nadřazené uzly skupiny, například třídy, oboru názvů a sestavení. I to je užitečné, abyste mohli mapy jednoduché vypnutím této funkce pomocí **zahrnout nadřazené položky** tlačítko na panelu nástrojů mapy nebo stisknutím klávesy **CTRL** při přidávání položek.

 ![Pole související s metodou v mapě kódu zásobníku volání](../debugger/media/debuggermap-showedfields.png "DebuggerMap_ShowedFields")

 Zde můžete snadno zobrazit metody, které používají stejná pole. Poslední přidané položky se zobrazí zeleně.

 Pokračujte v sestavování mapy, pokud chcete zobrazit další kód.

 ![Viz metody, které používají pole: mapa kódu zásobníku volání](../debugger/media/debuggermap-findallreferences.png "DebuggerMap_FindAllReferences")

 ![Metody, které používají pole v mapě kódu zásobníku volání](../debugger/media/debuggermap-foundallreferences.png "DebuggerMap_FoundAllReferences")

## <a name="FindBugs"></a> Najít chyby pomocí mapy
 Vizualizace kódu můžete nalézt chyby rychleji. Předpokládejme například, že hledáte chyby v aplikaci pro kreslení. Když nakreslíte čáru a pokusíte se vrátit akci zpět, nic se nestane, dokud nenakreslíte další čáru.

 Proto nastavte zarážky v `clear`, `undo`, a `Repaint` metody, spustit ladění a vytvořit mapu podobné následujícímu:

 ![Přidat další zásobník volání do mapy kódu](../debugger/media/debuggermap-addpaintobjectcallstack.png "DebuggerMap_AddPaintObjectCallStack")

 Všimněte si, že všechna gesta uživatelů na mapě volají `Repaint`, s výjimkou `undo`. To může vysvětlit, proč `undo` nefunguje okamžitě.

 Po opravě chyby a pokračování ve spouštění programu, mapování přidá nové volání z `undo` k `Repaint`:

 ![Přidat nové volání metody do zásobníku volání na mapě kódu](../debugger/media/debuggermap-addnewcallforrepaint.png "DebuggerMap_AddNewCallForRepaint")

## <a name="QA"></a> Q & A

- **Ne všechna volání se zobrazí na mapě. Proč?**

   Ve výchozím nastavení zobrazí se pouze vlastní kód na mapě. Chcete-li zobrazit externí kód, zapněte ho v **zásobník volání** okno:

   ![Zobrazit externí kód pomocí okna zásobník volání](../debugger/media/debuggermap-callstackmenu.png "DebuggerMap_CallStackMenu")

   nebo se vypnout **povolit volbu pouze vlastní kód** v možnostech ladění aplikace Visual Studio:

   ![Zobrazit externí kód pomocí dialogu Možnosti](../debugger/media/debuggermap-debugoptions.png "DebuggerMap_DebugOptions")

- **Změna mapování kód ovlivní?**

   Změna mapování kód nijak neovlivní. Nebojte se přejmenovat, přesunout nebo odebrat cokoli na mapě.

- **Co tato zpráva znamená: "diagram může být založen na starší verzi kódu"?**

   Po poslední aktualizaci mapy mohl být kód změněn. Například volání do mapy nemusí již v kódu existovat. Zavřete zprávu a potom zkuste znovu sestavit řešení před opětovnou aktualizací mapy.

- **Jak můžu řídit rozložení mapy?**

   Otevřít **rozložení** nabídky na panelu nástrojů mapy:

  - Změňte výchozí rozložení.

  - Chcete-li zastavit automatické uspořádání mapy, vypněte **při ladění automaticky rozmístit**.

  - Chcete-li změnit uspořádání mapy co při přidávání položek, vypněte **Inkrementální rozložení**.

- **Mohu sdílet mapu s ostatními?**

   Můžete exportovat mapu, odeslat ji ostatním uživatelům, pokud máte aplikaci Microsoft Outlook, nebo ji uložit do vašeho řešení, abyste ji mohli vrátit se změnami do řízení verzí Team Foundation.

   ![Sdílení mapy kódu zásobníku volání s ostatními](../debugger/media/debuggermap-sharewithothers.png "DebuggerMap_ShareWithOthers")

- **Jak mohu zabránit mapě v automaticky přidání nových zásobníků volání?**

   Zvolte ![tlačítko &#45; zásobníku volání zobrazit na mapě kódu automaticky](../debugger/media/debuggermap-automaticupdateicon.gif "DebuggerMap_AutomaticUpdateIcon") na panelu nástrojů Mapa. Chcete-li ručně přidat aktuální zásobník volání k mapě, stiskněte **Ctrl** + **Shift** +  **`** .

   Mapa bude pokračovat ve zvýraznění existujících zásobníků volání na mapě během ladění.

- **Co ikony položky a šipky znamenají?**

   Pokud chcete získat další informace o položce, přesuňte ukazatel myši nad ním a podívejte se na popis položky. Můžete také prohlédnout **legendy** se dozvíte, co znamenají jednotlivé ikony.

   ![Jak ikony na mapě kódu zásobníku volání znamenají?](../debugger/media/debuggermap-showlegend.png "DebuggerMap_ShowLegend")

  Přejděte na téma: [mapování zásobníku volání](#MapStack) • [Tvorba poznámek o kódu](#MakeNotes) • [aktualizace mapy s následujícím zásobníkem volání](#UpdateMap) • [přidání souvisejícího kódu do mapy](#AddRelatedCode) • [ Najít chyby pomocí mapy](#FindBugs)

## <a name="see-also"></a>Viz také
 [Mapování závislostí napříč vaším řešením](../modeling/map-dependencies-across-your-solutions.md) [mapy kódu použít k ladění aplikací](../modeling/use-code-maps-to-debug-your-applications.md) [najít potenciální problémy pomocí kódu mapování analyzátory](../modeling/find-potential-problems-using-code-map-analyzers.md) [Procházet a uspořádání map kódu](../modeling/browse-and-rearrange-code-maps.md)
