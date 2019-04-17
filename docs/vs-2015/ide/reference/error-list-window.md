---
title: Okno Seznam chyb | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ErrorList
helpviewer_keywords:
- Task List
- build errors
- Error List window
- errors [Visual Studio], Error List window
ms.assetid: b7f6d45a-733b-4ad8-bc2f-737a37509e56
caps.latest.revision: 36
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 9dc94abdfb35bc4537f0ba80f96f393157263e63
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59658146"
---
# <a name="error-list-window"></a>Okno Seznam chyb
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

POZNÁMKA:]
>  V seznamu chyb zobrazí informace o určité chybové zprávě. Číslo chyby nebo text řetězce chyby můžete zkopírovat z okna výstup. Chcete-li zobrazit okno výstup, stiskněte Ctrl + Alt + O. Zobrazit [okna výstup](../../ide/reference/output-window.md).  
  
 Můžete vyvíjet aplikace rychleji pomocí **seznam chyb** okna. Například můžete provádět následující úlohy:  
  
- Zobrazte chyby, varování a zprávy vytvořené při psaní kódu.  
  
- Najděte chyby syntaxe zaznamenané technologií IntelliSense.  
  
- Vyhledejte chyby v nasazení, některé statické analýzy chyby a chyby zjištěné při použití zásad šablony organizace.  
  
- Dvakrát klikněte na libovolný záznam chybové zprávy pro otevření souboru, kde dojde k problému a přesunout do umístění chyby.  
  
- Filtrovat položky, které se zobrazí a které sloupce informací se zobrazí pro každou položku.  
  
- Hledejte konkrétní termíny a nastavte obor hledání pouze na aktuální projekt nebo dokument.  
  
  Chcete-li zobrazit **seznam chyb**, klikněte na tlačítko **zobrazení / Seznam chyb**, nebo **CTRL +\\+ E**.  
  
  Můžete použít **chyby**, **upozornění**, a **zprávy** karet zobrazíte informace o různých úrovních.  
  
  Chcete-li seřadit, klikněte na libovolné záhlaví sloupce. Chcete-li znovu řadit podle dalšího sloupce, podržte stisknutou klávesu SHIFT a klikněte na další záhlaví sloupce. Chcete-li vybrat sloupce, které se zobrazí a které jsou skryté, zvolte **zobrazit sloupce** z místní nabídky. Chcete-li změnit pořadí, ve kterém jsou sloupce zobrazeny, přetáhněte libovolné záhlaví sloupce doleva nebo doprava.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které se zobrazí mohou lišit od těch zde popsaných v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, klikněte na tlačítko **nástroje / Import a Export nastavení**. Další informace najdete v tématu [přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="error-list-filters"></a>Filtry seznamů chyb  
 Existují dva typy filtru v dva rozevírací seznamy, jeden na pravé straně panelu nástrojů a druhý na levém panelu nástrojů. Určuje sadu souborech s kódem pomocí rozevíracího seznamu na levé straně panelu nástrojů (**celé řešení**, **otevřené dokumenty**, **aktuální projekt**,  **Aktuální dokument**).  
  
 Můžete omezit rozsah hledání můžete analyzovat a zpracovat skupiny chyb. Například můžete chtít zaměřit na základní chyby, které brání kompilaci projektu. Možnosti vytváření oboru zahrnují:  
  
1. **Otevřít dokumenty**: Zobrazit chyby, varování a zprávy pro otevřené dokumenty.  
  
2. **Aktuální projekt**: Zobrazit chyby, varování a zprávy z aktuálně vybraného dokumentu v projektu **Editor** nebo vybraný projekt v **Průzkumníka řešení**.  
  
   > [!NOTE]
   >  Filtrovaný seznam chyb, upozornění a zpráv se změní, pokud je projekt aktuálně vybraného dokumentu liší od projektu vybraného v **Průzkumníka řešení**.  
  
3. **Aktuální dokument**: Zobrazí chyby, varování a zprávy pro aktuálně vybraného dokumentu v **Editor** nebo **Průzkumníka řešení**.  
  
   Pokud na výsledek hledání je aktuálně použit filtr, zobrazí se název filtru v **seznam chyb** záhlaví okna. **Chyby**, **upozornění**, a **zprávy** tlačítka pak zobrazí počet filtrovaných položek zobrazených společně s celkový počtem položek; například tlačítka zobrazí x z y chyb. Pokud není použit žádný filtr, záhlaví říká pouze "Seznam chyb".  
  
   V seznamu na pravé straně panelu nástrojů Určuje, jestli se zobrazí chyby sestavení (chyby plynoucí z operace sestavení) nebo z technologie IntelliSense (byly zjištěny chyby před spuštěním sestavení), nebo z obou.  
  
## <a name="search"></a>Hledat  
 Použití **Hledat v seznamu chyb** textového pole na pravé straně **seznam chyb** nástrojů k vyhledání konkrétní chyby v seznamu chyb. Můžete hledat v jakémkoli viditelném sloupci v seznamu chyb a výsledky hledání jsou vždy řazeny podle sloupce, který má prioritu řazení namísto podle dotazu nebo použitého filtru. Pokud se rozhodnete **Esc** klávesu je zaměření **seznam chyb**, můžete vymazat hledaný výraz a filtrování výsledků hledání. Můžete také kliknout **X** na pravé straně textového pole k zaškrtnutí políčka zrušte.  
  
## <a name="save"></a>Uložit  
 Můžete zkopírovat seznam chyb a uložte ho do souboru. Vyberte chyby, které chcete kopírovat a klikněte pravým tlačítkem na výběr a pak v místní nabídce vyberte **kopírování**. Chyby lze potom vložit do souboru. Pokud vložíte chyby do Excelové tabulky, pole se zobrazí jako různé sloupce.  
  
## <a name="ui-element-list"></a>Seznam prvků uživatelského rozhraní  
 Severity  
 Zobrazuje různé typy **seznam chyb** položku (**chyba**, **zpráva**, **upozornění**, **upozornění (aktivní)**, **Upozornění (neaktivní)**.  
  
 Kód  
 Zobrazí kód chyby.  
  
 Popis  
 Zobrazí text záznamu.  
  
 Project  
 Název aktuálního projektu.  
  
 Soubor  
 Zobrazuje název souboru.  
  
 Řádek  
 Zobrazí řádek, kde k problému dochází.
