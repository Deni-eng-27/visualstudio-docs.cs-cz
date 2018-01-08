---
title: "Návod: Analýza kódu C/C++ na výskyt závad | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- C/C++, code analysis
- code analysis, walkthroughs
- code, analyzing C/C++
- code analysis tool, walkthroughs
ms.assetid: eaee55b8-85fe-47c7-a489-9be0c46ae8af
caps.latest.revision: "35"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c95d03201fe9c84e01e83e7fd55bef83755337e7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-analyzing-cc-code-for-defects"></a>Návod: Analýza kódu C/C++ na výskyt závad
Tento návod ukazuje, jak analyzovat kódu C/C++ pro potenciální defekty kódu pomocí nástroje Analýza kódu pro kód C/C++.  
  
 V tomto návodu projděte proces pomocí analýzy kódu pro analýzu kódu C/C++ pro potenciální závad v kódu.  
  
 Bude proveďte následující kroky:  
  
-   Spuštění analýzy kódu v nativním kódu.  
  
-   Analýza kódu vadou upozornění.  
  
-   Zpracovávat upozornění za chybu.  
  
-   Přidání poznámek ke zdrojového kódu ke zlepšení analýza vadou kódu.  
  
## <a name="prerequisites"></a>Požadavky  
  
-   [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)]nebo [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)].  
  
-   Kopii [Demo-ukázka](../code-quality/demo-sample.md).  
  
-   Základní znalosti jazyka C/C++  
  
### <a name="to-run-code-defect-analysis-on-native-code"></a>Ke spuštění vadou analýza kódu v nativním kódu  
  
1.  Otevřete ukázku řešení v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
     Ukázkové řešení teď naplní **Průzkumníku řešení**.  
  
2.  Na **sestavení** nabídky, klikněte na tlačítko **znovu sestavit řešení**.  
  
     Řešení sestavení bez jakýchkoli chyb nebo upozornění.  
  
3.  V **Průzkumníku**, vyberte CodeDefects projekt.  
  
4.  Na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
     **Stránky vlastností CodeDefects** se zobrazí dialogové okno.  
  
5.  Klikněte na tlačítko **analýza kódu**.  
  
6.  Klikněte **povolit analýzy kódu pro C/C++ v sestavení** zaškrtávací políčko.  
  
7.  Znovu sestavte projekt CodeDefects.  
  
     Upozornění analýzy kódu se zobrazí v **seznam chyb**.  
  
### <a name="to-analyze-code-defect-warnings"></a>K analýze upozornění vadou kódu  
  
1.  Na **zobrazení** nabídky, klikněte na tlačítko **seznam chyb**.  
  
     V závislosti na vývojáře profil, který jste zvolili v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], možná budete muset přejděte na příkaz **ostatní okna** na **zobrazení** nabídce a pak klikněte na tlačítko **seznam chyb**.  
  
2.  V **seznam chyb**, dvakrát klikněte na následující upozornění:  
  
     upozornění C6230: implicitní přetypování mezi sémanticky různé typy: pomocí HRESULT v kontextu, logická hodnota.  
  
     Editor kódu zobrazí řádek, který způsobil upozornění ve funkci `bool``ProcessDomain()`. Toto upozornění určuje, že HRESULT je použit v příkazu 'if' kde je očekávána logickou.  
  
3.  Opravte toto upozornění pomocí makro bylo úspěšné. Váš kód by měl vypadat následující kód:  
  
    ```  
    if (SUCCEEDED (ReadUserAccount()) )  
    ```  
  
4.  V **seznam chyb**, dvakrát klikněte na následující upozornění:  
  
     upozornění C6282: nesprávné operátor: přiřazení konstantu v kontextu testu. Byl == určený?  
  
5.  Opravte toto upozornění testování rovnosti. Váš kód by měl vypadat podobně jako následující kód:  
  
    ```  
    if ((len == ACCOUNT_DOMAIN_LEN) || (g_userAccount[len] != '\\'))  
    ```  
  
### <a name="to-treat-warning-as-an-error"></a>Chcete-li upozornění považovat za chybu  
  
1.  V souboru Bug.cpp, přidejte následující `#pragma` příkaz na začátek souboru, který se má upozornění C6001 považovat za chybu:  
  
    ```  
    #pragma warning (error: 6001)  
    ```  
  
2.  Znovu sestavte projekt CodeDefects.  
  
     V **seznam chyb**, C6001 se zobrazí jako chyba.  
  
3.  Opravte chyby zbývající dva C6001 v **seznam chyb** podle inicializace `i` a `j` na hodnotu 0.  
  
4.  Znovu sestavte projekt CodeDefects.  
  
     Sestavení projektu bez žádná upozornění ani chyby.  
  
### <a name="to-correct-the-source-code-annotation-warnings-in-annotationc"></a>Chcete-li opravit upozornění zdrojového kódu poznámky v annotation.c  
  
1.  V Průzkumníku řešení vyberte projekt poznámky.  
  
2.  Na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
     **Stránky vlastností poznámky** se zobrazí dialogové okno.  
  
3.  Klikněte na tlačítko **analýza kódu**.  
  
4.  Vyberte **povolit analýzy kódu pro C/C++ v sestavení** zaškrtávací políčko.  
  
5.  Znovu sestavte projekt poznámky.  
  
6.  V **seznam chyb**, dvakrát klikněte na následující upozornění:  
  
     upozornění C6011: vyhodnocení ukazatele NULL 'newNode'.  
  
     Toto upozornění označuje selhání volající Zkontrolujte návratovou hodnotu. V tomto případě volání **AllocateNode** může vrátit hodnotu NULL (viz soubor hlaviček annotations.h pro funkce deklaraci pro AllocateNode).  
  
7.  Otevřete soubor annotations.cpp.  
  
8.  Chcete-li toto upozornění, použijte k testování návratovou hodnotu příkazem 'if'. Váš kód by měl vypadat následující kód:  
  
     `if (NULL != newNode)`  
  
     `{`  
  
     `newNode->data = value;`  
  
     `newNode->next = 0;`  
  
     `node->next = newNode;`  
  
     `}`  
  
9. Znovu sestavte projekt poznámky.  
  
     Sestavení projektu bez žádná upozornění ani chyby.  
  
### <a name="to-use-source-code-annotation"></a>Použití nástroje zdrojového kódu  
  
1.  Přidání poznámek ke formální parametry a vrátí hodnotu funkce `AddTail` pomocí předběžné a Post podmínky, jak je uvedeno v tomto příkladu:  
  
     `[returnvalue:SA_Post (Null=SA_Maybe)] LinkedList* AddTail`  
  
     `(`  
  
     `[SA_Pre(Null=SA_Maybe)] LinkedList* node,`  
  
     `int value`  
  
     `)`  
  
2.  Znovu sestavte projekt poznámky.  
  
3.  V **seznam chyb**, dvakrát klikněte na následující upozornění:  
  
     upozornění C6011: Při přesměrování NULOVÝ ukazatel 'uzlu'.  
  
     Toto upozornění označuje, že uzel předaný funkci může mít hodnotu null a označuje číslo řádku, kde byla vyvolána upozornění.  
  
4.  Chcete-li toto upozornění, použijte k testování návratovou hodnotu příkazem 'if'. Váš kód by měl vypadat následující kód:  
  
    ```  
    . . .  
    LinkedList *newNode = NULL;   
    if (NULL == node)  
    {  
         return NULL;  
        . . .  
    }  
    ```  
  
5.  Znovu sestavte projekt poznámky.  
  
     Sestavení projektu bez žádná upozornění ani chyby.  
  
## <a name="see-also"></a>Viz také  
 [Návod: Analýza spravovaného kódu na výskyt závad v kódu](../code-quality/walkthrough-analyzing-managed-code-for-code-defects.md)