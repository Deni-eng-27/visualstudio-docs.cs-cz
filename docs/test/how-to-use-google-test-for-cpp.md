---
title: Jak používat testovací Google jazyka C++ v sadě Visual Studio
ms.date: 11/04/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: mblome
manager: douge
ms.workload:
- cplusplus
author: mikeblome
ms.openlocfilehash: c5e86884f017aa2fc490eb926485c567742b8647
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-google-test-for-c-in-visual-studio"></a>Jak používat testovací Google jazyka C++ v sadě Visual Studio
V **Visual Studio 2017 verze 15,5** a novější, je Google Test integrována do prostředí Visual Studio IDE jako součást výchozí **Develoment plochy s jazykem C++** zatížení. Pokud chcete ověřit, že je nainstalovaný na počítači, spusťte instalační program Visual Studio a najděte Google Test v seznamu součástí úlohy:

![Nainstalujte Google Test](media/cpp-google-component.png "nainstalovat Google Test pro C++")

## <a name="add-a-google-test-project-to-the-solution"></a>Do řešení přidat testovacího projektu Google
1. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel řešení a zvolte **přidat | Nový projekt**.
2. V levém podokně vyberte **Visual C++ | Test** a potom zvolte **testovacího projektu Google** v prostředním podokně.
3. Zadejte název testovacího projektu a klikněte na tlačítko **OK**.

![Nový projekt Test Google](media/cpp-gtest-new-project.png "přidat nový projekt Test Google")

## <a name="configure-the-test-project"></a>Konfigurace testovacího projektu
V **testovací konfigurace projektu** dialog, který se zobrazí, můžete zvolit projektu, kterou chcete otestovat. Když zvolíte projektu, Visual Studio přidá odkaz na vybranou projekt. Pokud si zvolíte žádný projekt, budete muset ručně přidáte odkazy na projekty, které chcete otestovat. Při výběru mezi statickým a dynamickým propojení s testovací Google binární soubory, jaké jsou požadavky jsou stejné jako pro žádné program C++. Další informace najdete v tématu [knihovny DLL v jazyce Visual C++](/cpp/build/dlls-in-visual-cpp).

 ![Konfigurace projektu Google Test](media/cpp-gtest-config.png "konfigurace projektu Google testu")

## <a name="set-additional-options"></a>Další možnosti pro sadu
Z hlavní nabídky zvolte **nástroje | Možnosti | Testování adaptéru pro Google Test** můžete nastavit další možnosti. Najdete v dokumentaci Google testovací Další informace o těchto nastavení.

 ![Nastavení projektu Google Test](media/cpp-gtest-settings.png "nastavení testovacího projektu Google")

## <a name="add-include-directives"></a>Přidání direktivy začlenění
Testovací soubor, přidejte všechny potřeby `#include` direktivy chcete zviditelnit vašeho programu typy a funkce pro testovací kód. Tento program je obvykle jednu úroveň v hierarchii složek. Pokud zadáte `#include "../"` okno technologie IntelliSense se zobrazí a umožňuje vybrat úplnou cestu k souboru záhlaví.

![Přidat # direktivy include](media/cpp-gtest-includes.png "přidat zahrnují direktivy pro test souboru")

## <a name="write-and-run-tests"></a>Zápis a spouštění testů
Nyní jste připraveni k zápisu a testy Google. Najdete v článku [Úvod do testovací Google](https://github.com/google/googletest/blob/master/googletest/docs/Primer.md) informace o testovací makra. V tématu [spouštění testů jednotek pomocí Průzkumníka testů](run-unit-tests-with-test-explorer.md) informace o zjišťování, spuštění a seskupení testů pomocí **Průzkumníka testů**.

## <a name="see-also"></a>Viz také
[Zápis testů částí pro C/C++](writing-unit-tests-for-c-cpp.md)










