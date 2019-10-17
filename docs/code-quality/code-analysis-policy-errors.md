---
title: Chyby zásad Analýzy kódu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.policyfailures
helpviewer_keywords:
- policy errors, code analysis
ms.assetid: d1f221cd-68c0-4277-9397-b76ad0dbae77
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 661f029b617c430f7205552080a94affc5bd543b
ms.sourcegitcommit: 485ffaedb1ade71490f11cf05962add1718945cc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72445885"
---
# <a name="code-analysis-policy-errors"></a>Chyby zásad Analýzy kódu

Pokud není splněna zásada analýzy kódu při vrácení se změnami, dojde k následujícím chybám:

**Nastavení analýzy kódu pro jeden nebo více projektů není kompatibilní se zásadami analýzy kódu.**

Pro jeden nebo více projektů kódu nebyl splněn požadavek na analýzu kódu pro kontrolu zdroje projektu. Tato chyba může být způsobena jednou nebo více z následujících podmínek:

- Analýza kódu není v sestavení povolena pro všechny projekty v řešení.

- Místní sada pravidel pro projekt v sadě Visual Studio má méně omezující nastavení **Akce** než sada pravidel projektu, například pravidlo nastavené na **akci**=**Chyba** na serveru má svou **akci** nastavenou na hodnotu **varování** nebo **Žádná** v sadě pravidel, která se spouští v sadě Visual Studio).

- Sada pravidel zadaná v sadě Visual Studio neobsahuje všechna pravidla, která jsou uvedena v sadě pravidel zadané v zásadě pro vrácení se změnami analýzy kódu pro projekt.

**Zásady analýzy kódu selhaly. V projektu jsou chyby {0} nebo sestavení není aktuální.**

Buď sestavení obsahuje chyby, nebo byly chyby opraveny, ale analýza kódu nebyla provedena po opravě.

**Vrácení se změnami se nezdařilo. Zásady analýzy kódu vyžadují, abyste se mohli vrátit se změnami prostřednictvím sady Visual Studio s otevřeným řešením.**

Zásady analýzy kódu vyžadují, aby všechny soubory vracené se změnami měly být v aktuálně otevřeném řešení. Chcete-li opravit tuto chybu, otevřete řešení, které obsahuje soubor, který má být vrácen se změnami.

**Ne všechny soubory v probíhajícím vracení se změnami jsou v aktuálně otevřeném řešení.**

Zásady analýzy kódu vyžadují, aby všechny soubory vracené se změnami měly být v aktuálně otevřeném řešení. Tato chyba se vyvolá, když je otevřené řešení, ale některé soubory v zobrazení "čeká na vrácení se změnami" nejsou součástí aktuálně otevřeného řešení. Chcete-li opravit tuto chybu, otevřete řešení, které obsahuje soubor, který má být vrácen se změnami.

**Verze {0} není správná. Silný název zadaný v zásadě je {1}.**

Tato chyba se vztahuje na projekty .NET. Pravidlo. DLL vyžadované zásadami analýzy kódu existuje v místním počítači, ale verze/veřejný klíč se neshoduje. Aby bylo možné tuto chybu opravit, musí tvůrce zásad aktualizovat knihovny DLL ve *složce C:\Program Files\Microsoft Visual Studio 8 \ Team Tools\Static Analysis Tools\FxCop\Rules @ no__t-1* Directory na svém počítači.

**sestavení {0} zadané v zásadách neexistuje.**

Tato chyba se vztahuje na projekty .NET. Pravidlo vyžadované zásadami analýzy kódu nemá v klientském počítači nainstalovanou odpovídající knihovnu DLL. Aby bylo možné tuto chybu opravit, musí tvůrce zásad aktualizovat knihovnu DLL ve *složce C:\Program Files\Microsoft Visual Studio 8 \ Team Tools\Static Analysis Tools\FxCop\Rules @ no__t-1* Directory na svém počítači.

**Nastavení pravidla @no__t projektu-1 nejsou v souladu se zásadami analýzy kódu.**

Tato chyba se vztahuje na projekty .NET. Nastavení pravidel spravovaného kódu nejsou tak striktní, protože zásady vyžadují. Chcete-li tuto chybu opravit, musí být nastavení klienta stejné nebo přísnější než požadavek zásad na serveru.

**Analýza kódu není povolena v aktivní konfiguraci. Před vrácením se změnami přepněte na konfigurační {0} a sestavte projekt {1}.**

V [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] má aktivní konfigurace povolenu analýzu kódu, ale je povolena alespoň jedna analýza kódu.

**Je nutné povolit analýzu kódu pro spravované binární soubory v projektu @no__t vlastnosti-1 a sestavení před vrácením se změnami.**

Tato chyba se vztahuje na aplikace .NET [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)]. Tato zásada vyžaduje, aby byla provedena analýza spravovaného kódu, ale není povolena v aktuálním projektu na klientovi.

**Je nutné povolit analýzu kódu v projektu @no__t vlastnosti-1 a sestavení před vrácením se změnami.**

Tato chyba se aplikuje na projekty [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a webové projekty. Tato zásada vyžaduje, aby byla provedena analýza spravovaného kódu, ale není povolena v aktuálním projektu na klientovi.

**Před vrácením se změnamiC++ je nutné povolit analýzu kódu v projektu {0} a sestavení.**

Tato chyba se týká nespravovaných projektů. Zásady analýzy kódu vyžadují analýzu kódu pro C/C++, ale nejsou povolené v aktuálním projektu na klientovi.

## <a name="see-also"></a>Viz také

- [Chyby aplikace Analýzy kódu](../code-quality/code-analysis-application-errors.md)
