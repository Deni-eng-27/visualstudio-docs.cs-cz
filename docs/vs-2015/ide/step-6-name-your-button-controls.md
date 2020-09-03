---
title: 'Krok 6: Pojmenujte své ovládací prvky tlačítek | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 56b3baa3-651e-4ad4-8942-e334c5c57158
caps.latest.revision: 31
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 4d4d703dbe28776cd93c7a438fc457d9f50ac4f7
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "75851133"
---
# <a name="step-6-name-your-button-controls"></a>Krok 6: Pojmenujte své ovládací prvky tlačítek
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Ve formuláři je pouze jeden ovládací prvek PictureBox. Po přidání se rozhraní IDE automaticky jmenuje **pictureBox1**. Existuje pouze jedno zaškrtávací políčko s názvem **checkBox1**. Brzy napíšete kód, který bude odkazovat na zaškrtávací políčko a PictureBox. Vzhledem k tomu, že existuje pouze jeden z těchto ovládacích prvků, budete znát, co to znamená, když ve svém kódu uvidíte **pictureBox1** nebo **checkBox1** .

> [!NOTE]
> V Visual Basic výchozí první písmeno libovolného názvu ovládacího prvku má počáteční zakončení, takže názvy jsou **pictureBox1**, **checkBox1**a tak dále.

 Ve formuláři jsou čtyři tlačítka a rozhraní IDE s názvem **Button1**, **Button2**, **Button3**a **Button4**. Pouhým zobrazením jejich aktuálních názvů nevíte, které tlačítko představuje tlačítko **Zavřít** a který je jedním z tlačítek **Zobrazit obrázek** . To je důvod, proč vaše tlačítko ovládá více informativních názvů je užitečné.

 ![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo") Verzi videa tohoto tématu najdete v tématu [kurz 1: vytvoření prohlížeče obrázků v Visual Basic-Video 3](https://msdn.microsoft.com/vbasic/gg315354.aspx) nebo v [kurzu 1: vytvoření prohlížeče obrázků v jazyce C# – video 3](https://msdn.microsoft.com/vcsharp/gg278411.aspx). Tato videa používají starší verzi sady Visual Studio, takže existují mírné rozdíly v některých příkazech nabídky a dalších prvcích uživatelského rozhraní. Koncepty a postupy však fungují podobně v aktuální verzi sady Visual Studio.

### <a name="to-name-your-button-controls"></a>Chcete-li pojmenovat ovládací prvky tlačítka

1. Ve formuláři klikněte na tlačítko **Zavřít** . (Pokud máte stále vybraná všechna tlačítka, kliknutím na klávesu ESC výběr zrušte.) Posuňte se v okně **vlastnosti** , dokud se nezobrazí vlastnost **(název)** . (Vlastnost **(Name)** je blízko horní části, pokud jsou vlastnosti seřazené abecedně.) Změňte název na **closeButton**, jak je znázorněno na následujícím obrázku.

     ![Okno Vlastnosti s názvem closeButton](../ide/media/express-setnameproperty.png "Express_SetNameProperty") okno Vlastnosti s názvem closeButton

    > [!NOTE]
    > Pokud se pokusíte změnit název tlačítka na **closeButton**s mezerou mezi slovy zavřít a tlačítko, rozhraní IDE zobrazí chybovou zprávu: "hodnota vlastnosti není platná." Mezery (a několik dalších znaků) nejsou povoleny v názvech ovládacích prvků.

2. Přejmenujte další tři tlačítka na **backgroundButton**, **clearButton**a **showButton**. Názvy můžete ověřit tak, že v okně **vlastnosti** zvolíte rozevírací seznam výběr ovládacího prvku. Nové názvy tlačítek se zobrazí.

3. Dvakrát klikněte na tlačítko **Zobrazit obrázek** ve formuláři. Jako alternativu zvolte tlačítko **Zobrazit obrázek** ve formuláři a pak zvolte klávesu ENTER. Když to uděláte, IDE otevře další kartu v hlavním okně s názvem **Form1.cs** (**Form1. vb** , pokud používáte Visual Basic). Tato karta zobrazuje soubor kódu za formulářem, jak je znázorněno na následujícím obrázku.

     ![Karta Form1.cs s kódem jazyka Visual C&#35;](../ide/media/express-showbuttoncode.png "Express_ShowButtonCode") Karta Form1.cs s kódem jazyka Visual C#

4. Zaměřte se na tuto část kódu. (Pokud používáte Visual Basic k zobrazení Visual Basic verze kódu, klikněte na kartu **VB** .)

     [!code-csharp[VbExpressTutorial1Step6#1](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial1step6/cs/form1.cs#1)]
     [!code-vb[VbExpressTutorial1Step6#1](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial1step6/vb/form1.vb#1)]

     Díváte jste se na kód s názvem `showButton_Click()` . Rozhraní IDE bylo přidáno do kódu formuláře při otevření souboru kódu pro tlačítko **showButton** . V době návrhu při otevření souboru kódu pro ovládací prvek ve formuláři se kód vygeneruje pro ovládací prvek, pokud ještě neexistuje. Tento kód, který se označuje jako *Metoda*, se spouští při spuštění programu a výběru ovládacího prvku – v tomto případě se **zobrazí tlačítko Zobrazit obrázek** .

    > [!NOTE]
    > V tomto kurzu je kód Visual Basic, který je automaticky vygenerován, zjednodušen odebráním všeho mezi závorkami, (). Kdykoli k tomu dojde, můžete stejný kód odstranit. Program bude pracovat v obou případech. Ve zbývající části kurzů je jakýkoli automaticky generovaný kód zjednodušený, kdykoli je to možné.

5. Zvolte znovu kartu Návrhář formulářů (**Form1.cs [Design]** v jazyce Visual C#, **Form1. vb [Design]** v Visual Basic) a poté otevřete soubor kódu pro tlačítko **Vymazat obrázek** pro vytvoření metody v kódu formuláře. Tento postup opakujte pro zbývající dvě tlačítka. V každém okamžiku rozhraní IDE přidá novou metodu do souboru kódu formuláře.

6. Chcete-li přidat další metodu, otevřete soubor kódu pro ovládací prvek CheckBox v Návrhář formulářů, aby rozhraní IDE přidalo `checkBox1_CheckedChanged()` metodu. Tato metoda je volána vždy, když uživatel vybere nebo zruší zaškrtnutí políčka.

    > [!NOTE]
    > Při práci na programu se často přesouváte mezi editorem kódu a Návrhář formulářů. Rozhraní IDE usnadňuje navigaci v projektu. Pomocí **Průzkumník řešení** otevřít Návrhář formulářů dvojitým kliknutím na **Form1.cs** v jazyce Visual C# nebo **Form1. vb** v Visual Basic nebo na panelu nabídek vyberte možnost **zobrazení**, **Návrhář**.

     Následující příklad ukazuje nový kód, který se zobrazí v editoru kódu.

     [!code-csharp[VbExpressTutorial1Step6#2](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial1step6/cs/form1.cs#2)]
     [!code-vb[VbExpressTutorial1Step6#2](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial1step6/vb/form1.vb#2)]

     Pět metod, které jste přidali, se nazývají *obslužné rutiny událostí*, protože je program volá vždy, když dojde k události (jako je například uživatel výběr tlačítka nebo výběru pole).

     Při zobrazení kódu pro ovládací prvek v rozhraní IDE v době návrhu, Visual Studio přidá metodu obslužné rutiny události pro ovládací prvek, pokud žádný není. Například když dvakrát kliknete na tlačítko, rozhraní IDE přidá obslužnou rutinu události pro událost Click (která je volána vždy, když uživatel zvolí tlačítko). Když dvakrát kliknete na zaškrtávací políčko, rozhraní IDE přidá obslužnou rutinu události pro svou událost CheckedChanged (která je volána vždy, když uživatel vybere nebo zruší pole).

     Po přidání obslužné rutiny události pro ovládací prvek se k němu můžete kdykoli vrátit z Návrhář formulářů dvojitým kliknutím na ovládací prvek nebo na řádku nabídek, výběrem možnosti **Zobrazit**, **kód**.

     Názvy jsou důležité při sestavování programů a metody (včetně obslužných rutin událostí) můžou mít libovolný název, který chcete. Když přidáte obslužnou rutinu události s rozhraním IDE, vytvoří se název založený na názvu ovládacího prvku a události, která je zpracovávána. Například událost Click pro tlačítko s názvem **showButton** se nazývá `showButton_Click()` Metoda obslužné rutiny události. Také se otevírají a uzavírající závorky () obvykle přidávají za názvem metody k označení toho, že se metody diskutuje. Pokud se rozhodnete, že chcete změnit název proměnné kódu, klikněte pravým tlačítkem na proměnnou v kódu a pak zvolte **refaktoring**, **Přejmenovat**. Všechny instance této proměnné v kódu jsou přejmenovány. Další informace najdete v tématu [přejmenování refaktoringu (C#)](../csharp-ide/rename-refactoring-csharp.md) nebo [refaktoringu a přejmenování](https://msdn.microsoft.com/library/001d2d81-9bb6-4e8e-ae3a-20c0daaa3959) .

### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Chcete-li přejít k dalšímu kroku kurzu, přečtěte si [článek krok 7: Přidání součástí dialogového okna do formuláře](../ide/step-7-add-dialog-components-to-your-form.md).

- Pokud se chcete vrátit k předchozímu kroku kurzu, přečtěte si [článek 5: Přidání ovládacích prvků do formuláře](../ide/step-5-add-controls-to-your-form.md).
