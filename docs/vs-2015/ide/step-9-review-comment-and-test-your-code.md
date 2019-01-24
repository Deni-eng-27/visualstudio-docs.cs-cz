---
title: 'Krok 9: Zkontrolujte, komentáře a testování kódu | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: f26f79ba-c91b-4164-b87f-679a1b231c09
caps.latest.revision: 31
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: b03c6c7af9cfedcf7e45a61dba826d99b300ffbe
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54796734"
---
# <a name="step-9-review-comment-and-test-your-code"></a>Krok 9: Kontrola, okomentování a otestování kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Dále přidáte komentář do vašeho kódu. Komentář je Všimněte si, že nedojde ke změně způsobu, jakým se chová program. To usnadňuje pro čtenáře kódu pochopit jeho význam. Přidání komentářů do kódu je dobré se naučit do. V jazyce Visual C# dvě lomítka (/ /) značí řádek jako komentáře. V jazyce Visual Basic jednoduché uvozovky (') slouží k označení řádku jako komentáře. Po přidání komentáře otestujete váš program. Je vhodné spustit a otestovat kód často při práci na svých projektech, takže můžete zachytit a opravit případné problémy dříve, než kód složitější. Tento postup se nazývá *iterativnější testování*.  
  
 Právě jste vytvořili něco, co funguje, a i když ještě není Hotovo, může program již načíst obrázek. Před přidání komentáře ke kódu a testování, potřebují dobu na zkontrolování koncepty kódu, protože tyto koncepty budete používat často:  
  
- Pokud jste dvakrát kliknuli **zobrazit obrázek** tlačítko v Návrháři formulářů Windows, rozhraní IDE automaticky přidalo *metoda* do kódu vašeho programu.  
  
- Způsoby, jak organizovat kód: Je to, jak váš kód seskupený.  
  
- Ve většině případů, metodu provádí malý počet akcí v určitém pořadí, například jako vaše `showButton_Click()` metoda zobrazí dialogové okno a potom načte obrázek.  
  
- Metoda je tvořen kód *příkazy*, nebo řádků kódu. Metodu si lze představit jako způsob, jak příkazy kódu svážete dohromady.  
  
- Když je metoda spuštěna, nebo *volá*, příkazy v metodě jsou spouštěny v pořadí jeden po druhém počínaje první z nich.  
  
   Následuje příklad příkazu.  
  
  ```csharp  
  pictureBox1.Load(openFileDialog1.FileName);  
  ```  
  
  ```vb  
  pictureBox1.Load(openFileDialog1.FileName)  
  ```  
  
   Příkazy jsou to, co nechává vaše programy provádět akce. V jazyce Visual C# příkaz vždy končí středníkem. V jazyce Visual Basic je konec řádku konec příkazu. (Žádný středník není třeba v jazyce Visual Basic). Předchozí příkaz sděluje vaše `PictureBox` ovládací prvek se načíst soubor, který uživatel vybral s **OpenFileDialog** komponenty.  
  
  ![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo")video verzi tohoto tématu naleznete v tématu [kurz 1: Vytvoření prohlížeče obrázků v jazyce Visual Basic - Video 5](http://go.microsoft.com/fwlink/?LinkId=205216) nebo [kurz 1: Vytvoření prohlížeče obrázků v C# – Video 5](http://go.microsoft.com/fwlink/?LinkId=205206). Tato videa používají starší verzi sady Visual Studio, takže existují mírné rozdíly v některých příkazech nabídek a jiných prvcích uživatelského rozhraní. Nicméně koncepty a postupy fungují podobně jako v aktuální verzi sady Visual Studio.  
  
### <a name="to-add-comments"></a>Chcete-li přidat komentáře  
  
1.  Přidejte následující komentář do kódu.  
  
     [!code-csharp[VbExpressTutorial1Step9_10#1](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial1step9_10/cs/form1.cs#1)]
     [!code-vb[VbExpressTutorial1Step9_10#1](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial1step9_10/vb/form1.vb#1)]  
  
    > [!NOTE]
    >  Vaše **showButton** Click tlačítka obslužná rutina události je nyní dokončena a pracuje. Zahájili jste psaní kódu, počínaje `if` příkazu. `if` Příkaz je, jak říct vašemu programu: "Zkontroluj tuto jednu věc a pokud je PRAVDA, proveď tyto akce." V takovém případě říkáte programu, otevřete **otevřít soubor** dialogové okno, a pokud uživatel vybere soubor a klikne **OK** tlačítko, načte soubor v ovládacím prvku PictureBox.  
  
    > [!TIP]
    >  Rozhraní IDE je sestaveno k usnadnění psaní kódu a *fragmenty kódu* jsou jedním ze způsobů, který provádí. Fragment je zástupce, který se rozbalí do malého bloku kódu.  
    >   
    >  Zobrazí se všechny dostupné Výstřižky. V panelu nabídky zvolte **nástroje**, **Správce fragmentů kódů**. Pro jazyk Visual C# `if` fragment kódu je v **Visual C#** . V jazyce Visual Basic `if` fragmenty kódu jsou v **podmínkách a smyčkách**, **vzorů v kódu**. Tento správce můžete použít k vyhledání existujících fragmentů nebo přidání vlastních fragmentů.  
    >   
    >  K aktivování výstřižku při zadávání kódu, zadejte ji a stiskněte klávesu Tabulátor. Mnoho fragmentů se nachází v **IntelliSense** okna, což je důvod, proč zvolit klávesu Tabulátor dvakrát: nejprve k vybrání fragmentu z **IntelliSense** okna a poté ke sdělení rozhraní IDE má fragment použít. (Technologie IntelliSense podporuje `if` fragment kódu, ale ne `ifelse` fragment kódu.)  
  
2.  Než svůj program spustíte, uložte program výběrem **Uložit vše** tlačítka panelu nástrojů, které se zobrazí takto.  
  
     ![Uložit všechny tlačítka panelu nástrojů](../ide/media/express-iconsaveall.png "Express_IconSaveAll")  
Tlačítko Uložit vše  
  
     Můžete také svůj program uložíte na řádku nabídek, zvolte **souboru**, **Uložit vše**. To je osvědčený postup pro uložení včas a často.  
  
     Když je spuštěn, váš program by měl vypadat jako na následujícím obrázku.  
  
     ![Picture Viewer](../ide/media/express-pictureviewerdonerun.png "Express_PictureViewerDoneRun")  
Prohlížeč obrázků  
  
### <a name="to-test-your-program"></a>Testovat váš program  
  
1.  Stisknutím klávesy F5 nebo vyberte **spustit ladění** tlačítka panelu nástrojů.  
  
2.  Zvolte **zobrazit obrázek** tlačítko spustit kód, který jste napsali. Nejprve program otevře **otevřít soubor** dialogové okno. Ověřte, že vaše filtry se zobrazí v **soubory typu** rozevírací seznam v dolní části dialogového okna. Potom přejděte na obrázek a otevřete jej. Obvykle lze najít vzorové obrázky dodávané s operačním systémem Windows ve vaší **dokumenty** složky, uvnitř **Moje Obrázky\Příklady obrázků** složky.  
  
    > [!NOTE]
    >  Pokud nevidíte žádné obrázky v **vyberte soubor s obrázkem** dialogové okno, ujistěte se, že "všechny soubory (*.\*)" filtru je vybrali v rozevíracím seznamu v dolní pravé části dialogových oken.  
  
3.  Načíst obrázek a zobrazí se ve vašem ovládacím prvku PictureBox. Zkuste změnit velikost formuláře přetažením jeho okrajů. Protože máte váš ovládací prvek PictureBox ukotven uvnitř kontejneru TableLayoutPanel, který je sám ukotven uvnitř formuláře, oblast vašeho obrázku změní velikost sebe sama tak, aby je stejně široká jako formulář a vyplní horních 90 procent formuláře. To je důvod, proč jste použili kontejnery TableLayoutPanel a FlowLayoutPanel: Udržují správnou velikost, když ji uživatel změní formuláře.  
  
     Nyní větší obrázky překračují hranice prohlížeče obrázků. V dalším kroku přidáte kód, aby obrázky pasovaly do okna.  
  
### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  
  
-   Přechod k dalšímu kroku výukového programu naleznete v tématu [krok 10: Napsat kód pro přídavná tlačítka a zaškrtávací políčko](../ide/step-10-write-code-for-additional-buttons-and-a-check-box.md).  
  
-   Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 8: Napsat kód pro zobrazení obslužné rutiny události obrázku tlačítka](../ide/step-8-write-code-for-the-show-a-picture-button-event-handler.md).
