---
title: VSPerfReport | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- command-line tools, VSPerfReporttool
- performance tools, VSPerfReport tool
- profiling tools,VSPerfReport
- VSPerfReport tool
- command line, tools
- instrumentation, VSPerfReporttool
ms.assetid: dbfd8d91-4430-4b82-81b9-97ac61412a6c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 56dbbded2f141ab2e4be02c81f4e40fd6f523809
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55020799"
---
# <a name="vsperfreport"></a>VSPerfReport
Vsperfreport – nástroj příkazového řádku se používá k vytvoření sestavy, které používají [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojů pro profilaci sady souborů dat profilování. Výchozí formát sestavy. *sdíleného svazku clusteru* souboru.  
  
 VSPerfReport používá následující syntaxi:  
  
```cmd  
VSPerfReport [/U] vspfilename [/options]  
```  
  
 Všimněte si, že `filename` musí být platná. *Vsp* nebo. *vsps* souboru.  
  
 Vsperfreport – nástroj příkazového řádku se také používá k porovnání. *vsp* nebo. *vsps* soubory. Aby se vygenerovala sestava rozdíl ("diff"), použijte následující syntaxi:  
  
```cmd  
VSPerfReport [/U] /diff vspfilename1 vspfilename2 [/options]  
```  
  
 `vspfilename1 and vspfilename2` musí být platný. *vsp* nebo. *vsps* soubory.  
  
## <a name="symbol-files"></a>Soubory symbolů  
 Chcete-li zobrazit informace o symbolech, jako jsou názvy funkcí a čísla řádků, VSPerfReport vyžaduje přístup k symbolu (. Soubory symbolů soubory PDB) PROFILOVANÉHO komponent a Windows. Další informace najdete v tématu [jak: Zadejte umístění souborů se symboly z příkazového řádku](../profiling/how-to-specify-symbol-file-locations-from-the-command-line.md).  
  
## <a name="general-report-options"></a>Možnosti Obecné sestavy  
 Následující tabulka popisuje obecnou zprávu formátování možnosti a možnosti, které vyberte data, která mají být uvedeny.  
  
|Možnosti|Popis|  
|-------------|-----------------|  
|**U**|Výstup sestavy a přesměrovaný výstup konzoly je zapsán jako Unicode. První možnost je povinná.|  
|**Shrnutí:**[*typy*]|Vytvoří jeden nebo více typů sestav.<br /><br /> -   `All` -jsou generovány všechny typy sestav.<br />-   `CallerCallee` -nadřazené a podřízené vztahy mezi funkcemi.<br />-   `Function` -volané funkce.<br />-   `CallTree` -hierarchii volané funkce.<br />-   `Counter` -všechny značky společně s Windows performance hodnoty čítačů.<br />-   `Ip` -pokyny profilována.<br />-   `Life` -dobu životnosti přidělených objektů (k dispozici, když jsou shromážděná data o přidělování.)<br />-   `Line` data profilu řádku zdrojového kódu.<br />-   `Header` -Sestava obsahuje informace o souboru záhlaví.<br />-   `Mark` všechny značky.<br />-   `Module` -Profilované moduly.<br />-   `Process` -Profilovat procesy.<br />-   `Thread` -vlákna profilována.<br />-   `Type` -přidělené typy.<br />-   `Contention` -Sporty prostředků.<br />-   `RuleWarnings` -problémy pravidla výkonu<br />-   `ETW` -všechny události trasování událostí pro Windows (ETW) shromážděné při spuštění profilace. Datový soubor ETL musí být v původním umístění nebo do adresáře, který obsahuje soubor .vsp nebo .vsps.|  
|**Xml**|Výstup sestavy ve formátu XML.|  
|**CallTrace**|Vytvoří seznam vstupu funkce a ukončí, událostí trasování událostí pro Windows a značky.|  
|**ClearPackedSymbols**|Odebere dříve vložený symboly z datového souboru profilování. Tento příkaz spustit před spuštěním PackSymbols a druhý čas.|  
|**SymbolPath:** `path`|Určuje cesty pro hledání nebo serverů symbolů, které obsahují symboly pro datového souboru profilování.|  
|**DebugSymPath**|Seznam umístění, která jsou prohledány na symboly a určuje, zda jsou dostupné. Tato možnost je užitečná při řešení problémů rozlišení symbolů.|  
|**PackSymbols**|Ukládání symbolů do souboru dat profilování (.vsp) proto symbolu (. *soubor PDB*) soubory nejsou vyžadovány pro analýzu.|  
|**Výstup:** *cesta*&#124;*název souboru*|Určuje alternativní umístění pro soubory generované sestavě. Ve výchozím nastavení jsou sestavy vytvoří v aktuálním adresáři.|  
|**SummaryFile**|Analyzovat a uložit analyzované informace v souboru souhrnu .vsps.|  
|**PrintMarks**|Zobrazte názvy a časová razítka pro všechny značky v souboru zadané sestavy.|  
|**?**|Zobrazí informace o použití.|  
|**NoLogo**|Informace o verzi skryje, když je sestava spuštěna.|  
|**UserRulesDirectory**|Určuje adresář obsahující uživatelsky definovaným výkonem pravidla [ještě nebyla implementována].|  
  
## <a name="filter-options"></a>Možnosti filtrování  
 Následující tabulka popisuje možnosti filtrovat dostupná data.  
  
|Možnosti|Popis|  
|-------------|-----------------|  
|**JustMyCode**[**:**[`caller`][,`callee`]]|Zobrazit pouze uživatele volání funkcí aplikace; Skryjte systémových volání.<br /><br /> -Žádné parametry - skrýt všechny systémové funkce.<br />-   `caller` -Zobrazit jednu úroveň funkce systému, které volají funkce aplikace.<br />-   `callee` -Zobrazit jednu úroveň funkce systému, které jsou volány pomocí funkcí aplikace uživatele.|  
|**StartTime:**[*value*]|Zobrazit pouze data shromážděná za hodnotou (v milisekundách).|  
|**EndTime:**[*hodnotu*]|Zobrazit pouze data shromážděná před hodnotou (v milisekundách).|  
|**FilterFile:** `VSPFFile`|Určuje umístění souboru filtru, která byla vygenerována z okna sestavy výkonu Visual Studio.|  
|**MsFilter:**[*časzahájeni, trvání*]|Zobrazit pouze data od `starttime` až do délky `duration` (v milisekundách).|  
|**Proces:**[*pid*]|Zobrazit pouze data ze zadaného procesu.|  
|**Vlákna:**[*idvlákna*]|Zobrazit pouze data ze zadaného vlákna.|  
|**Vlákna:**[*idvlákna, idprocesu*]|Zobrazit pouze data ze zadaného vlákna přidruženého se zadaným procesem.|  
  
## <a name="difference-report-options"></a>Možnosti sestavy rozdíl  
 Následující tabulka popisuje možnosti pro porovnávání souborů sestav.  
  
|Možnosti|Popis|  
|-------------|-----------------|  
|**Diff**  `vspfile1 vspfile2`|Porovnání dvou souborů sestav (. *Vsp* nebo. *vsps*) soubory. Možnosti souhrnu budou ignorovány pomocí možnosti rozdílů.|  
|**Diff:**[*hodnotu*]|Nižší než tato prahová hodnota bude ignorována rozdíl mezi dvěma hodnotami. Také se nezobrazí nová data s hodnotami pod tuto mezní hodnotu.|  
|**DiffTable:**[*tablename*]|Použijte tuto konkrétní tabulku pro porovnání souborů. Výchozí hodnota je tabulka funkcí.|  
|**DiffColumn:**[*názevsloupce*]|Pomocí tohoto konkrétního sloupce porovnání hodnot. Výchozí hodnota je sloupec procent výhradních vzorků.|  
|**QueryDiffTables**|Vypsat platné tabulky a sloupce příslušné dva soubory sestav, které jsou k dispozici.|  
  
## <a name="see-also"></a>Viz také:  
 [Zobrazení sestav výkonu](../profiling/performance-report-views.md)