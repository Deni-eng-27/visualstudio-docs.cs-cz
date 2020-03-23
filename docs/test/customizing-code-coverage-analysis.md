---
title: Přizpůsobení analýzy pokrytí kódu
ms.date: 08/21/2019
ms.topic: conceptual
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
author: mikejo5000
ms.openlocfilehash: bce7a6b9369f33e6fa5248821f58d9903172415c
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2020
ms.locfileid: "75918651"
---
# <a name="customize-code-coverage-analysis"></a>Přizpůsobení analýzy pokrytí kódu

Ve výchozím nastavení pokrytí kódu analyzuje všechna sestavení řešení, která jsou načtena během testů částí. Doporučujeme použít toto výchozí chování, protože funguje dobře většinu času. Další informace naleznete [v tématu Použití pokrytí kódu k určení, kolik kódu je testováno](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md).

Chcete-li vyloučit testovací kód z výsledků pokrytí kódu <xref:System.Diagnostics.CodeAnalysis.ExcludeFromCodeCoverageAttribute> a zahrnout pouze kód aplikace, přidejte atribut do testovací třídy.

Chcete-li zahrnout sestavení, která nejsou součástí vašeho řešení, získejte soubory *PDB* pro tato sestavení a zkopírujte je do stejné složky jako soubory *dll* sestavení.

## <a name="run-settings-file"></a>Spustit soubor nastavení

[Soubor nastavení spuštění](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md) je konfigurační soubor používaný nástroji pro testování částí. Upřesňující nastavení krytí kódu jsou určena v souboru *.runsettings.*

Chcete-li přizpůsobit pokrytí kódu, postupujte takto:

1. Přidejte do řešení soubor nastavení spuštění. V **Průzkumníku řešení**v místní nabídce řešení zvolte **Přidat** > **novou položku**a vyberte **soubor XML**. Uložte soubor s názvem, například *CodeCoverage.runsettings*.

2. Přidejte obsah z ukázkového souboru na konci tohoto článku a přizpůsobte jej podle svých potřeb, jak je popsáno v následujících částech.

::: moniker range="vs-2017"

3. Chcete-li vybrat soubor nastavení spuštění, zvolte v nabídce **Test** **Nastavení testů** > **Vybrat soubor nastavení testu**. Informace o určení souboru nastavení spuštění pro spuštění testů z příkazového řádku naleznete v [tématu Konfigurace testů jednotek](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md#command-line).

::: moniker-end

::: moniker range=">=vs-2019"

3. Chcete-li vybrat soubor nastavení spuštění, zvolte v nabídce **Test** **možnost Vybrat soubor nastavení**. Informace o určení souboru nastavení spuštění pro spuštění testů z příkazového řádku naleznete v [tématu Konfigurace testů jednotek](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md#command-line).

::: moniker-end

   Když vyberete **Analyzovat pokrytí kódu**, informace o konfiguraci se přečtou ze souboru nastavení spuštění.

   > [!TIP]
   > Všechny předchozí výsledky pokrytí kódu a zbarvení kódu nejsou automaticky skryty při spuštění testů nebo aktualizaci kódu.

::: moniker range="vs-2017"

Chcete-li vypnout a zapnout vlastní nastavení, odznačte nebo vyberte soubor v nabídce **Nastavení testu.** > **Test Settings**

![Nabídka Nastavení testu s vlastním souborem nastavení v Sadě Visual Studio 2017](../test/media/codecoverage-settingsfile.png)

::: moniker-end

::: moniker range=">=vs-2019"

Chcete-li vypnout a zapnout vlastní nastavení, odznačte nebo vyberte soubor v nabídce **Test.**

::: moniker-end

## <a name="symbol-search-paths"></a>Cesty pro vyhledávání symbolů

Pokrytí kódu vyžaduje soubory symbolů (*soubory PDB)* pro sestavení. U sestavení sestavených podle vašeho řešení jsou soubory symbolů obvykle k dispozici vedle binárních souborů a pokrytí kódu funguje automaticky. V některých případech můžete chtít zahrnout odkazovaná sestavení do analýzy pokrytí kódu. V takových případech nemusí být soubory *PDB* vedle binárních souborů, ale v souboru *.runsettings* můžete určit cestu hledání symbolů.

```xml
<SymbolSearchPaths>
      <Path>\\mybuildshare\builds\ProjectX</Path>
      <!--More paths if required-->
</SymbolSearchPaths>
```

> [!NOTE]
> Rozlišení symbolu může nějakou dobu trvat, zejména při použití vzdáleného umístění souboru s mnoha sestaveními. Proto zvažte kopírování souborů *PDB* do stejného místního umístění jako binární soubory *( DLL* a *EXE*).

## <a name="include-or-exclude-assemblies-and-members"></a>Zahrnout nebo vyloučit sestavení a členy

Můžete zahrnout nebo vyloučit sestavení nebo určité typy a členy z analýzy disponibility kódu. Pokud je oddíl **Zahrnout** prázdný nebo vynechaný, budou zahrnuta všechna sestavení, která jsou načtena a mají přidružené soubory PDB. Pokud sestavení nebo člen odpovídá klauzuli v části **Vyloučit,** je vyloučenz pokrytí kódu. Oddíl **Vyloučit** má přednost před oddílem **Zahrnout:** pokud je sestavení uvedeno v **části Zahrnout** i **Vyloučit**, nebude zahrnuto do pokrytí kódu.

Například následující XML vyloučí jedno sestavení zadáním jeho názvu:

```xml
<ModulePaths>
  <Exclude>
   <ModulePath>Fabrikam.Math.UnitTest.dll</ModulePath>
   <!-- Add more ModulePath nodes here. -->
  </Exclude>
</ModulePaths>
```

Následující příklad určuje, že do pokrytí kódu by mělo být zahrnuto pouze jedno sestavení:

```xml
<ModulePaths>
  <Include>
   <ModulePath>Fabrikam.Math.dll</ModulePath>
   <!-- Add more ModulePath nodes here. -->
  </Include>
</ModulePaths>
```

V následující tabulce jsou uvedeny různé způsoby, jak sestavení a členy mohou být spárovány pro zahrnutí nebo vyloučení z pokrytí kódu.

| Element XML | Co odpovídá |
| - | - |
| Cesta modulu | Shoduje se se stavy určenými názvem sestavení nebo cestou souboru. |
| CompanyName | Odpovídá sestavení podle atributu **Company.** |
| Publickeytoken | Odpovídá podepsaným sestavením tokenem veřejného klíče. |
| Zdroj | Odpovídá prvkům podle názvu cesty zdrojového souboru, ve kterém jsou definovány. |
| Atribut | Odpovídá prvkům, které mají zadaný atribut. Zadejte úplný název atributu, `<Attribute>^System\.Diagnostics\.DebuggerHiddenAttribute$</Attribute>`například .<br/><br/>Pokud <xref:System.Runtime.CompilerServices.CompilerGeneratedAttribute> atribut vyloučíte, kód, `async` `await`který `yield return`používá funkce jazyka, jako jsou , , a automaticky implementované vlastnosti, je vyloučen z analýzy pokrytí kódu. Chcete-li vyloučit skutečně generovaný kód, vylučte pouze <xref:System.CodeDom.Compiler.GeneratedCodeAttribute> atribut. |
| Funkce | Odpovídá procedurám, funkcím nebo metodám podle plně kvalifikovaného názvu, včetně seznamu parametrů. Část názvu můžete také porovnat pomocí [regulárního výrazu](#regular-expressions).<br/><br/>Příklady:<br/><br/>`Fabrikam.Math.LocalMath.SquareRoot(double);`(C#)<br/><br/>`Fabrikam::Math::LocalMath::SquareRoot(double)`(C++) |

### <a name="regular-expressions"></a>Regulární výrazy

Zahrnout a vyloučit uzly používají regulární výrazy, které nejsou stejné jako zástupné znaky. Ve shodách se nerozlišují velká a malá písmena. Tady je několik příkladů:

- **. \* ** odpovídá řetězci libovolných znaků

- **\\.** odpovídá tečka "."

- ( ) odpovídá závorce "( )" ** \\ \\**

- **\\\\**odpovídá oddělovači cesty\\k souboru " "

- **^** odpovídá začátku řetězce

- **$** odpovídá konci řetězce

Následující jazyk XML ukazuje, jak zahrnout a vyloučit určitá sestavení pomocí regulárních výrazů:

```xml
<ModulePaths>
  <Include>
    <!-- Include all loaded .dll assemblies (but not .exe assemblies): -->
    <ModulePath>.*\.dll$</ModulePath>
  </Include>
  <Exclude>
    <!-- But exclude some assemblies: -->
    <ModulePath>.*\\Fabrikam\.MyTests1\.dll$</ModulePath>
    <!-- Exclude all file paths that contain "Temp": -->
    <ModulePath>.*Temp.*</ModulePath>
  </Exclude>
</ModulePaths>
```

Následující jazyk XML ukazuje, jak zahrnout a vyloučit určité funkce pomocí regulárních výrazů:

```xml
<Functions>
  <Include>
    <!-- Include methods in the Fabrikam namespace: -->
    <Function>^Fabrikam\..*</Function>
    <!-- Include all methods named EqualTo: -->
    <Function>.*\.EqualTo\(.*</Function>
  </Include>
  <Exclude>
    <!-- Exclude methods in a class or namespace named UnitTest: -->
    <Function>.*\.UnitTest\..*</Function>
  </Exclude>
</Functions>
```

> [!WARNING]
> Pokud je chyba v regulárním výrazu, jako je například unescaped nebo neodpovídající závorky, analýza pokrytí kódu se nespustí.

Další informace o regulárních výrazech naleznete [v tématu Použití regulárních výrazů v sadě Visual Studio](../ide/using-regular-expressions-in-visual-studio.md).

## <a name="sample-runsettings-file"></a>Ukázkový soubor s příponou .runsettings

Zkopírujte tento kód a upravte jej tak, aby vyhovoval vašim potřebám.

```xml
<?xml version="1.0" encoding="utf-8"?>
<!-- File name extension must be .runsettings -->
<RunSettings>
  <DataCollectionRunSettings>
    <DataCollectors>
      <DataCollector friendlyName="Code Coverage" uri="datacollector://Microsoft/CodeCoverage/2.0" assemblyQualifiedName="Microsoft.VisualStudio.Coverage.DynamicCoverageDataCollector, Microsoft.VisualStudio.TraceCollector, Version=11.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a">
        <Configuration>
          <CodeCoverage>
<!--
Additional paths to search for .pdb (symbol) files. Symbols must be found for modules to be instrumented.
If .pdb files are in the same folder as the .dll or .exe files, they are automatically found. Otherwise, specify them here.
Note that searching for symbols increases code coverage runtime. So keep this small and local.
-->
<!--
            <SymbolSearchPaths>
                   <Path>C:\Users\User\Documents\Visual Studio 2012\Projects\ProjectX\bin\Debug</Path>
                   <Path>\\mybuildshare\builds\ProjectX</Path>
            </SymbolSearchPaths>
-->

<!--
About include/exclude lists:
Empty "Include" clauses imply all; empty "Exclude" clauses imply none.
Each element in the list is a regular expression (ECMAScript syntax). See /visualstudio/ide/using-regular-expressions-in-visual-studio.
An item must first match at least one entry in the include list to be included.
Included items must then not match any entries in the exclude list to remain included.
-->

            <!-- Match assembly file paths: -->
            <ModulePaths>
              <Include>
                <ModulePath>.*\.dll$</ModulePath>
                <ModulePath>.*\.exe$</ModulePath>
              </Include>
              <Exclude>
                <ModulePath>.*CPPUnitTestFramework.*</ModulePath>
              </Exclude>
            </ModulePaths>

            <!-- Match fully qualified names of functions: -->
            <!-- (Use "\." to delimit namespaces in C# or Visual Basic, "::" in C++.)  -->
            <Functions>
              <Exclude>
                <Function>^Fabrikam\.UnitTest\..*</Function>
                <Function>^std::.*</Function>
                <Function>^ATL::.*</Function>
                <Function>.*::__GetTestMethodInfo.*</Function>
                <Function>^Microsoft::VisualStudio::CppCodeCoverageFramework::.*</Function>
                <Function>^Microsoft::VisualStudio::CppUnitTestFramework::.*</Function>
              </Exclude>
            </Functions>

            <!-- Match attributes on any code element: -->
            <Attributes>
              <Exclude>
                <!-- Don't forget "Attribute" at the end of the name -->
                <Attribute>^System\.Diagnostics\.DebuggerHiddenAttribute$</Attribute>
                <Attribute>^System\.Diagnostics\.DebuggerNonUserCodeAttribute$</Attribute>
                <Attribute>^System\.CodeDom\.Compiler\.GeneratedCodeAttribute$</Attribute>
                <Attribute>^System\.Diagnostics\.CodeAnalysis\.ExcludeFromCodeCoverageAttribute$</Attribute>
              </Exclude>
            </Attributes>

            <!-- Match the path of the source files in which each method is defined: -->
            <Sources>
              <Exclude>
                <Source>.*\\atlmfc\\.*</Source>
                <Source>.*\\vctools\\.*</Source>
                <Source>.*\\public\\sdk\\.*</Source>
                <Source>.*\\microsoft sdks\\.*</Source>
                <Source>.*\\vc\\include\\.*</Source>
              </Exclude>
            </Sources>

            <!-- Match the company name property in the assembly: -->
            <CompanyNames>
              <Exclude>
                <CompanyName>.*microsoft.*</CompanyName>
              </Exclude>
            </CompanyNames>

            <!-- Match the public key token of a signed assembly: -->
            <PublicKeyTokens>
              <!-- Exclude Visual Studio extensions: -->
              <Exclude>
                <PublicKeyToken>^B77A5C561934E089$</PublicKeyToken>
                <PublicKeyToken>^B03F5F7F11D50A3A$</PublicKeyToken>
                <PublicKeyToken>^31BF3856AD364E35$</PublicKeyToken>
                <PublicKeyToken>^89845DCD8080CC91$</PublicKeyToken>
                <PublicKeyToken>^71E9BCE111E9429C$</PublicKeyToken>
                <PublicKeyToken>^8F50407C4E9E73B6$</PublicKeyToken>
                <PublicKeyToken>^E361AF139669C375$</PublicKeyToken>
              </Exclude>
            </PublicKeyTokens>

            <!-- We recommend you do not change the following values: -->

            <!-- Set this to True to collect coverage information for functions marked with the "SecuritySafeCritical" attribute. Instead of writing directly into a memory location from such functions, code coverage inserts a probe that redirects to another function, which in turns writes into memory. -->
            <UseVerifiableInstrumentation>True</UseVerifiableInstrumentation>
            <!-- When set to True, collects coverage information from child processes that are launched with low-level ACLs, for example, UWP apps. -->
            <AllowLowIntegrityProcesses>True</AllowLowIntegrityProcesses>
            <!-- When set to True, collects coverage information from child processes that are launched by test or production code. -->
            <CollectFromChildProcesses>True</CollectFromChildProcesses>
            <!-- When set to True, restarts the IIS process and collects coverage information from it. -->
            <CollectAspDotNet>False</CollectAspDotNet>

          </CodeCoverage>
        </Configuration>
      </DataCollector>
    </DataCollectors>
  </DataCollectionRunSettings>
</RunSettings>
```

## <a name="see-also"></a>Viz také

- [Konfigurace testů jednotek pomocí souboru nastavení spuštění](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md)
- [Použití pokrytí kódu k určení, kolik kódu je testováno](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)
- [Testování částí kódu](../test/unit-test-your-code.md)
