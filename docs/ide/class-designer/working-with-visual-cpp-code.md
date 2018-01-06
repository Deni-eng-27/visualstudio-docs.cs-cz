---
title: "Práce s kódem jazyka Visual C++ (návrhář tříd) | Microsoft Docs"
ms.custom: 
ms.date: 06/21/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.classdesigner.cpplimitation
helpviewer_keywords:
- Visual C++, Class Designer
- Class Designer, Visual C++ support
- Class Designer, limitations
- Class Designer, tasks in Visual C++
- Visual C++, class diagrams
- C++, class diagrams
- C++, Class Designer
ms.assetid: f5b40921-2ef7-4de0-b595-45b44c79ffa6
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e0861f6e97ea5cc2321befce8cdf6c460c7ec6cc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="working-with-visual-c-code-class-designer"></a>Práce s kódem jazyka Visual C++ (návrhář tříd)
Návrhář tříd zobrazí návrhové ploše názvem *diagramu tříd* , který poskytuje vizuální reprezentace elementy kódu v projektu. Diagramy tříd můžete použít k návrhu a vizualizovat třídami a ostatními typy v projektu.  

Návrhář tříd podporuje následující elementy kódu C++:  

-   Třídy (podobá obrazce spravované třídy, s tím rozdílem, že může mít více vztahů dědičnost)  

-   Anonymní – třída (zobrazí se zobrazení tříd vygenerovaný název anonymního typu)  

-   Šablony třídy  

-   Struktura  

-   Výčet  

-   Makro (zobrazí se po zpracování zobrazení makra)  

-   Definice TypeDef  

> [!NOTE]
>  To však není stejný jako diagramu tříd UML, který můžete vytvořit v projektu modelování. Další informace najdete v tématu [diagramů tříd UML: referenční dokumentace](../../modeling/uml-class-diagrams-reference.md).  

## <a name="troubleshooting-type-resolution-and-display-issues"></a>Řešení potíží s typu řešení a problémy zobrazení  

### <a name="location-of-source-files"></a>Umístění zdrojových souborů  
Návrhář tříd není sledování od umístění zdrojových souborů. Proto pokud změnit strukturu projektu nebo přesunout zdrojové soubory v projektu, návrhář tříd můžete ztrátě informací o typu (zejména typ zdroje typedef, základní třídy nebo přidružení typů). Může dojít chybě, jako **třída Návrhář nemůže zobrazit tento typ**. Pokud tak učiníte, přetáhněte upraveném nebo přemístěné zdrojový kód na diagramu tříd znovu a znovu ji zobrazit.  

### <a name="update-and-performance-issues"></a>Aktualizace a problémy s výkonem  
Pro projekty Visual C++ může trvat 30 – 60 sekund pro změnu v zdrojový soubor, který se zobrazí v diagramu tříd. Toto zpoždění může také způsobit návrhář tříd, které má být vyvolána chyba **ve výběru nebyly nalezeny žádné typy**. Pokud narazíte na chyby, jako je tato, klikněte na tlačítko **zrušit** v chybové zprávě a čekání pro tento element kódu zobrazit v zobrazení tříd. Až to uděláte, návrhář tříd by mohli zobrazit typu.  

Pokud diagramu tříd neaktualizuje se změny provedené v kódu, možná budete muset diagram zavřít a znovu ho otevřete.  

### <a name="type-resolution-issues"></a>Typ řešení problémů  
Návrhář tříd nemusí být schopen převést typy z následujících důvodů:  
  
-   Typ je v projektu nebo sestavení, které není na něj odkazovat z projektu, který obsahuje diagramu tříd. Chcete-li opravit tuto chybu, přidejte odkaz na projekt nebo sestavení, které obsahuje typ. Další informace najdete v tématu [Správa odkazů v projektu](../managing-references-in-a-project.md).  
  
-   Typ není ve správném oboru, takže ji nelze najít návrhář tříd. Zkontrolujte, že kód není chybějící `using`, `imports`, nebo `#include` příkaz. Ujistěte se, že nebyly přesunut typ (nebo souvisejícího typu) mimo obor názvů, ve kterém byl původně nachází také.  

-   Typ neexistuje nebo byla změněna na komentář. A opravte tuto chybu, ujistěte se, že nejsou označené jako komentář nebo odstranit typ.  

-   Typ nachází v knihovně odkazuje #import – direktiva. Možných řešení je ručně přidat generovaný kód (soubor .tlh) #include – direktiva do záhlaví souboru.  

Chyba se nejpravděpodobněji najdete v části řešení problému typ je **kód nebyl nalezen pro jeden nebo více obrazců v diagramu tříd '\<element >'**. Tato chybová zpráva nemusí znamenat, že váš kód došlo k chybě. Znamená, že pouze tento návrhář tříd se nepodařilo zobrazení vašeho kódu. Zkuste následující míry.  

-   Zkontrolujte, zda typu. Zajistěte, aby mít není neúmyslně komentované a odstranit zdrojový kód.  

-   Zkontrolujte, jestli návrhář tříd podporuje typ, který jste zadali. V tématu [omezení pro elementy kódu C++](#limitations).  

-   Došlo k pokusu o vyřešení typu. Typ může být v projektu nebo sestavení, které není na něj odkazovat z projektu, který obsahuje diagramu tříd. Chcete-li opravit tuto chybu, přidejte odkaz na projekt nebo sestavení, které obsahuje typ. Další informace najdete v tématu [Správa odkazů v projektu](../managing-references-in-a-project.md).  

-   Ujistěte se, že typ je ve správném oboru, aby ji mohli najít návrhář tříd. Ujistěte se, že kód není chybějící `using`, `imports`, nebo `#include` příkaz. Ujistěte se, že nebyly přesunut typ (nebo souvisejícího typu) mimo obor názvů, ve kterém byl původně nachází také.  

### <a name="troubleshooting-other-error-messages"></a>Řešení potíží s další chybové zprávy  
Pomoc při řešení potíží chyby a upozornění můžete najít ve veřejné fórech Microsoft Developer Network (MSDN). Najdete v článku [návrháře fórum sady Visual Studio – třída](http://go.microsoft.com/fwlink/?linkid=160754).  

##  <a name="limitations"></a>Omezení pro elementy kódu C++  

-   Když je načten projektu Visual C++, návrhář tříd funguje způsobem, jen pro čtení. Můžete změnit diagramu tříd, ale nemůže uložit změny z diagramu tříd zpátky do zdrojového kódu.  

-   Návrhář tříd podporuje pouze nativní sémantiku C++. Pro projekty Visual C++, které jsou zkompilovány do spravovaného kódu návrhář tříd pouze vizualizovat elementy kódu, které jsou nativní typy. Proto můžete přidat diagramu tříd do projektu, ale návrhář tříd nebude možné vizualizovat elementy, ve kterém `IsManaged` je nastavena na `true` (to znamená, typů hodnot a odkazové typy).  

-   Návrhář tříd pro projekty Visual C++, čte pouze definici typu. Předpokládejme například, že můžete definovat typu v souboru hlavičky () a její členy v souboru implementace (sada). Pokud vyvolání "Zobrazení diagramu tříd" na soubor implementace (sada), zobrazí návrhář tříd nic. Jako další příklad – Pokud vyvolání "Zobrazení diagramu tříd" na sada souboru, který používá `#include` příkaz zahrnout další soubory, ale neobsahuje žádné skutečné – třída definice, zobrazí nic návrhář tříd znovu.  

-   Soubory IDL (.idl), které definují rozhraní COM a knihovny typů, se nezobrazují v diagramech, pokud nejsou zkompilovány do nativního kódu C++.  

-   Návrhář tříd se nepodporuje, globální funkce a proměnné.  

-   Návrhář tříd nepodporuje sjednocení. Toto je zvláštní druh třída, ve které je paměť přidělená pouze množství potřebné pro Evropské unie největší datový člen.  

-   Návrhář tříd nezobrazí základní datové typy, jako `int` a `char`.  

-   Návrhář tříd nezobrazuje typy, které jsou definovány mimo aktuální projekt, pokud projekt nemá správné odkazy na tyto typy.  

-   Návrhář tříd můžete zobrazit vnořené typy, ale není vztahy mezi vnořené typy a dalších typů.  

-   Třída Návrhář je nemůže zobrazit typy, které jsou neplatné nebo které jsou odvozeny od typu void.  

## <a name="see-also"></a>Viz také
[Navrhování a zobrazování tříd a typů](designing-and-viewing-classes-and-types.md)   
[Práce s diagramy tříd](working-with-class-diagrams.md)   
[Navrhování tříd a typů](designing-classes-and-types.md)   
[Další informace o chybách návrháře tříd](additional-information-about-errors.md)   
[Třídy jazyka Visual C++ v Návrháři tříd](visual-cpp-classes.md)   
[Struktury jazyka Visual C++ v Návrháři tříd](visual-cpp-structures.md)   
[Výčty jazyka Visual C++ v Návrháři tříd](visual-cpp-enumerations.md)   
[Definice Typedefs jazyka Visual C++ v Návrháři tříd](visual-cpp-typedefs.md)
