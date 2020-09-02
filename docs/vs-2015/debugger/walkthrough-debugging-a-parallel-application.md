---
title: 'Návod: ladění paralelní aplikace | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, parallel tasks walkthrough
- parallel stacks toolwindow
- parallel tasks toolwindow
- parallel applications, debugging [C++]
- debugging, parallel applications
- parallel applications, debugging [Visual Basic]
- parallel applications, debugging [C#]
ms.assetid: 2820ac4c-c893-4d87-8c62-83981d561493
caps.latest.revision: 31
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ad496bb55bae8d9e08035408059e454430ab4e39
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "65705371"
---
# <a name="walkthrough-debugging-a-parallel-application"></a>Návod: Ladění paralelní aplikace
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tento návod ukazuje, jak použít **Paralelní úlohy** a okna **paralelních zásobníků** k ladění paralelní aplikace. Tato okna vám pomůžou pochopit a ověřit chování modulu runtime kódu, který používá [Task Parallel Library (TPL)](https://msdn.microsoft.com/library/b8f99f43-9104-45fd-9bff-385a20488a23) nebo [Concurrency Runtime](https://msdn.microsoft.com/library/874bc58f-8dce-483e-a3a1-4dcc9e52ed2c). Tento návod obsahuje vzorový kód, který obsahuje předdefinované zarážky. Po zalomení kódu návod ukazuje, jak použít **Paralelní úlohy** a okna **paralelní zásobníky** k její kontrole.  
  
 Tento návod učí tyto úlohy:  
  
- Jak zobrazit zásobníky volání všech vláken v jednom zobrazení.  
  
- Jak zobrazit seznam `System.Threading.Tasks.Task` instancí, které jsou vytvořeny ve vaší aplikaci.  
  
- Jak zobrazit skutečné zásobníky volání úkolů místo vláken.  
  
- Jak přejít na kód z okna **Paralelní úlohy** a **paralelní zásobníky**  
  
- Způsob, jakým se Windows vypořádat se škálováním prostřednictvím seskupení, lupy a dalších souvisejících funkcí.  
  
## <a name="prerequisites"></a>Předpoklady  
 Tento návod předpokládá, že je povolená **pouze můj kód** . V nabídce **nástroje** klikněte na položku **Možnosti**, rozbalte uzel **ladění** , vyberte možnost **Obecné**a poté vyberte možnost **Povolit pouze můj kód (pouze spravované)**. Pokud tuto funkci nenastavíte, můžete i nadále používat tento návod, ale výsledky se mohou lišit od ilustrací.  
  
## <a name="c-sample"></a>Ukázka jazyka C#  
 Použijete-li ukázku jazyka C#, tento návod také předpokládá, že je externí kód skrytý. Chcete-li přepnout, zda je zobrazen externí kód, klikněte pravým tlačítkem **myši na záhlaví tabulky v** okně **zásobník volání** a potom vyberte nebo zrušte zaškrtnutí **Zobrazit externí kód**. Pokud tuto funkci nenastavíte, můžete i nadále používat tento návod, ale výsledky se mohou lišit od ilustrací.  
  
## <a name="c-sample"></a>Ukázka C++  
 Použijete-li ukázku jazyka C++, můžete ignorovat odkazy na externí kód v tomto tématu. Externí kód se vztahuje pouze na ukázku C#.  
  
## <a name="illustrations"></a>Ilustrace  
 Ilustrace v tomto tématu zaznamenané na čtyřjádrovém počítači, na kterém je spuštěná ukázka jazyka C# I když můžete použít jiné konfigurace k dokončení tohoto Názorného postupu, ilustrace se mohou lišit od toho, co se zobrazuje v počítači.  
  
## <a name="creating-the-sample-project"></a>Vytvoření ukázkového projektu  
 Vzorový kód v tomto návodu je určen pro aplikaci, která nic nedělá. Cílem je pouze pochopit, jak používat okna nástrojů k ladění paralelní aplikace.  
  
#### <a name="to-create-the-sample-project"></a>Vytvoření ukázkového projektu  
  
1. V aplikaci Visual Studio v nabídce **soubor** přejděte na možnost **Nový** a poté klikněte na položku **projekt**.  
  
2. V podokně **Nainstalované šablony** vyberte možnost Visual C#, Visual Basic nebo Visual C++. V případě spravovaných jazyků se ujistěte, že [!INCLUDE[net_v40_short](../includes/net-v40-short-md.md)] se zobrazuje v poli rozhraní.  
  
3. Vyberte **Konzolová aplikace** a pak klikněte na **OK**. Zůstane v konfiguraci ladění, což je výchozí nastavení.  
  
4. Otevřete v projektu soubor kódu. cpp,. cs nebo. vb. Odstraňte jeho obsah a vytvořte prázdný soubor kódu.  
  
5. Vložte následující kód pro zvolený jazyk do prázdného souboru kódu.  
  
   [!code-cpp[Debugger#1](../snippets/cpp/VS_Snippets_Misc/debugger/cpp/beta2_native.cpp#1)]
   [!code-csharp[Debugger#1](../snippets/csharp/VS_Snippets_Misc/debugger/cs/s.cs#1)]
   [!code-vb[Debugger#1](../snippets/visualbasic/VS_Snippets_Misc/debugger/vb/module1.vb#1)]  
  
6. V nabídce **File** (Soubor) klikněte na **Save All** (Uložit vše).  
  
7. V nabídce **sestavení** klikněte na příkaz **znovu sestavit řešení**.  
  
    Všimněte si, že jsou k dispozici čtyři volání `Debugger.Break` ( `DebugBreak` v ukázce jazyka C++), proto není nutné vkládat zarážky; pouhá spuštění aplikace způsobí přerušení v ladicím programu až čtyřikrát.  
  
## <a name="using-the-parallel-stacks-window-threads-view"></a>Použití okna Paralelní zásobníky: zobrazení vláken  
 V nabídce **Ladit** klikněte na **Spustit ladění**. Počkejte, než se dorazí na první zarážku.  
  
#### <a name="to-view-the-call-stack-of-a-single-thread"></a>Zobrazení zásobníku volání jednoho vlákna  
  
1. V nabídce **ladění** přejděte na **okna** a potom klikněte na **vlákna**. Ukotvěte okno **vlákna** v dolní části sady Visual Studio.  
  
2. V nabídce **ladění** přejděte na **okna** a potom klikněte na **zásobník volání**. Ukotvěte okno **zásobník volání** v dolní části sady Visual Studio.  
  
3. Dvakrát klikněte na vlákno v okně **vlákna** , čímž se nastaví jako aktuální. Aktuální vlákna mají žlutou šipku. Když změníte aktuální vlákno, jeho zásobník volání se zobrazí v okně **zásobník volání** .  
  
#### <a name="to-examine-the-parallel-stacks-window"></a>Kontrola okna Paralelní zásobníky  
  
1. V nabídce **ladění** přejděte na **okna** a potom klikněte na **paralelní zásobníky**. Ujistěte se, že je v poli v levém horním rohu vybraná možnost **vlákna** .  
  
     Pomocí okna **paralelní zásobníky** můžete zobrazit více zásobníků volání současně v jednom zobrazení. Následující ilustrace znázorňuje okno **paralelní zásobníky** nad oknem **zásobník volání** .  
  
     ![Zobrazení vláken v okně paralelní zásobníky](../debugger/media/pdb-walkthrough-1.png "PDB_Walkthrough_1")  
  
     Zásobník volání hlavního vlákna se zobrazí v jednom poli a zásobníky volání pro ostatní čtyři vlákna jsou seskupeny v jiném poli. Čtyři vlákna jsou seskupena dohromady, protože jejich rámce zásobníku sdílí stejné kontexty metod; To znamená, že jsou stejné metody: `A` , `B` a `C` . Chcete-li zobrazit ID a názvy vláken, která sdílejí stejné pole, umístěte ukazatel myši na záhlaví (**4 vlákna**). Aktuální vlákno je zobrazeno tučně, jak je znázorněno na následujícím obrázku.  
  
     ![Popis, který zobrazuje ID a názvy vláken](../debugger/media/pdb-walkthrough-1a.png "PDB_Walkthrough_1A")  
  
     Žlutá šipka označuje aktivní rámec zásobníku aktuálního vlákna. Chcete-li získat další informace, najeďte myší  
  
     ![Popis tlačítka pro aktivní rámec zásobníku](../debugger/media/pdb-walkthrough-1b.png "PDB_Walkthrough_1B")  
  
     Kliknutím pravým tlačítkem myši v okně **zásobník volání** můžete nastavit, kolik podrobností se má zobrazit pro rámce zásobníku (**názvy modulů**, **typy parametrů**, **názvy parametrů**, **hodnoty parametrů**, **čísla řádků** a **posun bajtů**).  
  
     Modrý zvýraznění kolem pole indikuje, že aktuální vlákno je součástí tohoto pole. Aktuální vlákno je také vyznačeno tučným rámcem zásobníku v popisku. Pokud dvakrát kliknete na hlavní vlákno v okně vlákna, můžete si všimnout, že modrý zvýraznění v okně **paralelní zásobníky** se odpovídajícím způsobem přesune.  
  
     ![Zvýrazněné hlavní vlákno v okně paralelní zásobníky](../debugger/media/pdb-walkthrough-1c.png "PDB_Walkthrough_1C")  
  
#### <a name="to-resume-execution-until-the-second-breakpoint"></a>Pokračování v provádění až do druhé zarážky  
  
1. Chcete-li pokračovat v provádění, dokud nebude dosaženo druhé zarážce, v nabídce **ladění** klikněte na tlačítko **pokračovat**. Následující ilustrace znázorňuje strom vláken ve druhé zarážce.  
  
     ![Okno paralelní zásobníky zobrazující mnoho větví](../debugger/media/pdb-walkthrough-2.png "PDB_Walkthrough_2")  
  
     Na první zarážce byly čtyři vlákna z S. A až S. B až S. C. Tyto informace jsou stále viditelné v okně **paralelní zásobníky** , ale v těchto čtyřech vláknech probíhalo další postup. Jedna z nich pokračovala S. D a pak S.E. Asia Další pokračování na S. F, S. G a S.H. Dva ostatní pokračuje na S. I a S. J a z jednoho z nich se dostali na S. K a druhý neuživatelský externí kód.  
  
     Můžete umístit ukazatel myši na záhlaví pole, například **1 vlákno** nebo **2 vlákna**, a zobrazit tak ID vláken vláken. Můžete umístit ukazatel myši na snímky zásobníku a zobrazit ID vláken a další podrobnosti o snímku. Modrý zvýraznění indikuje aktuální vlákno a žlutá šipka označuje aktivní rámec zásobníku aktuálního vlákna.  
  
     Ikona tkanin – vlákna (překrývající modré a červené vlnovky) označují aktivní rámce zásobníku neaktuálních vláken. V okně **zásobník volání** poklikejte na y. B pro přepínání snímků. Okno **paralelní zásobníky** indikuje aktuální rámec zásobníku aktuálního vlákna pomocí ikony šipky zeleného zahnutého okna.  
  
     V okně **vlákna** přepínejte mezi vlákny a sledujte, že zobrazení v okně **paralelní zásobníky** je aktualizováno.  
  
     Pomocí místní nabídky v okně **paralelní zásobníky** můžete přepnout do jiného vlákna nebo do jiného rámce jiného vlákna. Například klikněte pravým tlačítkem S. J, přejděte na **Přepnout na rámec**a potom klikněte na příkaz.  
  
     ![Cesta k paralelním zásobníkům pro spuštění](../debugger/media/pdb-walkthrough-2b.png "PDB_Walkthrough_2B")  
  
     Klikněte pravým tlačítkem myši na možnost S. C a přejděte na možnost **Přepnout na rámec**. Jeden z příkazů má značku zaškrtnutí, která označuje rámec zásobníku aktuálního vlákna. Můžete přepnout na tento snímek stejného vlákna (pouze zelená šipka se přesune) nebo můžete přepnout do jiného vlákna (modré zvýraznění se také přesune). Následující ilustrace znázorňuje podnabídku.  
  
     ![Nabídka zásobníků se dvěma možnostmi v C, zatímco J je aktuální.](../debugger/media/pdb-walkthrough-3.png "PDB_Walkthrough_3")  
  
     Když je kontext metody spojen s pouze jedním snímkem zásobníku, zobrazí záhlaví pole **1 vlákno** a můžete na něj přejít dvojitým kliknutím. Pokud dvakrát kliknete na kontext metody, ke kterému je přidruženo více než 1 rámec, nabídka se automaticky otevře. Při najetí myší na kontexty metod si všimněte černého trojúhelníku vpravo. Kliknutím na tento trojúhelník se zobrazí také místní nabídka.  
  
     U rozsáhlých aplikací, které mají mnoho vláken, můžete chtít soustředit se jenom na podmnožinu vláken. Okno **paralelní zásobníky** může zobrazit zásobníky volání pouze pro vlákna označená příznakem. Na panelu nástrojů klikněte na tlačítko **Zobrazit pouze označené příznakem** vedle rozevíracího seznamu.  
  
     ![Prázdné okno a popisek paralelních zásobníků](../debugger/media/pdb-walkthrough-3a.png "PDB_Walkthrough_3A")  
  
     Dále v okně **vlákna** označte vlákna jeden po jedné, abyste viděli, jak se jejich zásobníky volání zobrazují v okně **paralelní zásobníky** . Chcete-li označit vlákna, použijte místní nabídku nebo první buňku vlákna. Opětovným kliknutím na tlačítko Zobrazit pouze panel nástrojů s **příznakem** zobrazíte všechna vlákna.  
  
#### <a name="to-resume-execution-until-the-third-breakpoint"></a>Chcete-li pokračovat v provádění až po třetí zarážku  
  
1. Chcete-li pokračovat v provádění, dokud nebude dosaženo třetí zarážce, v nabídce **ladění** klikněte na tlačítko **pokračovat**.  
  
    Pokud je více vláken ve stejné metodě, ale metoda nebyla na začátku zásobníku volání, metoda se zobrazí v různých polích. Příklad v aktuální zarážce je S. L, který má tři vlákna v něm a je zobrazen ve třech polích. Dvakrát klikněte na S.L.  
  
    ![Cesta spuštění v okně paralelní zásobníky](../debugger/media/pdb-walkthrough-3b.png "PDB_Walkthrough_3B")  
  
    Všimněte si, že S. L je tučné v dalších dvou polích tučné, abyste viděli, kde se nachází jinde. Pokud chcete zjistit, které snímky volají do S. L a které rámce volá, klikněte na tlačítko **zobrazení přepínací metody** na panelu nástrojů. Následující ilustrace znázorňuje zobrazení metody okna **paralelní zásobníky** .  
  
    ![Zobrazení metody v okně paralelních zásobníků](../debugger/media/pdw-walkthrough-4.png "PDW_Walkthrough_4")  
  
    Všimněte si, jak se diagram na vybrané metodě pivotoval a umístí ho do vlastního pole uprostřed zobrazení. Volané a volající se zobrazí v horní a dolní části. Pokud chcete tento režim opustit, klikněte znovu na tlačítko **zobrazení metody přepínání** .  
  
    Místní nabídka okna **paralelní zásobníky** má také následující další položky.  
  
   - **Hexadecimální zobrazení** přepíná čísla v popisech mezi desítkovými a šestnáctkovými hodnotami.  
  
   - **Informace o načtení symbolů** a **Nastavení symbolů** otevřou příslušná dialogová okna.  
  
   - **Přejít ke zdrojovému kódu** a **Přejít na zpětný překlad** navigace v editoru na vybranou metodu.  
  
   - **Zobrazit externí kód** zobrazí všechny snímky i v případě, že nejsou v uživatelském kódu. Zkuste zobrazit, aby se diagram rozšířil na další snímky (což může být nedostupné, protože pro ně nemáte symboly).  
  
     Pokud máte velké diagramy a máte krok na další zarážku, můžete chtít zobrazení automaticky přejít na aktivní rámec zásobníku aktuálního vlákna; To znamená, že vlákno, které dosáhlo zarážky jako první. V okně **paralelní zásobníky** se ujistěte, že je na panelu nástrojů zapnuto tlačítko **automaticky přejít na aktuální rámec zásobníku** .  
  
     ![Automatické posouvání v okně paralelní zásobníky](../debugger/media/pdb-walkthrough-4a.png "PDB_Walkthrough_4A")  
  
2. Než budete pokračovat, v okně **paralelní zásobníky** se posuňte všem směrem doleva a dolů.  
  
#### <a name="to-resume-execution-until-the-fourth-breakpoint"></a>Pokračování v provádění až do čtvrté zarážky  
  
1. Chcete-li pokračovat v provádění, dokud není dosaženo čtvrté zarážky, v nabídce **ladění** klikněte na tlačítko **pokračovat**.  
  
     Všimněte si, jak se zobrazení automaticky posouvá na místo. Přepněte vlákna v okně **vlákna** nebo přepněte rámce zásobníku v okně **zásobník volání** a Všimněte si, jak se zobrazení vždy automaticky posouvá na správný rámeček. Vypne **automatické posouvání na aktuální možnost snímku nástroje** a zobrazí rozdíl.  
  
     **Pohled na pohled z ptačí perspektivy** také pomáhá s velkými diagramy v okně **paralelní zásobníky** . **Zobrazení očí** můžete zobrazit tak, že kliknete na tlačítko mezi posuvníky v pravém dolním rohu okna, jak je znázorněno na následujícím obrázku.  
  
     ![Zobrazení perspektivy&#45;v okně paralelní zásobníky](../debugger/media/pdb-walkthrough-5.png "PDB_Walkthrough_5")  
  
     Obdélník můžete rychle posunout kolem diagramu.  
  
     Dalším způsobem, jak diagram přesunout v libovolném směru, je kliknout na prázdnou oblast diagramu a přetáhnout ho tam, kde chcete.  
  
     Chcete-li přiblížit nebo oddálit diagram, stiskněte a podržte klávesu CTRL při přesunu kolečka myši. Případně klikněte na tlačítko přiblížení na panelu nástrojů a pak použijte nástroj Lupa.  
  
     ![Zvětšené zásobníky v okně paralelní zásobníky](../debugger/media/pdb-walkthrough-5a.png "PDB_Walkthrough_5A")  
  
     Můžete také zobrazit zásobníky v horním směrem dolů, a to tak, že kliknete na nabídku **nástroje** , kliknete na možnost **Možnosti**a pak vyberete nebo zrušíte zaškrtnutí políčka v uzlu **ladění** .  
  
2. Než budete pokračovat, v nabídce **ladění** klikněte na **Zastavit ladění** a ukončete provádění.  
  
## <a name="using-the-parallel-tasks-window-and-the-tasks-view-of-the-parallel-stacks-window"></a>Použití okna Paralelní úlohy a zobrazení úlohy okna Paralelní zásobníky  
 Doporučujeme, abyste před pokračováním dokončili předchozí postupy.  
  
#### <a name="to-restart-the-application-until-the-first-breakpoint-is-hit"></a>Restartování aplikace, dokud nebude dosaženo první zarážce  
  
1. V nabídce **ladění** klikněte na **Spustit ladění** a počkejte, než se dorazí na první zarážku.  
  
2. V nabídce **ladění** přejděte na **okna** a potom klikněte na **vlákna**. Ukotvěte okno **vlákna** v dolní části sady Visual Studio.  
  
3. V nabídce **ladění** přejděte na **Windows** a klikněte na **zásobník volání**. Ukotvěte okno **zásobník volání** v dolní části sady Visual Studio.  
  
4. Dvakrát klikněte na vlákno v okně **vlákna** , čímž se vytvoří aktuální. Aktuální vlákna mají žlutou šipku. Když změníte aktuální vlákno, ostatní okna budou aktualizována. V dalším kroku prověříme úlohy.  
  
5. V nabídce **ladění** přejděte na příkaz **Windows** a klikněte na možnost **Paralelní úlohy**. Následující obrázek znázorňuje okno **Paralelní úlohy** .  
  
     ![Čtyři spuštěné úlohy v okně Paralelní úlohy](../debugger/media/pdw-walkthrough-6.png "PDW_Walkthrough_6")  
  
     Pro každou spuštěnou úlohu si můžete přečíst jeho ID, které je vráceno se stejnou pojmenovanou vlastností, ID a název vlákna, ve kterém je spuštěno, jeho umístění (když je ukazatel myši nad, zobrazí se popis, který obsahuje celý zásobník volání). V rámci sloupce **úlohy** také můžete zobrazit metodu, která byla předána do úlohy. Jinými slovy, počátečním bodem.  
  
     Můžete řadit libovolný sloupec. Všimněte si glyfu řazení, který označuje sloupec a směr řazení. Sloupce můžete také změnit jejich přetažením doleva nebo doprava.  
  
     Žlutá šipka indikuje aktuální úlohu. Úkoly můžete přepínat dvojitým kliknutím na úlohu nebo pomocí místní nabídky. Když přepnete úkoly, podkladové vlákno bude aktuální a ostatní okna budou aktualizována.  
  
     Při ručním přepnutí z jednoho úkolu na druhý se žlutá šipka přesune, ale bílá šipka stále zobrazuje úlohu, která způsobila přerušení ladicího programu.  
  
#### <a name="to-resume-execution-until-the-second-breakpoint"></a>Pokračování v provádění až do druhé zarážky  
  
1. Chcete-li pokračovat v provádění, dokud nebude dosaženo druhé zarážce, v nabídce **ladění** klikněte na tlačítko **pokračovat**.  
  
     Dříve se ve sloupci **stav** zobrazily všechny úlohy, které jsou spuštěny, ale nyní dvě úlohy čekají. Úlohy je možné zablokovat z mnoha různých důvodů. Ve sloupci **stav** najeďte myší na čekající úlohu a zjistěte, proč je zablokovaná. Například na následujícím obrázku úloha 3 čeká na úlohu 4.  
  
     ![Dva čekající úlohy v okně Paralelní úlohy](../debugger/media/pdb-walkthrough-7.png "PDB_Walkthrough_7")  
  
     Úloha 4 pak čeká na monitorování, které vlastní vlákno přiřazené k úloze 2.  
  
     ![Úloha a popisek čekání v okně úlohy](../debugger/media/pdb-walkthrough-7a.png "PDB_Walkthrough_7A")  
  
     Úkol můžete označit kliknutím na příznak v prvním sloupci okna **Paralelní úlohy** .  
  
     Pomocí příznaku můžete sledovat úlohy mezi různými zarážkami ve stejné relaci ladění nebo filtrovat úkoly, jejichž zásobníky volání se zobrazují v okně **paralelní zásobníky** .  
  
     Při předchozím použití okna **paralelní zásobníky** jste zobrazili vlákna aplikace. Zobrazte okno **paralelní zásobníky** znovu, ale tentokrát se zobrazí úlohy aplikace. Provedete to tak, že vyberete **úkoly** v poli vlevo nahoře. Na následujícím obrázku je znázorněno zobrazení úkolů.  
  
     ![Zobrazení vláken v okně paralelní zásobníky](../debugger/media/pdb-walkthrough-8.png "PDB_Walkthrough_8")  
  
     Vlákna, která aktuálně nespouštějí úlohy, se nezobrazí v zobrazení úlohy okna **paralelní zásobníky** . V případě vláken, která spouštějí úkoly, jsou také z horního a dolního zásobníku filtrovány některé rámce zásobníku, které nejsou relevantní pro úlohy.  
  
     Znovu zobrazte okno **Paralelní úlohy** . Kliknutím pravým tlačítkem myši na záhlaví kteréhokoli sloupce zobrazíte místní nabídku pro daný sloupec.  
  
     ![Místní nabídka zobrazení v okně Paralelní úlohy](../debugger/media/pdb-walkthrough-8a.png "PDB_Walkthrough_8A")  
  
     Pomocí místní nabídky můžete přidat nebo odebrat sloupce. Například není vybrán sloupec AppDomain. Proto se v seznamu nezobrazí. Klikněte na **Nadřazená položka**. **Nadřazený** sloupec se zobrazí bez hodnot pro žádnou ze čtyř úkolů.  
  
#### <a name="to-resume-execution-until-the-third-breakpoint"></a>Chcete-li pokračovat v provádění až po třetí zarážku  
  
1. Chcete-li pokračovat v provádění, dokud nebude dosaženo třetí zarážce, v nabídce **ladění** klikněte na tlačítko **pokračovat**.  
  
     Nová úloha, úloha 5, je teď spuštěná a úloha 4 teď čeká. Můžete se podívat, proč na čekající úkol ve **stavovém** okně najede myší. V **nadřazeném** sloupci si všimněte, že úloha 4 představuje nadřazený úkol 5.  
  
     Chcete-li lépe vizualizovat vztah nadřazený-podřízený, klikněte pravým tlačítkem myši na záhlaví **nadřazeného** sloupce a potom klikněte na položku **nadřazené podřízené zobrazení**. Měl by se zobrazit následující obrázek.  
  
     ![Nadřazené zobrazení podřízené&#45;v okně Paralelní úlohy](../debugger/media/pdb-walkthrough-9.png "PDB_Walkthrough_9")  
  
     Všimněte si, že úloha 4 a úloha 5 jsou spuštěny ve stejném vlákně. Tyto informace nejsou zobrazeny v okně **vlákna** . Podívejte se, že se jedná o další výhody okna **paralelní úkoly** . Potvrďte to tak, že zobrazíte okno **paralelní zásobníky** . Ujistěte se, že prohlížíte **úkoly**. Vyhledejte úkoly 4 a 5 dvojitým kliknutím na ně v okně **Paralelní úlohy** . V takovém případě se modrý zvýraznění v okně **paralelní zásobníky** aktualizuje. Můžete také vyhledat úlohy 4 a 5 kontrolou tlačítek v okně **paralelní zásobníky** .  
  
     ![Zobrazení úloh v paralelních zásobnících okna](../debugger/media/pdb-walkthrough-9a.png "PDB_Walkthrough_9A")  
  
     V okně **paralelní zásobníky** klikněte pravým tlačítkem na S. P a pak klikněte na **Přejít ke vláknu**. Okno se přepne do zobrazení vlákna a odpovídající rámec je v zobrazení. Ve stejném vlákně vidíte obě úlohy.  
  
     ![Zvýrazněné vlákno v zobrazení vláken](../debugger/media/pdb-walkthrough-9b.png "PDB_Walkthrough_9B")  
  
     Toto je další výhodou zobrazení úlohy v okně **paralelní zásobníky** ve srovnání s oknem **vláken** .  
  
#### <a name="to-resume-execution-until-the-fourth-breakpoint"></a>Pokračování v provádění až do čtvrté zarážky  
  
1. Chcete-li pokračovat v provádění, dokud nebude dosaženo třetí zarážce, v nabídce **ladění** klikněte na tlačítko **pokračovat**. Kliknutím na záhlaví sloupce **ID** seřadíte podle ID. Měl by se zobrazit následující obrázek.  
  
     ![Čtyři stavy úloh v paralelních zásobnících okna](../debugger/media/pdb-walkthrough-10.png "PDB_Walkthrough_10")  
  
     Protože byl úkol 5 dokončen, již není zobrazen. Pokud se nejedná o případ na vašem počítači a zablokování se nezobrazuje, proveďte krok jednou stisknutím klávesy F11.  
  
     Úloha 3 a úloha 4 teď čekají na sebe a zablokují se. K dispozici jsou také 5 nových úloh, které jsou podřízenými položkami úlohy 2 a jsou nyní naplánovány. Naplánované úlohy jsou úlohy, které byly spuštěny v kódu, ale ještě nebyly spuštěny. Proto jsou sloupce přiřazení **umístění** a **vlákna** prázdné.  
  
     Znovu zobrazte okno **paralelní zásobníky** . Záhlaví každého pole má popisek, který zobrazuje ID a názvy vláken. Přepněte do zobrazení úlohy v okně **paralelní zásobníky** . Když najedete myší na záhlaví, zobrazí se ID a název úlohy a stav úlohy, jak je znázorněno na následujícím obrázku.  
  
     ![Popisek záhlaví v okně paralelní zásobníky](../debugger/media/pdb-walkthrough-11.png "PDB_Walkthrough_11")  
  
     Úkoly můžete seskupit podle sloupce. V okně **Paralelní úlohy** klikněte pravým tlačítkem myši na záhlaví sloupce **stav** a pak klikněte na možnost **Seskupit podle stav**. Následující ilustrace znázorňuje okno **Paralelní úlohy** seskupené podle stavu.  
  
     ![Seskupené úlohy v okně Paralelní úlohy](../debugger/media/pdb-walkthrough-12.png "PDB_Walkthrough_12")  
  
     Můžete také seskupit podle libovolného jiného sloupce. Seskupením úloh se můžete soustředit na podmnožinu úkolů. Každá sbalitelná skupina má počet položek, které jsou seskupeny dohromady. Všechny položky ve skupině můžete také rychle označit kliknutím na tlačítko **příznak** napravo od tlačítka **sbalit** .  
  
     ![Seskupené zásobníky v okně paralelní zásobníky](../debugger/media/pdb-walkthrough-12a.png "PDB_Walkthrough_12A")  
  
     Poslední funkcí okna **Paralelní úlohy** k prohlédnutí je místní nabídka, která se zobrazí po kliknutí pravým tlačítkem myši na úlohu.  
  
     ![Místní nabídka v okně Paralelní úlohy](../debugger/media/pdb-walkthrough-12b.png "PDB_Walkthrough_12B")  
  
     Místní nabídka zobrazuje různé příkazy v závislosti na stavu úlohy. Příkazy mohou zahrnovat **kopírování**, **Výběr všech**, **hexadecimálního zobrazení**, **Přepnutí na úlohu**, **zablokování přiřazeného vlákna**, **zablokování všech vláken, ale toto**a **příznak**. **Thaw Assigned Thread**  
  
     Můžete zablokovat základní vlákno úlohy nebo úlohy nebo můžete zablokovat všechna vlákna s výjimkou přiřazeného. Zmrazené vlákno je znázorněno v okně **Paralelní úlohy** , protože je v okně **vlákna** s ikonou modrého *pozastavení* .  
  
## <a name="summary"></a>Shrnutí  
 Tento názorný postup ukázal okna **paralelních úkolů** a **paralelních zásobníků** pro ladicí program. Používejte tato okna na skutečných projektech, které používají vícevláknový kód. Můžete kontrolovat paralelní kód napsaný v jazyce C++, C# nebo Visual Basic.  
  
## <a name="see-also"></a>Viz také  
 [Ladění vícevláknových aplikací](../debugger/walkthrough-debugging-a-parallel-application.md)   
 [Základy ladicího programu](../debugger/debugger-basics.md)   
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)   
 [Paralelní programování](https://msdn.microsoft.com/library/4d83c690-ad2d-489e-a2e0-b85b898a672d)   
 [Concurrency Runtime](https://msdn.microsoft.com/library/874bc58f-8dce-483e-a3a1-4dcc9e52ed2c)   
 [Použití okna Paralelní zásobníky](../debugger/using-the-parallel-stacks-window.md)   
 [Používání okna úloh](../debugger/using-the-tasks-window.md)
