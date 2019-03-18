---
title: Použití Pylintu pro kód Python
description: Spusťte PyLint v sadě Visual Studio ke kontrole problémů v kódu Pythonu, včetně možnosti příkazového řádku k přizpůsobení linting.
ms.date: 03/13/2019
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: jillfra
ms.custom: seodec18
ms.workload:
- python
- data-science
ms.openlocfilehash: 0d18c7cb5f27695478e296d308347aaaf1b20f94
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58153731"
---
# <a name="use-pylint-to-check-python-code"></a>Použití Pylintu ke kontrole kódu v Pythonu

[Pylintu](https://www.pylint.org/), je často používaný nástroj, který kontroluje chyby v kódu Pythonu a může vést ke vzniku dobré psaní kódu, Python integrované do sady Visual Studio pro projekty v Pythonu.

## <a name="run-pylint"></a>Spustit PyLint

Stačí pravým tlačítkem na projekt Python v **Průzkumníka řešení** a vyberte **Python** > **spustit Pylintu**:

![Příkaz Pylintu kontextové nabídky pro projekty v Pythonu](media/code-pylint-command.png)

Pomocí tohoto příkazu vás vyzve k instalaci Pylintu do vašeho prostředí active, pokud ještě není k dispozici.

Pylintu upozornění a chyby se zobrazí **seznam chyb** okno:

![Seznam chyb Pylintu](media/code-pylint-error-list.png)

Poklepáním na chybu přejdete přímo ke zdrojovému kódu, který vygeneroval tento problém.

> [!Tip]
> Najdete v článku [Pylintu funkce odkaz](https://pylint.readthedocs.io/en/latest/technical_reference/features.html) podrobný seznam všech Pylintu výstupní zprávy.

## <a name="set-pylint-command-line-options"></a>Nastavení možností příkazového řádku Pylintu

[Možnosti příkazového řádku](https://pylint.readthedocs.io/en/latest/user_guide/run.html#command-line-options) část Pylintu dokumentace popisuje, jak řídit chování Pylintu společnosti prostřednictvím *.pylintrc* konfigurační soubor. Tento soubor je možné použít v kořenovém adresáři projektu Pythonu v sadě Visual Studio nebo jinde v závislosti na tom, jak často chcete tato nastavení použijí (najdete v článku [možnosti příkazového řádku](https://pylint.readthedocs.io/en/latest/user_guide/run.html#command-line-options) podrobnosti).

Například tato upozornění už nezobrazovala "chybí docstring" je vidět na předchozím obrázku s *.pylintrc* soubor v projektu, proveďte kroky:

1. Na příkazovém řádku přejděte do kořenového adresáře projektu (který má vaše *.pyproj* soubor) a spusťte následující příkaz pro vytvoření komentářem konfiguračního souboru:

   ```command
   pylint --generate-rcfile > .pylintrc
   ```

1. V Průzkumníku řešení Visual Studio, klikněte pravým tlačítkem na projekt, vyberte **přidat** > **existující položku**, přejděte k novému *.pylintrc* souboru, vyberte ho, a Vyberte **přidat**.

1. Otevřete soubor pro úpravy, který má několik nastavení, které můžete pracovat. Chcete-li zakázat upozornění, vyhledejte `[MESSAGES CONTROL]` části a pak vyhledejte `disable` nastavení v této části. Je to dlouhý řetězec určitých zpráv, ke kterým můžete připojit libovolným upozornění chcete. V tomto příkladu, připojte `,missing-docstring` (včetně vymezování čárkami).

1. Uložit *.pylintrc* souboru a spustit PyLint znovu, abyste viděli, že jsou nyní potlačit upozornění.

> [!Tip]
> Použití *.pylintrc* souboru ze sdílené síťové složky, vytvořte proměnnou prostředí s názvem `PYLINTRC` s hodnotou název souboru v síti sdílet pomocí cesty UNC nebo písmeno jednotky pro mapovanou. Například `PYLINTRC=\\myshare\python\.pylintrc`.
