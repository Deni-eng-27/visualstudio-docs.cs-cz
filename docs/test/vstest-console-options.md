---
title: VSTest.Console.exe – možnosti příkazového řádku
ms.date: 07/12/2018
ms.topic: reference
helpviewer_keywords:
- vstest.console.exe
- command-line tests
ms.author: gewarren
author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 147ec9096be430d0bc81be65fdf68f927c0f3dac
ms.sourcegitcommit: 044bb54cb4552c8f4651feb11d62e52726117e75
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/30/2019
ms.locfileid: "68661946"
---
# <a name="vstestconsoleexe-command-line-options"></a>VSTest.Console.exe – možnosti příkazového řádku

*VSTest. Console. exe* je nástroj příkazového řádku pro spouštění testů. Na příkazovém řádku můžete zadat několik možností v libovolném pořadí. Tyto možnosti jsou uvedeny v [obecných parametrech příkazového řádku](#general-command-line-options).

> [!NOTE]
> Adaptér MSTest v sadě Visual Studio funguje také v režimu starší verze (ekvivalent spuštění testů s *MSTest. exe*) kvůli kompatibilitě. V režimu starší verze nemůže využít funkci TestCaseFilter. Adaptér může přepnout do režimu starší verze, pokud je zadán soubor *testsettings* , **forcelegacymode** je nastaven na **hodnotu true** v souboru *runsettings* nebo pomocí atributů jako **HostType**.
>
> Chcete-li spustit automatizované testy na počítači založeném na architektuře ARM, je nutné použít *VSTest. Console. exe*.

## <a name="general-command-line-options"></a>Obecné možnosti příkazového řádku

V následující tabulce jsou uvedeny všechny možnosti pro *VSTest. Console. exe* a jejich krátký popis. Podobný souhrn můžete zobrazit zadáním `VSTest.Console/?` na příkazovém řádku.

| Možnost | Popis |
|---|---|
|**[*názvy testovacích souborů*]**|Spustí testy ze zadaných souborů. Více názvů testovacích souborů oddělte mezerami.<br />Příklady: `mytestproject.dll`,`mytestproject.dll myothertestproject.exe`|
|**/Settings: [*název souboru*]**|Spusťte testy s dalšími nastaveními, jako jsou například sběrače dat.<br />Příklad: `/Settings:Local.RunSettings`|
|**/Tests: [*název testu*]**|Spusťte testy s názvy, které obsahují zadané hodnoty. Chcete-li zadat více hodnot, oddělte je čárkami.<br />Příklad: `/Tests:TestMethod1,testMethod2`<br />Možnost příkazového řádku **/Tests** nelze použít s parametrem příkazového řádku **/TestCaseFilter** .|
|**/Parallel**|Určuje, že testy budou spuštěny paralelně. Ve výchozím nastavení je možné použít až všechna dostupná jádra v počítači. Počet jader, které se mají použít v souboru nastavení, můžete nakonfigurovat.|
|**/Enablecodecoverage**|Povolí adaptér diagnostiky dat CodeCoverage v testovacím běhu.<br />Výchozí nastavení se použijí, pokud není zadáno pomocí souboru nastavení.|
|**/Inisolation.**|Spustí testy v izolovaném procesu.<br />Tato izolace usnadňuje zastavení procesu *VSTest. Console. exe* na chybě v testech, ale testy mohou běžet pomaleji.|
|**/UseVsixExtensions**|Tato možnost zpřístupní proces *VSTest. Console. exe* nebo přeskočí nainstalované rozšíření VSIX (pokud existuje) v testovacím běhu.<br />Tato možnost je zastaralá. Od další hlavní verze sady Visual Studio může být tato možnost odebrána. Přejděte k využití rozšíření, která jsou zpřístupněna jako balíček NuGet.<br />Příklad: `/UseVsixExtensions:true`|
|**/TestAdapterPath:[*path*]**|Vynutí, aby proces *VSTest. Console. exe* používal vlastní testovací adaptéry ze zadané cesty (pokud existuje) v testovacím běhu.<br />Příklad: `/TestAdapterPath:[pathToCustomAdapters]`|
|**/Platform: [*typ platformy*]**|Cílová architektura platformy, která se má použít pro spuštění testu.<br />Platné hodnoty jsou x86, x64 a ARM.|
|**/Framework: [*Framework – verze*]**|Cílová verze rozhraní .NET, která se má použít pro spuštění testu.<br />Platné hodnoty jsou Framework35, Framework40, Framework45 a FrameworkUap10.<br />Je-li cílové rozhraní určeno jako **Framework35**, testy jsou spouštěny v modulu CLR 4,0 "compatibly Mode".<br />Příklad: `/Framework:framework40`|
|**/TestCaseFilter:[*expression*]**|Spustí testy, které odpovídají danému výrazu.<br />výraz\> < má formát < vlastnost\>= < hodnota\>[\|<ový výraz\>].<br />Příklad: `/TestCaseFilter:"Priority=1"`<br />Příklad: `/TestCaseFilter:"TestCategory=Nightly|FullyQualifiedName=Namespace.ClassName.MethodName"`<br />Možnost příkazového řádku **/TestCaseFilter** nelze použít s parametrem příkazového řádku **/Tests** . <br />Informace o vytváření a používání výrazů najdete v tématu [testovací případ Filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).|
|**/?**|Zobrazí informace o použití.|
|**/Logger: [*URI/FriendlyName*]**|Zadejte protokolovací nástroj pro výsledky testů.<br />Příklad: K protokolování výsledků do souboru sady Visual Studio Výsledky testů (TRX) použijte **/Logger: TRX**.<br />Příklad: K publikování výsledků testů do Team Foundation Server použijte TfsPublisher:<br />**/Logger: TfsPublisher;**<br />**Collection = adresa URL\>projektu <;**<br />**Název sestavení = < název\>sestavení;**<br />**TeamProject = < název\>projektu;**<br />**[; Platform =\<standardně "any CPU" >]**<br />**[; Charakter =\<výchozí nastavení "ladit" >]**<br />**[; RunTitle = < název\>]**|
|**/ListTests: [*název souboru*]**|Zobrazí seznam zjištěných testů z daného kontejneru testů.|
|**/ListDiscoverers**|Zobrazí seznam nainstalovaných zjišťování testů.|
|**/ListExecutors**|Zobrazí seznam nainstalovaných prováděcích modulů testů.|
|**/ListLoggers**|Zobrazí seznam nainstalovaných protokolovacích nástrojů testů.|
|**/ListSettingsProviders**|Zobrazí seznam nainstalovaných zprostředkovatelů nastavení testů.|
|**/Blame**|Sleduje testy při jejich provádění a, pokud proces hostitele testu selže, vygeneruje názvy testů v pořadí spuštění až do a včetně konkrétního testu, který byl spuštěn v době selhání. Tento výstup usnadňuje izolaci problematického testu a další diagnostiku. [Další informace](https://github.com/Microsoft/vstest-docs/blob/master/docs/extensions/blame-datacollector.md).|
|**/Diag: [*název souboru*]**|Zapíše protokoly trasování diagnostiky do zadaného souboru.|
|**/ResultsDirectory: [*cesta*]**|Adresář výsledků testů bude vytvořen v zadané cestě, pokud neexistuje.<br />Příklad: `/ResultsDirectory:<pathToResultsDirectory>`|
|**/ParentProcessId:[*parentProcessId*]**|ID procesu nadřazeného procesu zodpovědného za spuštění aktuálního procesu.|
|**/Port:[*port*]**|Port pro připojení soketu a příjem zpráv událostí.|
|**/Collect: [DataCollector*FriendlyName*]**|Povolí shromažďování dat pro testovací běh. [Další informace](https://aka.ms/vstest-collect).|

> [!TIP]
> V možnostech a hodnotách se nerozlišují velká a malá písmena.

## <a name="examples"></a>Příklady

Syntaxe pro spuštění *VSTest. Console. exe* je:

`Vstest.console.exe [TestFileNames] [Options]`

Následující příkaz spustí *VSTest. Console. exe* pro knihovnu testů **myTestProject. dll**:

```cmd
vstest.console.exe myTestProject.dll
```

Následující příkaz spustí *VSTest. Console. exe* s více testovacími soubory. Názvy testovacích souborů oddělte mezerami:

```cmd
Vstest.console.exe myTestFile.dll myOtherTestFile.dll
```

Následující příkaz spustí *VSTest. Console. exe* s několika možnostmi. Spustí testy v souboru *myTestFile. dll* v izolovaném procesu a použije nastavení zadané v *místním souboru. runsettings* . Kromě toho spustí pouze testy označené "Priorita = 1" a zaprotokoluje výsledky do souboru *. TRX* .

```cmd
vstest.console.exe  myTestFile.dll /Settings:Local.RunSettings /InIsolation /TestCaseFilter:"Priority=1" /Logger:trx
```
