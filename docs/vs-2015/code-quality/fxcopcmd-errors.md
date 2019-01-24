---
title: FxCopCmd – chyby
ms.date: 10/19/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
helpviewer_keywords:
- FxCopCmd errors
ms.author: gewarren
author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4d723065e224058b7e269299aad2900f97a1425d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54786597"
---
# <a name="fxcopcmd-tool-errors"></a>Fxcopcmd – chyby nástroje

Fxcopcmd – nebere v úvahu všechny chyby, chcete-li být závažné. Pokud fxcopcmd – má dostatek informací k provedení částečné analýzy, provede analýzu a sestavy chyb, ke kterým došlo. Kód chyby, která je 32bitové celé číslo, obsahuje bitová kombinace číselných hodnot, které odpovídají chyby.

Následující tabulka popisuje kódů chyb vrácených nástrojem fxcopcmd –:

|Chyba|Číselná hodnota|
|-----------|-------------------|
|Žádné chyby|0x0|
|Chyba analýzy|0x1|
|Pravidlo výjimky|0x2|
|Chyba při načítání projektu|0x4|
|Chyba při načítání sestavení|0x8|
|Chyba při načítání knihovny pravidlo|0x10|
|Chyba při načítání sestavy importu|0x20|
|Chyba výstupu|0x40|
|Chyba přepínač příkazového řádku|0x80|
|Chyba při inicializaci|0x100|
|Chyba odkazy na sestavení|0x200|
|BuildBreakingMessage|0x400|
|Došlo k neznámé chybě|0x1000000|

**Chyba analýzy** dochází k závažným chybám. Znamená to, že analýzu nelze dokončit. Pokud se používá, kód chyby: také obsahuje základní příčiny závažná chyba. Následující podmínky generovat závažné chyby:

- Analýzy nelze provést z důvodu nedostatečné vstup.

- Analýzy došlo k výjimce, která není zpracována fxcopcmd –.

- Zadaný soubor projektu nebyl nalezen nebo je poškozený.

- Možnost výstupu se nezadalo nebo nebylo možné zapsat soubor.

> [!NOTE]
> Fxcopcmd – návratový kód **sestavení odkazuje na chyby** 0x200 sám o sobě je varování spíše než chybu. Tento návratový kód znamená, že, který chybí některé nepřímé odkazy, ale, že byl schopen zpracovat je fxcopcmd –. Toto upozornění znamená, že je možné, že některé výsledky analýzy mohl být ohrožený. Nakládat s **sestavení odkazuje na chyby** za chybu, pokud se zkombinuje s jakýkoli návratový kód.

## <a name="see-also"></a>Viz také:

- [Chyby aplikace Analýzy kódu](../code-quality/code-analysis-application-errors.md)