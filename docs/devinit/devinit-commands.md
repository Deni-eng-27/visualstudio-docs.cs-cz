---
title: Příkazy devinit
description: Podrobnosti o tom, jak použít příkazy devinit k instalaci komponent.
ms.date: 08/28/2020
ms.topic: reference
author: andysterland
ms.author: andster
manager: jillfra
ms.workload:
- multiple
monikerRange: '>= vs-2019'
ms.prod: visual-studio-windows
ms.technology: devinit
ms.openlocfilehash: a22e0f5a20050e62aa9978c40f2189c82ca3071c
ms.sourcegitcommit: 13cf7569f62c746708a6ced1187d8173eda7397c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/25/2020
ms.locfileid: "91352325"
---
# <a name="devinit-commands"></a>příkazy devinit

## <a name="init"></a>Init

```console
> devinit init
```

Inicializujte prostředí spuštěním nástrojů určených v [_.devinit.jspro_](devinit-json.md) soubor v aktuálním pracovním adresáři.  

### <a name="options-for-init"></a>Možnosti pro init

Volitelné možnosti pro `devinit init` příkaz

| Argument             | Povinné | Popis                                                               |
|----------------------|----------|---------------------------------------------------------------------------|
| -f,--soubor           | No       | Cesta k _.devinit.jsv_ souboru                                         |
| --Error-Action       | No       | Určuje, jak se mají zpracovávat chyby. Možnosti: zastavit, ignorovat, pokračovat (výchozí).|
| -v,--verbose         | No       | Vygeneruje podrobný výstup.                                                      |
| -n,--suchého běhu         | No       | Suché spuštění.                                                                  |

## <a name="run"></a>Spustit

```console
> devinit run -t <toolname>
```

Spustí konkrétní nástroj, níže uvedené parametry. Konkrétní použití najdete v [dokumentaci](devinit-tool-list.md) k jednotlivým nástrojům.

### <a name="options-for-run"></a>Možnosti spuštění

Možnosti `devinit run` příkazu

| Argument                                  | Povinné | Popis                                                                          |
|-------------------------------------------|----------|--------------------------------------------------------------------------------------|
| -t,--nástroj                                 | Yes      | Povinná hodnota. Název nástroje.                                                             |
| -i,--vstup                                | No       | Vstupní hodnota nástroje Například název souboru, balíček nebo název.                           |
| --Error-Action                            | No       | Určuje způsob zpracování chyb nástrojů: zastavit, ignorovat, pokračovat. Výchozím nastavením je zastavit. |
| -v,--verbose                              | No       | Vygeneruje podrobný výstup.                                                                 |
| -n,--suchého běhu                              | No       | Suché spuštění.                                                                             |
| --&lt;arg1 &gt; &lt; arg2 &gt; &lt; argn&gt;  | No       | Další argumenty příkazového řádku nástroje.                                       |

#### <a name="--file-argument"></a>--argument souboru

Určuje cestu k _devinit.jsv souboru. Pokud – soubor není zadaný, hledáme výchozí soubor v následujících umístěních:

* {Current-Directory} \\.devinit.jsna
* {Current-Directory} \\ . devinit \\.devinit.js

`.`Budou se také shodovat cesty bez úvodní složky v adresáři nebo názvu souboru.

#### <a name="--error-action-argument"></a>--error – argument akce

Určuje akci, která má být provedena, pokud nástroj vrátí nenulový ukončovací kód. Platné hodnoty jsou:

| Argument | Popis                                                                                                                                                                                                                                                                           |
|----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| continue | Pokračovat v zpracovávání jiných nástrojů po vygenerování chyby se standardní chybou Ukončovací kód devinit.exe je nenulový (selhání). Toto chování je podobné akci zastavení chyby, ale zpracování pokračuje. `continue` je výchozí chyba – akce příkazu init.              |
| ignorovat   | Pokračujte v zpracovávání jiných nástrojů po vygenerování upozornění na standardní výstup. Ukončovací kód procesu DevInit by měl vždy být nula (úspěch). `ignore`Nastavení ignoruje všechny chyby.                                                                                                      |
| Zastavit     | Vygeneruje chybu standardní chyby a zastaví zpracování nástrojů. Ukončovací kód devinit.exe je nenulový (selhání). Jedná se o podobnou akci pokračovat při chybě, ale zpracování je zastaveno při první zjištěné chybě. `stop` je výchozí chyba – akce pro všechny příkazy s výjimkou init. |

#### <a name="--dry-run-switch"></a>– přepínač suchého běhu

Příkazy nástroje echo, které by se spustily, ale nespouštějí žádné nástroje. 

#### <a name="--verbose-switch"></a>--verbose Switch

Vygeneruje podrobný výstup do standardního výstupu. Pokud nástroj, který má být spuštěn, podporuje možnost verbose, rozšiřte podrobný přepínač na nástroj.

#### <a name="additional-command-line-arguments"></a>Další argumenty příkazového řádku

Použití prvku `<arg>` , který obsahuje místo ve své hodnotě, musí zahrnovat další dvojici řídicích uvozovek.

```console
> devinit run -t <toolname> -<somearg> "<some value>"
```

Pro instalaci dotnet do konkrétního adresáře `C:\Program Files\dotnet` :

```console
> devinit run -t require-dotnetcoresdk --"-InstallDir \"C:\Program Files\dotnet\""
```

## <a name="list"></a>Seznam

```console
> devinit list
```

Zobrazí seznam všech dostupných nástrojů.

## <a name="show"></a>Zobrazit

```console
> devinit show -t <toolname>
```

| Argument       | Povinné | Popis                                                                          |
|----------------|----------|--------------------------------------------------------------------------------------|
| -t,--nástroj      | Yes      | Povinná hodnota. Název nástroje.                                                             |

Vytiskne informace o nápovědě pro daný nástroj.

## <a name="version"></a>Verze

```console
> devinit version
```

Vytiskne aktuální informace o verzi pro devinit.

## <a name="help"></a>Nápověda

```console
> devinit help
> devinit help list
```

Vytiskne text v nápovědě pro devinit nebo pro konkrétní příkaz `devinit <command>` .
 