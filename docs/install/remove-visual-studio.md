---
title: "Odebrání Visual Studio 2017 | Microsoft Docs"
description: "Zjistěte, jak odebrat Visual Studio, krok za krokem."
ms.custom: 
ms.date: 09/12/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- uninstall
- uninstall Visual Studio
- remove
- remove Visual Studio
- cleanup
- cleanup Visual Studio
- clean up
- clean up Visual Studio
ms.assetid: 9c81a777-9c95-4934-b517-c60c6dc78799
author: heaths
ms.author: heaths
manager: erickn
ms.workload: multiple
ms.openlocfilehash: a08a24be4f3f9e915a93c9beac7cf5e5c28eb7ca
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="remove-visual-studio"></a>Odebrání Visual Studio

Pokud dojde k závažné chybě a nelze opravit nebo odinstalovat Visual Studio, můžete spustit `InstallCleanup.exe` nástroj pro odebrání instalační soubory a informace o produktu. Spuštění tohoto nástroje je potřeba udělat jako poslední možnost, pokud opravit nebo odinstalovat služeb při selhání a může odinstalovat funkce z jiné instalace sady Visual Studio nebo jiné produkty, které je třeba opravit.

V níže uvedených pokynů můžete spustit nástroj s přepínače příkazového řádku s následující chování:

| přepínače | Chování |
| ------ | -------- |
| `-i`   | Tento přepínač je výchozí, pokud je předán žádný jiný přepínač a odstraní pouze hlavní instalační adresář a produktu informace. Toto chování je vhodnější, pokud chcete přeinstalovat stejnou verzi, po spuštění `InstallCleanup.exe` nástroj. |
| `-f`   | Zadání tohoto přepínače odebere hlavní instalační adresář, informace o produktu a většina další funkce, které jsou nainstalované mimo instalační adresář, který může být sdíleny s další instalace sady Visual Studio nebo jiné produkty. Toto chování je vhodnější, pokud máte v úmyslu odebrat Visual Studio bez přeinstalace později. |

1. Ukončete instalační program sady Visual Studio.
2. Otevřete příkazový řádek správce. Chcete-li otevřít příkazový řádek správce, postupujte takto:
   * Na **spustit** nabídky, klikněte na tlačítko **spustit** (Start + R).
   * Typ **cmd**.
   * Klikněte pravým tlačítkem na **příkazového řádku**a potom klikněte na **spustit jako správce**.
3. Zadejte úplnou cestu `InstallCleanup.exe` nástroj a předejte kteroukoli přepínač příkazového řádku požadavky. Ve výchozím nastavení cestu nástroje je následující:
   ```
   C:\Program Files (x86)\Microsoft Visual Studio\Installer\resources\app\layout\InstallCleanup.exe
   ```

Pokud nenajdete `InstallCleanup.exe` v adresáři instalační program Visual Studio – vždy nachází v `%ProgramFiles(x86)%\Microsoft Visual Studio` – postupujte podle pokynů a [instalaci sady Visual Studio](install-visual-studio.md) a když se zobrazí obrazovka výběru pracovního vytížení, zavřete okno a postupujte podle předchozí kroky opakujte.

## <a name="get-support"></a>Získat podporu
V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránky. Pokud se žádný z kroků pro řešení potíží, kontaktujte nás pomocí živé konverzace pro pomoc s instalací (pouze v angličtině). Podrobnosti najdete v tématu [stránky podpory sady Visual Studio](https://www.visualstudio.com/vs/support/#talktous).

Tady je několik další možnosti podpory:
* Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu v [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/)a klást otázky a odpovědi.
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím našich [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio).  (Tato možnost vyžaduje [Githubu](https://github.com/) účtu.)

## <a name="see-also"></a>Viz také
* [Nainstalovat Visual Studio 2017](install-visual-studio.md)
* [Aktualizace Visual Studio 2017](update-visual-studio.md)
* [Upravit Visual Studio 2017](modify-visual-studio.md)
* [Odinstalace Visual Studio 2017](uninstall-visual-studio.md)
