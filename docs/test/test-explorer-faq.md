---
title: "Testování Explorer – nejčastější dotazy | Microsoft Docs"
ms.date: 1/15/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Test Explorer
- Test window
- Visual Studio Test Explorer
- summary line
- unit tests
- Test Explorer FAQ
ms.author: kehavens
ms.workload:
- multiple
author: kendrahavens
manager: ghogen
ms.openlocfilehash: db3cf85576e6c46aca14897f7244cd0f56d8d5c2
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2018
---
# <a name="visual-studio-test-explorer-faq"></a>Visual Studio Průzkumníka testů – nejčastější dotazy

## <a name="test-discovery"></a>Test zjišťování

### <a name="1-the-test-explorer-is-not-discovering-my-tests-that-have-theories-custom-adapters-custom-traits-use-ifdefs-or-are-dynamically-defined-how-can-i-discover-these-tests"></a>1. Průzkumníka testů není zjišťování Moje testů, které teorií, vlastní adaptéry, vlastní vlastnosti, použijte #ifdefs nebo jsou definovány dynamicky. Jak mohou zjistit tyto testy?

  Sestavení projektu a zajistěte, aby na základě sestavení zjišťování zapnutý **nástroje > Možnosti > Test**.

  [Test zjišťování reálném čase](https://go.microsoft.com/fwlink/?linkid=862824), který je při zjišťování testů založené na zdroj nelze zjistit testy, které používají teorií, vlastní adaptéry, vlastní vlastnosti `#ifdef` příkazy, nebo které jsou definovány dynamicky jiným způsobem. Sestavení je vyžadována pro tyto testy mají být zjišťované přesně. V 15.6 verze Preview sestavení na základě zjišťování (tradiční discoverer) se spustí až po sestavení. To znamená, že Test zjištění reálném čase zjistí tolik testy, jak můžete při úpravách a zjišťování na základě sestavení umožňuje teorií (nebo všechny dynamicky definované testy), než se objeví po sestavení. Test zjišťování reálném čase zlepšuje odezvu, ale nepřesahuje umožňují získat úplné a přesné výsledky po sestavení.

### <a name="2-what-does-the--plus-symbol-that-appears-in-the-top-line-of-test-explorer-mean"></a>2. Jaké '+' (symbol, který se zobrazí v horní řádek Průzkumníka testů střední plus)?

  '+' (A) symbol označuje další testy mohou být zjištěny po sestavení, pokud je zapnutá zjišťování na základě sestavení. Pokud dynamicky definované se objeví, že testy jsou zjištěna v projektu.

  ![Souhrn řádku symbol plus](media/testex-plussymbol.png)

### <a name="3-assembly-based-discovery-is-no-longer-working-for-my-project-how-do-i-turn-it-back-on"></a>3. Zjišťování na základě sestavení již nefunguje pro moje projekt. Jak lze zapnout ji zpět na?

  Přejděte na **nástroje > Možnosti > Test** a zaškrtněte políčko pro **kromě zjistit testy vytvořené ze sestavení po sestavení.**

  ![Možnosti založené na sestavení](media/testex-toolsoptions.png)

### <a name="4-tests-now-appear-in-test-explorer-while-i-type-without-having-to-build-my-project-what-changed"></a>4. Testy se teď zobrazují v Průzkumníka testů při psaní, aniž by museli sestavení projektu. Co se změnilo?

  Tato funkce je volána [reálném čase testu zjišťování](https://go.microsoft.com/fwlink/?linkid=862824). Analyzátor Roslyn používá ke zjištění testy a naplnit Průzkumníka testů v reálném čase, aniž by bylo potřeba sestavení projektu. Další informace o chování testu zjišťování pro dynamicky definované testy například teorií nebo vlastní vlastnosti najdete v části Nejčastější dotazy k č. 1.

### <a name="5-what-languages-and-test-frameworks-can-use-real-time-test-discovery"></a>5. Jaké jazyků a rozhraní test můžete použít zjišťování testování reálném čase?

  [Test zjišťování reálném čase](https://go.microsoft.com/fwlink/?linkid=862824) funguje pouze pro spravované jazyky (C# a Visual Basic), protože je sestaven pomocí Roslyn kompilátoru. Prozatím se reálném čase testu zjišťování funguje výhradně u xUnit, NUnit a Mstestu architektury.

## <a name="features"></a>Funkce

### <a name="how-can-i-turn-on-feature-flags-to-try-out-new-testing-features"></a>Jak lze zapnout funkci příznaky vyzkoušet nové funkce testování?

Funkce příznaky se používají pro odeslání experimentální nebo nedokončených součástí produktu avid uživatelům, kteří chtěli váš názor dříve, než funkce dodáte oficiálně. Může se destabilizovat prostředí IDE. Doporučujeme používat pouze v bezpečném vývojových prostředí, jako jsou virtuální počítače. Funkce příznaky jsou vždy použijte vaše vlastníte rizikového nastavení. Můžete zapnout s povolenými experimentálními funkcemi [rozšíření funkce příznaky](https://marketplace.visualstudio.com/items?itemName=PaulHarrington.FeatureFlagsExtension), nebo prostřednictvím příkazového řádku vývojáře.

![Příznak rozšíření funkce](media/testex-featureflag.png)

Chcete-li zapnout funkci příznak prostřednictvím příkazového řádku vývojáře Visual Studia, použijte následující příkaz. Změňte cestu k nainstalovaným Visual Studio v počítači a změňte klíč registru pro příznak požadované funkce.

```shell
vsregedit set “C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise” HKLM FeatureFlags\TestingTools\UnitTesting\HierarchyView Value dword 1
```

> [!NOTE]
> Příznak pomocí stejného příkazu můžete vypnout pomocí hodnoty 0 namísto 1 po dword.
  
## <a name="see-also"></a>Viz také

<xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=fullName>  
[Vytváření a spouštění testování částí pro existující kód](http://msdn.microsoft.com/e8370b93-085b-41c9-8dec-655bd886f173)
[jednotky Otestujte svůj kód](unit-test-your-code.md)
[Live nejčastější dotazy k testování částí](live-unit-testing-faq.md)
