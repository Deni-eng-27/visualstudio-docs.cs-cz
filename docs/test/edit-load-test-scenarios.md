---
title: Scénáře testování zatížení
ms.date: 10/03/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, scenarios
- load tests, user activities
- load tests, modeling scenarios
ms.assetid: fec04f2e-bf38-4d44-b2ec-fa50f58fd0d9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 647548a59c965b6feacb994efa041ecd5b6c6b91
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62786161"
---
# <a name="edit-load-test-scenarios"></a>Úpravy scénářů zátěžových testů

Zátěžový test *scénář* Určuje vzor zatížení, kombinaci testů, kombinace prohlížečů a kombinaci sítí. Scénáře jsou důležité, protože umožňují konfigurace testů k simulaci reálné, komplexní úlohy.

Například můžete testovat server e-commerce s internetovým front-endu používá stovky souběžných zákazníci už průběhu mnoha rychlosti připojení a s různými prohlížeči. Stejný web může mít také funkci správy, které používají interní zaměstnanci k aktualizaci produktů a zobrazování statistických údajů. Tito interní uživatelé by obvykle přistupovali k webu pomocí stejného prohlížeče a vysokorychlostního připojení LAN. Je vhodné zapouzdřit vlastnosti těchto dvou různých skupin uživatelů v různých situacích. Každý scénář může obsahovat typ virtuálního uživatele. V takovém případě můžete provést do scénáře zátěžového testu představovat virtuální zákazníky a jiný scénář provádět představovat virtuální interní uživatele webu.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="scenario-components"></a>Součásti scénáře

Všechny možnosti počáteční konfigurace a nastavení zadejte, když vytvoříte zátěžový test, můžete změnit později v **editoru zátěžového testu**. Můžete také přidat nové scénáře, parametrů spuštění a sady čítačů k zátěžovému testu.

![Scénáře testování zatížení](../test/media/loadtesteditinscenarios.png)

Scénáře obsahují následující součásti:

|Termín|Definice|
|-|-|
|Poměr prohlížečů|Simuluje, že virtuální uživatelé přístup k webu prostřednictvím různých webových prohlížečů.|
|Vzor zatížení|Určuje počet virtuálních uživatelů, kteří jsou aktivní během testu zatížení a rychlost spouštění nových uživatelů. Příklad: krok, "konstantně" a cílově zaměřeného vzoru zátížení.|
|Model poměru testů|Určuje pravděpodobnost, že virtuální uživatel spustí daný test ve scénáři testu zatížení. Příklad: 20 % šance spustit TestA a 80 % šance spustit TestB. Model kombinace testů by měl odrážet cíle vašeho testu pro konkrétní scénář.|
|Poměr testů|Kombinace testů je výběr webového výkonu a testy jednotek, které tvoří scénáře a distribuce těchto testů.|
|Poměr sítí|Simuluje, že virtuální uživatelé přístup k webu prostřednictvím různých síťových připojení. Mix sítě nabízí možnosti, které zahrnují sítě LAN, kabelový modem a další možnosti.|

Má scénář několik dalších vlastností, které lze upravit pomocí **editoru zátěžových testů**. Další informace najdete v tématu [vlastnosti scénáře zátěžového testu](../test/load-test-scenario-properties.md).

## <a name="tasks"></a>Úkoly

|Úlohy|Související témata|
|-|-----------------------|
|**Přidáte pozastavení umělé lidské interakce ve vašem scénáři:** Doby uvažování se používají pro simulaci lidského chování, které způsobuje, že lidé mezi interakcemi s webem čekat. Doby uvažování se vyskytují mezi požadavky v testu výkonnosti webu a mezi testovacími iteracemi v případě zkušebního scénáře. Použití času přemýšlení v testu zatížení může být užitečné při vytváření přesnější simulace zatížení.|-   [Úpravy dob uvažování pro simulaci prodlev při zásahem ze strany webové stránky](../test/edit-think-times-in-load-test-scenarios.md)|
|**Zadejte počet virtuálních uživatelů pro váš scénář:** Můžete nakonfigurovat vlastnosti vzorku zatížení k určení, jak je upraveno simulované uživatelské zatížení během zkušební zatížení. Získat tři předdefinované načtené vzorky: Konstanta, krok a cílově zaměřeného vzoru zátížení. Vyberete vzorek zatížení a upravíte vlastnosti odpovídající úrovni pro vaše cíle zátěžového testu.|-   [Úpravy vzorů zatížení pro model aktivity virtuálního uživatele](../test/edit-load-patterns-to-model-virtual-user-activities.md)|
|**Konfigurace pravděpodobnosti spuštění testu ve scénáři virtuálním uživatelem:** Můžete použít kombinaci testů, která určuje pravděpodobnost, že virtuální uživatel spustí daný test ve scénáři testu zatížení. To umožňuje simulovat zatížení více realisticky. Namísto toho, aby pouze jeden pracovní postup prostřednictvím aplikace, může mít několik pracovních postupů, což je užší jak koncoví uživatelé pracují s vašimi aplikacemi.|-   [Úpravy modelů kombinací testů](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md)|
|**Přidání nebo odebrání webového výkonu nebo Jednotkový test do scénáře zátěžového testu:** Můžete přidat nebo odebrat test webového výkonu nebo Jednotkový ze zátěžového testu ve scénáři. Zátěžový test obsahuje jeden nebo více scénářů, z nichž každý obsahuje jeden nebo více výkonu nebo jednotkových testů webu.|-   [Upravit poměr testů](../test/edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario.md)|
|**Konfigurace požadované kombinace sítě pro váš scénář:** Pomocí kombinace sítě, můžete simulovat zatížení sítě více realisticky v případě zkušebního scénáře. Zatížení je generováno pomocí heterogenní kombinace typů sítí místo jednoho jediného typu sítě. Můžete vytvořit užší odhad jak koncoví uživatelé pracují s vašimi aplikacemi. Model mix sítě by měl odrážet cíle tohoto scénáře.|-   [Určení typů virtuálních sítí](../test/specify-virtual-network-types-in-a-load-test-scenario.md)|
|**Vyberte vhodnou kombinaci prohlížeče webu pro váš scénář:** Pomocí prohlížeče kombinace, můžete simulovat webovou zátěž více realisticky v případě zkušebního scénáře. Zatížení je generováno pomocí heterogenní kombinace prohlížečů místo jednoho jediného prohlížeče. Můžete vytvořit užší odhad prohlížečů, které budou použity s vašimi aplikacemi.|-   [Určení typů webových prohlížečů](../test/edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario.md)|
|**Konfigurace nastavení iterace testu pro váš scénář:** Konfigurace nastavení iterace testu pomocí editoru zátěžového testu a okna Vlastnosti scénáře zátěžového testu můžete upravit. Ve výchozím nastavení scénář nastavit pomocí žádné maximální testovací iterace. Volitelně můžete nakonfigurovat maximální počet iterací ve scénáři a délkou prodlevy mezi nimi.|-   [Konfigurace iterací testů ve scénářích](../test/configure-test-iterations-in-a-load-test-scenario.md)|
|**Konfigurace nastavení zpoždění pro váš scénář:** Použití **editoru zátěžového testu** a **vlastnosti** můžete nastavit zpoždění před zahájením scénáře v zátěžovém testu. Příkladem, kdy je vhodné použít **zpoždění spuštění** vlastnost je, pokud potřebujete jeden scénář pro zahájení výroby položek, které jiný scénář spotřebovává. Můžete pozdržet náročnou situaci povolení výrobního scénáře k naplnění nějaká data.|-   [Zpoždění pro spuštění scénáře Configureng](../test/configure-scenario-start-delays.md)|
|**Určete vzdálené počítače použít ve scénáři zátěžového testu:** Po vytvoření zátěžového testu můžete upravit vlastnosti vašeho scénáře zkušebního zatížení k označení, které testovací agenty, které chcete zahrnout. Další informace najdete v tématu [testovací kontrolery a testovací agenty](configure-test-agents-and-controllers-for-load-tests.md).|-   [Jak: Určení testovacích agentů k použití](../test/how-to-specify-test-agents-to-use-in-load-test-scenarios.md)|

## <a name="see-also"></a>Viz také:

- [Úpravy zátěžových testů](../test/edit-load-tests.md)
- [Vlastnosti scénáře zátěžového testu](../test/load-test-scenario-properties.md)