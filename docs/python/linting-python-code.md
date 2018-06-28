---
title: Použití PyLint pro linting kód Python
description: Jak používat PyLint v sadě Visual Studio Zkontrolujte problémy v kódu jazyka Python.
ms.date: 06/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: dba3c262e7c36f1b21ba84a172daa91901fb32f4
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2018
ms.locfileid: "37056739"
---
# <a name="using-pylint-to-check-python-code"></a>Použití PyLint ke kontrole kód Python

[PyLint](https://www.pylint.org/), často používaný nástroj, který kontroluje chybami v kódu jazyka Python a může vést ke vzniku dobrý Python kódování vzory, je integrovaná do sady Visual Studio pro projektů v jazyce Python.

Právě Python projekt v Průzkumníku řešení klikněte pravým tlačítkem a vyberte **Python > spustit PyLint...** :

![Příkaz PyLint na kontextovou nabídku projektů v jazyce Python](media/code-pylint-command.png)

Použití tohoto příkazu výzvu k instalaci PyLint do aktivního prostředí, pokud již není přítomen.

PyLint upozornění a chyb se zobrazí v okně Seznam chyb:

![Seznam chyb PyLint](media/code-pylint-error-list.png)

Poklepáním na chybu přejdete přímo na zdrojový kód, který vygeneroval tento problém.

> [!Tip]
> Najdete v článku [PyLint funkce odkaz](https://pylint.readthedocs.io/en/latest/technical_reference/features.html) podrobný seznam všech PyLint výstup zpráv.

## <a name="setting-pylint-command-line-options"></a>Nastavení možnosti příkazového řádku PyLint

[Možnosti příkazového řádku](https://pylint.readthedocs.io/en/latest/user_guide/run.html#command-line-options) část PyLint dokumentace popisuje, jak můžete řídit chování na PyLint prostřednictvím `.pylintrc` konfigurační soubor. Takový soubor mohou být umístěny v kořenu projektu Python v sadě Visual Studio nebo jinde v závislosti na tom, jak často chcete tato nastavení použita (viz [možnosti příkazového řádku](https://pylint.readthedocs.io/en/latest/user_guide/run.html#command-line-options) podrobnosti).

Například potlačení upozornění "chybějící docstring" viz předchozí obrázek s `.pylintrc` souboru v projektu, postupujte podle kroků:

1. Na příkazovém řádku přejděte do kořenového adresáře projektu (která obsahuje vaše `.pyproj` souboru) a spusťte následující příkaz pro vytvoření komentáři konfiguračního souboru:

   ```command
   pylint --generate-rcfile > .pylintrc
   ```

1. V Průzkumníku řešení Visual Studio, klikněte pravým tlačítkem na projekt, vyberte **Přidat > ukončení položky...** , přejděte do a vyberte novou `.pylintrc` soubor a vyberte **přidat**.

1. Otevřete soubor pro úpravy, který obsahuje řadu nastavení, se kterými můžete pracovat. Chcete-li zakázat upozornění, vyhledejte `[MESSAGES CONTROL]` části a pak vyhledejte `disable` nastavení v této části. Není dlouhý řetězec konkrétní zpráv, na které můžete připojit upozornění, podle toho, která má. V tomto příkladu, připojit `,missing-docstring` (včetně vymezování čárkou).

1. Uložit `.pylintrc` souboru a spusťte PyLint zjistíte, že jsou teď potlačovány upozornění.

> [!Tip]
> Použít `.pylintrc` souboru ze sdílené síťové složky, vytvořit proměnnou prostředí s názvem `PYLINTRC` s hodnotou název souboru v síti sdílet pomocí cesty UNC nebo písmeno mapovaná jednotka. Například `PYLINTRC=\\myshare\python\.pylintrc`.
