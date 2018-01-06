---
title: "Zápis testů částí pro knihovny DLL C++ v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 84575412-1de7-4e53-811d-ae035eb21d13
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ac5389640c486d5b886454c15dc0e979c0683caf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="write-unit-tests-for-c-dlls-in-visual-studio"></a>Zápis testů částí pro knihovny DLL C++ v sadě Visual Studio

 K testování kódu knihovny DLL, v závislosti na tom, jestli exportuje funkce, které chcete testovat několika způsoby. Vyberte jednu z následujících způsobů:  
  
 **Testování částí volat jenom funkce, které byly exportovány z knihovny DLL:**  
 Přidat samostatné testovacího projektu, jak je popsáno v [zápis testování částí pro C/C++](writing-unit-tests-for-c-cpp.md). K testovacímu projektu přidejte odkaz na projekt knihovny DLL.  
  
 Přejděte na postup [k odkazování exportovaných funkcí z projektu knihovny DLL](#projectRef).  
  
 **Jako soubor .exe je sestavena knihovny DLL:**  
 Přidáte samostatné testovacího projektu. Propojte objekt výstupní soubor.  
  
 Přejděte na postup [propojení testy na objekt nebo knihovna soubory](#objectRef).  
  
 **Jednotky testy volat třetí funkce, které nejsou exportována z knihovny DLL a knihovny DLL se dají vytvářet jako statické knihovny:**  
 Změňte projektu knihovny DLL tak, aby je kompilováno do souboru LIB. Přidáte samostatné testovací projekt, který odkazuje na projekt v rámci testu.  
  
 Tento přístup má výhodu povolení testy používat jiný exportovat členy, ale při tom zachovat testy v samostatných projektu.  
  
 Přejděte na postup [změnit knihovnu DLL na statickou knihovnu](#staticLink).  
  
 **Testování částí musí volat třetí funkce, které nejsou exportována a kód musí být vytvořená jako dynamická knihovna (DLL):**  
 Přidání testů jednotek v projektu stejný jako kód produktu.  
  
 Přejděte na postup [přidání testů jednotek ve stejném projektu](#sameProject).  
  
## <a name="creating-the-tests"></a>Vytváření testů  
  
###  <a name="staticLink"></a>Chcete-li změnit knihovnu DLL do statické knihovny  
  
-   Pokud testy musí používat členy, kteří nejsou exportované sadou projektu knihovny DLL a sestavení projektu testovaného jako dynamické knihovny, zvažte jeho převodem na statické knihovny.  
  
    1.  V **Průzkumníku řešení**, v místní nabídce projektu testovaného, zvolte **vlastnosti**. Otevře se okno Vlastnosti projektu.  
  
    2.  Zvolte **vlastnosti konfigurace | Obecné**.  
  
    3.  Nastavit **typ konfigurace** k **statické knihovny (LIB)**.  
  
 Pokračujte postupem uvedeným [propojení testy na objekt nebo knihovna soubory](#objectRef).  
  
###  <a name="projectRef"></a>Chcete-li exportované funkce DLL z testovacího projektu  
  
-   Pokud projektu knihovny DLL exportuje funkce, které chcete testovat, můžete přidat odkaz na projekt kódu z testovacího projektu.  
  
    1.  Vytvoření projektu testování částí nativní.  
  
        1.  Na **soubor** nabídce zvolte **nový | Projekt | Visual C++, testovací | Projektu testování částí C++**.  
  
    2.  V **Průzkumníku řešení**, v místní nabídce testovacího projektu, zvolte **odkazy**. Otevře se okno Vlastnosti projektu.  
  
    3.  Vyberte **společných vlastností | Architektura a odkazy na**a potom zvolte **přidat nový odkaz** tlačítko.  
  
    4.  Vyberte **projekty**a potom projekt, který má být testována.  
  
         Vyberte **přidat** tlačítko.  
  
    5.  Ve vlastnostech k testovacímu projektu přidejte do adresáře Include umístění projektu v rámci testu.  
  
         Zvolte **vlastnosti konfigurace | Adresáře VC ++ | Zahrnout adresáře**.  
  
         Zvolte **upravit**a poté přidejte adresáři záhlaví projektu v rámci testu.  
  
 Přejděte na [zápis testů částí](#addTests).  
  
###  <a name="objectRef"></a>Propojení testy na objekt nebo knihovna soubory  
  
-   Pokud knihovnu DLL neexportuje funkce, které chcete testovat, můžete přidat výstup **.obj** nebo **.lib** soubor závislosti testovacího projektu.  
  
    1.  Vytvoření projektu testování částí nativní.  
  
        1.  Na **soubor** nabídce zvolte **nový | Projekt | Visual C++ | Test | Projektu testování částí nativní**.  
  
    2.  V **Průzkumníku řešení**, v místní nabídce testovacího projektu, zvolte **vlastnosti**.  
  
    3.  Zvolte **vlastnosti konfigurace | Linkeru | Vstup | Další závislosti**.  
  
         Zvolte **upravit**a přidejte názvy **.obj** nebo **.lib** soubory. Nepoužívejte názvy úplnou cestu.  
  
    4.  Zvolte **vlastnosti konfigurace | Linkeru | Obecné | Další knihovny adresáře**.  
  
         Zvolte **upravit**a přidejte cestu k adresáři **.obj** nebo **.lib** soubory. Cesta je obvykle ve složce sestavení projektu v rámci testu.  
  
    5.  Zvolte **vlastnosti konfigurace | Adresáře VC ++ | Zahrnout adresáře**.  
  
         Zvolte **upravit**a poté přidejte adresáři záhlaví projektu v rámci testu.  
  
 Přejděte na [zápis testů částí](#addTests).  
  
###  <a name="sameProject"></a>Chcete-li přidat ve stejném projektu testování částí  
  
1.  Změnit vlastnosti projektu kódu produktu zahrnuje hlavičky a soubory knihovny, které jsou požadovány pro testování jednotky.  
  
    1.  V **Průzkumníku**, místní nabídky projektu testovaného, vyberte možnost Vlastnosti. Otevře se okno Vlastnosti projektu.  
  
    2.  Zvolte **vlastnosti konfigurace | Adresáře VC ++**.  
  
    3.  Úpravy adresáře Include a Library:  
  
        |||  
        |-|-|  
        |**Zahrnout adresáře** | **$(VCInstallDir)UnitTest\include;$(IncludePath)**|  
        |**Adresáře knihovny** | **$(VCInstallDir)UnitTest\lib;$(LibraryPath)**|  
  
2.  Přidejte soubor testování částí C++:  
  
    -   V **Průzkumníku řešení**, místní nabídky projektu, zvolte **přidat | Nová položka | Testování částí C++**.  
  
 Přejděte na [zápis testů částí](#addTests).  
  
##  <a name="addTests"></a>Zápis testů částí  
  
1.  Do každého souboru kód testu jednotek přidat `#include` příkaz pro záhlaví projektu v rámci testu.  
  
2.  Přidáte test třídy a metody k souborům kód testu jednotek. Příklad:  
  
    ```cpp  
    #include "stdafx.h"  
    #include "CppUnitTest.h"  
    #include "MyProjectUnderTest.h"  
    using namespace Microsoft::VisualStudio::CppUnitTestFramework;  
    namespace MyTest  
    {  
      TEST_CLASS(MyTests)  
      {  
      public:  
          TEST_METHOD(MyTestMethod)  
          {  
              Assert::AreEqual(MyProject::Multiply(2,3), 6);  
          }  
      };  
    }  
    ```  
  
## <a name="run-the-tests"></a>Spouštění testů  
  
1.  Na **Test** nabídce zvolte **Windows | Testování Explorer**.  
2. Pokud všechny testy nejsou zobrazeny v okně, sestavte projekt test kliknutím pravým tlačítkem na jeho uzlu v **Průzkumníku řešení** a výběr **sestavení** nebo **znovu sestavit**.
  
2.  V Průzkumníku testu zvolte **spustit všechny**, nebo vyberte konkrétní testy, kterou chcete spustit. Klikněte pravým tlačítkem myši na test pro další možnosti, včetně spuštění v režimu ladění se zarážkami povolena.
  
## <a name="see-also"></a>Viz také
[Rychlý začátek: Vývoj řízený testy s použitím Průzkumníka testů](../test/quick-start-test-driven-development-with-test-explorer.md)

  
## <a name="see-also"></a>Viz také  
 [Zápis testů jednotek pro C/C++](writing-unit-tests-for-c-cpp.md)   
 [Referenční dokumentace rozhraní API atributu Microsoft.VisualStudio.TestTools.CppUnitTestFramework](../test/microsoft-visualstudio-testtools-cppunittestframework-api-reference.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)   
 [Návod: Vytvoření a použití dynamické knihovny (C++)](/cpp/build/walkthrough-creating-and-using-a-dynamic-link-library-cpp)   
 [Import a export](/cpp/build/importing-and-exporting)
