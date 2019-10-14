---
title: 'Krok 6: Pojmenování tlačítkových ovládacích prvků'
ms.date: 08/30/2016
ms.assetid: 56b3baa3-651e-4ad4-8942-e334c5c57158
ms.topic: tutorial
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
dev_langs:
- CSharp
- VB
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 22bc479ccd29a9eaf76e50f630061699856502ea
ms.sourcegitcommit: 034c503ae04e22cf840ccb9770bffd012e40fb2d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306239"
---
# <a name="step-6-name-your-button-controls"></a>Krok 6: Pojmenování tlačítkových ovládacích prvků

Ve formuláři je jen jeden @no__t – 0. Po přidání se rozhraní IDE automaticky jmenuje **pictureBox1**. Existuje pouze jeden <xref:System.Windows.Forms.CheckBox> s názvem **checkBox1**. Brzy napíšete kód a tento kód bude odkazovat na zaškrtávací políčko a PictureBox. Vzhledem k tomu, že existuje pouze jeden z těchto ovládacích prvků, budete znát, co to znamená, když ve svém kódu uvidíte **pictureBox1** nebo **checkBox1** .

> [!TIP]
> V Visual Basic výchozí první písmeno libovolného názvu ovládacího prvku má počáteční zakončení, takže názvy jsou **pictureBox1**, **checkBox1**a tak dále.

Ve formuláři jsou čtyři tlačítka a rozhraní IDE s názvem **Button1**, **Button2**, **Button3**a **Button4**. Pouhým zobrazením jejich aktuálních názvů nevíte, které tlačítko představuje tlačítko **Zavřít** a který je jedním z tlačítek **Zobrazit obrázek** . To je důvod, proč vaše tlačítko ovládá více informativních názvů je užitečné.

## <a name="to-name-your-button-controls"></a>Chcete-li pojmenovat ovládací prvky tlačítka

1. Ve formuláři klikněte na tlačítko **Zavřít** . (Pokud máte stále vybraná všechna tlačítka, kliknutím na klávesu **ESC** výběr zrušte.) Posuňte se v okně **vlastnosti** , dokud se nezobrazí vlastnost **(název)** . (Vlastnost **(Name)** je blízko horní části, pokud jsou vlastnosti seřazené abecedně.) Změňte název na **closeButton**, jak je znázorněno na následujícím snímku obrazovky.

    okno ![Properties s názvem closeButton @ no__t-1<br>Okno ***vlastností*** *s* *názvem* closeButton

    > [!NOTE]
    > Zkuste změnit název tlačítka na **tlačítko Zavřít**s mezerou mezi slovy "Zavřít" a "tlačítko". Když to uděláte, rozhraní IDE zobrazí chybovou zprávu: Hodnota vlastnosti není platná. Mezery (a několik dalších znaků) nejsou povoleny v názvech ovládacích prvků.

1. Přejmenujte další tři tlačítka na **backgroundButton**, **clearButton**a **showButton**.
Názvy můžete ověřit tak, že v okně **vlastnosti** zvolíte rozevírací seznam výběr ovládacího prvku. Nové názvy tlačítek se zobrazí.

1. Dvakrát klikněte na tlačítko **Zobrazit obrázek** ve formuláři. Jako alternativu zvolte na formuláři tlačítko **Zobrazit obrázek** a potom stiskněte klávesu **ENTER** . Když to uděláte, IDE otevře další kartu v hlavním okně s názvem **Form1.cs**. (Pokud používáte Visual Basic, karta má název **Form1. vb**).

   Tato karta zobrazuje soubor kódu za formulářem, jak je znázorněno na následujícím snímku obrazovky.

    karta ![Form1.cs s kódem jazyka&#35; Visual C @ no__t-2<br>
Karta ***Form1.cs*** *s C# kódem*

    > [!NOTE]
    > Karta Form1.cs nebo Form1. vb může místo toho zobrazovat **showButton** jako **showButton** .

1. Zaměřte se na tuto část kódu.

    ```csharp
        private void ShowButton_Click(object sender, EventArgs e)
    {
    }
    ```

    ```vb
        Private Sub showButton_Click() Handles showButton.Click

    End Sub
    ```

   [!INCLUDE [devlang-control](./includes/devlang-control.md)]

   Díváte jste se na kód s názvem `showButton_Click()` (případně `ShowButton_Click()`). Rozhraní IDE bylo přidáno do kódu formuláře při otevření souboru kódu pro tlačítko **showButton** . V době návrhu při otevření souboru kódu pro ovládací prvek ve formuláři se kód vygeneruje pro ovládací prvek, pokud ještě neexistuje. Tento kód, který se označuje jako *Metoda*, se spouští při spuštění aplikace a výběru ovládacího prvku – v tomto případě se **zobrazí tlačítko Zobrazit obrázek** .

1. Zvolte znovu kartu **Návrhář formulářů** (**Form1.cs [Design]** ) a pak otevřete soubor kódu pro tlačítko **Vymazat obrázek** pro vytvoření metody v kódu formuláře. Tento postup opakujte pro zbývající dvě tlačítka. V každém okamžiku rozhraní IDE přidá novou metodu do souboru kódu formuláře.

1. Chcete-li přidat další metodu, otevřete soubor kódu pro ovládací prvek **CheckBox** v **Návrhář formulářů** , aby rozhraní IDE přidalo metodu `checkBox1_CheckedChanged()`. Tato metoda je volána vždy, když uživatel vybere nebo zruší zaškrtnutí políčka.

   > [!TIP]
   > Při práci na aplikaci se často přesouváte mezi editorem kódu a **Návrhář formulářů**. Rozhraní IDE usnadňuje navigaci v projektu. Pomocí **Průzkumník řešení** otevřít **Návrhář formulářů** dvojím kliknutím na *Form1.cs* v C# nebo *Form1. vb* v Visual Basic nebo na řádku nabídek vyberte možnost **Zobrazit** **Návrháře** > .

    Následující příklad ukazuje nový kód, který se zobrazí v editoru kódu.

    [!code-csharp[VbExpressTutorial1Step6_#2](../ide/codesnippet/CSharp/step-6-name-your-button-controls_2.cs)]

    [!code-vb[VbExpressTutorial1Step6_#2](../ide/codesnippet/VisualBasic/step-6-name-your-button-controls_2.vb)]

    > [!NOTE]
    > Váš kód nemusí zobrazit obslužné rutiny událostí ve camelCase písmenech.

    Pět metod, které jste přidali, se nazývají *obslužné rutiny událostí*, protože vaše aplikace je volá vždy, když dojde k události (jako je například uživatel výběr tlačítka nebo výběru pole).

    Při zobrazení kódu pro ovládací prvek v rozhraní IDE v době návrhu, Visual Studio přidá metodu obslužné rutiny události pro ovládací prvek, pokud žádný není. Například když dvakrát kliknete na tlačítko, rozhraní IDE přidá obslužnou rutinu události pro svou událost <xref:System.Windows.Forms.Control.Click> (která je volána vždy, když uživatel zvolí tlačítko). Když dvakrát kliknete na zaškrtávací políčko, rozhraní IDE přidá obslužnou rutinu události pro svou událost <xref:System.Windows.Forms.CheckBox.CheckedChanged> (která je volána vždy, když uživatel vybere nebo zruší pole).

    Po přidání obslužné rutiny události pro ovládací prvek se k němu můžete kdykoli vrátit z **Návrhář formulářů** dvojitým kliknutím na ovládací prvek nebo na řádku nabídek, výběrem možnosti **Zobrazit** > **kód**.

    Názvy jsou důležité při sestavování programů a metody (včetně obslužných rutin událostí) můžou mít libovolný název, který chcete. Když přidáte obslužnou rutinu události s rozhraním IDE, vytvoří se název založený na názvu ovládacího prvku a události, která je zpracovávána.

    Například událost Click pro tlačítko s názvem **showButton** se nazývá metoda obslužné rutiny události `showButton_Click()` (nebo `ShowButton_Click()`). Také se otevírají a uzavírající závorky `()` obvykle přidávají za názvem metody, které označují, že se metody diskutuje.

    Pokud se rozhodnete, že chcete změnit název proměnné kódu, klikněte pravým tlačítkem na proměnnou v kódu a pak zvolte **refaktoring** > **Přejmenovat**. Všechny instance této proměnné v kódu jsou přejmenovány. Další informace najdete v tématu [refaktoringu přejmenování](../ide/reference/rename.md).

## <a name="next-steps"></a>Další kroky

* Pokud chcete přejít na další krok kurzu, přečtěte si téma ** @ no__t-1Step 7: Přidejte součásti dialogového okna do formuláře @ no__t-0 @ no__t-1.

* Pokud se chcete vrátit k předchozímu kroku kurzu, přečtěte si téma [Step 5: Přidejte ovládací prvky do formuláře @ no__t-0.

## <a name="see-also"></a>Viz také:

* [Kurz 2: Vytvoření časovaného matematického kvízu @ no__t-0
* [Kurz 3: Vytvoření vyhovující hry @ no__t-0
