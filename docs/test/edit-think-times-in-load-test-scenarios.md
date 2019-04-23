---
title: Dob uvažování pro zátěžové testování
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, think times
- load tests, adding delays
- load tests, changing think times
ms.assetid: 8e03bee5-ab7b-4b40-9497-9dbe91ccb90e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: e19e1cb4f9b49c40923d96b177ceb4d6c31b746f
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60090017"
---
# <a name="edit-think-times-to-simulate-website-human-interaction-delays-in-load-tests-scenarios"></a>Úpravy dob uvažování pro simulaci prodlev při zásahem ze strany webové stránky ve scénářích zátěžových testů

Doby uvažování se používají pro simulaci lidského chování, které způsobuje, že lidé mezi interakcemi s webem čekat. Doby uvažování se vyskytují mezi požadavky v testu výkonnosti webu a mezi testovacími iteracemi v případě zkušebního scénáře. Použití času přemýšlení v testu zatížení může být užitečné při vytváření přesnější simulace zatížení. Můžete změnit, zda testy zvažte dobu používat nebo ignorovat v zatížení. Můžete změnit, zda zvažte časy se používají v zatížení testy v **editoru zátěžového testu**.

*Profil uvažování* je nastavení, která se použije pro scénář v rámci zátěžového testu. Nastavení určuje, zda zvažte časy jsou uloženy v jednotlivých webových testů výkonu se používají během zátěžového testu. Pokud chcete použít v některé testy webového výkonu časy přemýšlení, ale v jiných nesmí umístit je do různých scénářů. Další informace o scénářích najdete v tématu [úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md).

Na začátku nastavit, jestli použít čas přemýšlení v zátěžových testech při vytváření zátěžovému testu pomocí **nového Průvodce zátěžovým testem**. Další informace najdete v tématu [úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md).

**Myslíte, že profil** možnosti jsou popsány v následujícím seznamu:

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

**Off**

Doby uvažování se ignorují. Toto nastavení použijte, pokud chcete generovat maximálního zatížení silně zdůraznit, webový server. Nepoužívejte ho, když se pokoušíte vytvořit víc odpovídají realitě uživatelské interakce s webovým serverem.

**On**

Doby uvažování se používají, přesně tak, jak byly zaznamenány v testu výkonnosti webu. Simuluje spouštění testů výkonnosti webu, přesně tak, jak zaznamenána více uživatelů. Protože zátěžový test simuluje více uživatelů pomocí stejných myslíte, že čas vytvořit vzor zatížení nepřirozené synchronizovaných virtuálních uživatelů.

**Normální distribuce**

Doby uvažování se používá, ale měnit na normální křivky. Poskytuje více realistická simulace virtuálních uživatelů tím, že čas přemýšlení mezi požadavky mírně liší.

> [!NOTE]
> Úplný seznam vlastnosti scénáře zátěžového testu a jejich popis najdete v části [vlastnosti scénáře zátěžového testu](../test/load-test-scenario-properties.md).

## <a name="change-the-think-profile"></a>Změnit profil uvažování

### <a name="to-change-a-think-profile-in-a-load-test-scenario"></a>Chcete-li změnit profil uvažování nastaven ve scénáři zátěžového testu

1. Z webového výkonu a zatížení testovací projekt, otevřete zátěžový test.

2. V **editoru zátěžových testů**, vyberte uzel scénář, ve které chcete změnit **myslíte, že profil**. **Myslíte, že profil** se zobrazí **vlastnosti** okna. Stisknutím klávesy **F4** zobrazíte **vlastnosti** okna.

3. Změnit **myslíte, že profil** vlastnost **vlastnosti** okna.

4. Po dokončení změn vlastností zvolte **Uložit** na **souboru** nabídky. Můžete spustit zátěžový test pomocí nového profil uvažování nastaven.

## <a name="see-also"></a>Viz také:

- [Úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md)