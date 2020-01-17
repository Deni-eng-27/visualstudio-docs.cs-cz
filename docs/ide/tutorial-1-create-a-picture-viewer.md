---
title: 'Kurz 1: vytvoření prohlížeče obrázků'
ms.date: 10/16/2019
ms.assetid: 3071d6df-2b2f-4e95-ab68-bef727323136
ms.topic: tutorial
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f9af5a3e8796af3aeaefae569d61e78a1039d84e
ms.sourcegitcommit: f3f668ecaf11b4c2738ebc91923c6b5e38e74670
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2020
ms.locfileid: "76115090"
---
# <a name="tutorial-1-create-a-picture-viewer"></a>Kurz 1: vytvoření prohlížeče obrázků

V tomto kurzu sestavíte aplikaci, která načte obrázek ze souboru a zobrazí se v okně. Naučíte se, jak pomocí **Návrhář formulářů** přetahovat ovládací prvky jako tlačítka a pole obrázků do formuláře, nastavit jejich vlastnosti a plynule změnit velikost formuláře pomocí kontejnerů. Můžete také začít psát kód.

> [!NOTE]
> Tento kurz se zabývá C# i Visual Basic, takže se zaměřte na informace, které jsou specifické pro programovací jazyk, který používáte.

Tento kurz vás provede následujícími úlohami:

* Vytvořte nový projekt.

* Otestujte (Ladit) aplikaci.

* Přidejte základní ovládací prvky, jako jsou zaškrtávací políčka a tlačítka, do formuláře.

* Umístěte ovládací prvky na formulář pomocí rozložení.

* Přidejte dialogová okna **otevřít soubor** a **barev** do formuláře.

* Pište kód pomocí technologie IntelliSense a fragmenty kódu.

* Zapište metody obslužné rutiny události.

Až skončíte, aplikace by měla vypadat podobně jako na následujícím obrázku:

![Aplikace pro prohlížeč obrázků, kterou vytvoříte v tomto kurzu](../ide/media/express_pictureviewerdone.png)

## <a name="tutorial-links"></a>Odkazy na kurz

|Název|Popis|
|-----------|-----------------|
|[Krok 1: vytvoření projektu aplikace model Windows Forms](../ide/step-1-create-a-windows-forms-application-project.md)|Začněte vytvořením projektu aplikace model Windows Forms.|
|[Krok 2: spuštění aplikace pro prohlížeč obrázků](../ide/step-2-run-your-program.md)|Spusťte projekt aplikace model Windows Forms, který jste vytvořili v předchozím kroku.|
|[Krok 3: nastavení vlastností formuláře](../ide/step-3-set-your-form-properties.md)|Změňte vzhled formuláře pomocí okna **vlastnosti** .|
|[Krok 4: rozložení formuláře pomocí ovládacího prvku TableLayoutPanel](../ide/step-4-lay-out-your-form-with-a-tablelayoutpanel-control.md)|Přidejte ovládací prvek `TableLayoutPanel` do formuláře.|
|[Krok 5: Přidání ovládacích prvků do formuláře](../ide/step-5-add-controls-to-your-form.md)|Do formuláře přidejte ovládací prvky, například ovládací prvek `PictureBox` a ovládací prvek `CheckBox`. Přidejte tlačítka do formuláře.|
|[Krok 6: Pojmenujte své ovládací prvky tlačítek](../ide/step-6-name-your-button-controls.md)|Přejmenujte tlačítka na smysluplnější.|
|[Krok 7: přidejte do svého formuláře komponenty dialogových oken](../ide/step-7-add-dialog-components-to-your-form.md)|Přidejte komponentu `OpenFileDialog` a `ColorDialog` komponentu do formuláře.|
|[Krok 8: Zapište kód pro obslužnou rutinu události zobrazit tlačítko obrázku](../ide/step-8-write-code-for-the-show-a-picture-button-event-handler.md)|Pište kód pomocí nástroje IntelliSense.|
|[Krok 9: kontrola, komentář a testování kódu](../ide/step-9-review-comment-and-test-your-code.md)|Zkontrolujte a otestujte svůj kód. Přidejte komentáře podle potřeby.|
|[Krok 10: napište kód pro další tlačítka a zaškrtávací políčko](../ide/step-10-write-code-for-additional-buttons-and-a-check-box.md)|Napíšete kód pro nastavení dalších tlačítek a zaškrtávací políčko v práci pomocí technologie IntelliSense.|
|[Krok 11: spuštění aplikace a vyzkoušení dalších funkcí](../ide/step-11-run-your-program-and-try-other-features.md)|Spusťte aplikaci a nastavte barvu pozadí. Vyzkoušejte jiné funkce, jako je například změna barev, písem a ohraničení.|

K dispozici jsou také skvělé a bezplatné studijní materiály pro video. Další informace o programování v C#nástroji najdete v tématu [ C# základy: vývoj pro absolutní začátečníky](https://channel9.msdn.com/Series/C-Sharp-Fundamentals-Development-for-Absolute-Beginners). Další informace o programování v Visual Basic najdete v tématu [Visual Basic základy: vývoj pro absolutní začátečníky](https://channel9.msdn.com/Series/Visual-Basic-Development-for-Absolute-Beginners).

## <a name="next-steps"></a>Další kroky

Chcete-li začít s kurzem, začněte v **[kroku 1: vytvoření projektu aplikace model Windows Forms](../ide/step-1-create-a-windows-forms-application-project.md)** .

## <a name="see-also"></a>Viz také:

* [Další C# kurzy](/visualstudio/get-started/csharp/)
* [Kurzy Visual Basic](/visualstudio/get-started/visual-basic/)
* [C++výuka](/cpp/get-started/tutorial-console-cpp)
