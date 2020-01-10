---
title: Okno nástrojů
ms.date: 01/18/2018
ms.topic: reference
f1_keywords:
- vs.toolbox.general
- vs.toolbox
helpviewer_keywords:
- Toolbox [Visual Studio]
- custom controls [Visual Studio]
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c7decdb80cd06b1af3230b2926c4ebd37b48e422
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/01/2020
ms.locfileid: "75596447"
---
# <a name="toolbox"></a>Sada nástrojů

Okno **panelu nástrojů** zobrazuje ovládací prvky, které lze přidat do projektů aplikace Visual Studio. Chcete-li otevřít sadu nástrojů, klikněte v nabídce **zobrazení** na příkaz **Sada nástrojů** .

![Okno nástrojů](media/toolbox.png)

Můžete přetáhnout a vyřadit různé ovládací prvky na povrch návrháře používáte a změnit velikost a umístění ovládacích prvků.

Ve spojení s návrháře zobrazení, například jako zobrazení návrháře XAML souboru, zobrazí se panel nástrojů. **Sada nástrojů** zobrazuje pouze ovládací prvky, které lze použít v aktuálním návrháři. Můžete hledat v **sadě nástrojů** a dále filtrovat položky, které se zobrazí.

> [!NOTE]
> U některých typů projektů nemusí **Sada nástrojů** zobrazit žádné položky.

Verze rozhraní .NET, na kterou projekt cílí, také ovlivňuje sadu ovládacích prvků viditelných v sadě nástrojů. V případě potřeby můžete změnit cílovou verzi rozhraní .NET Framework ze stránek vlastností projektu. Vyberte uzel projektu v **Průzkumník řešení**a pak na panelu nabídek zvolte vlastnosti **projekt** > **ProjectName**. Na kartě **aplikace** použijte rozevírací seznam **cílové rozhraní** .

## <a name="manage-the-toolbox-window-and-its-controls"></a>Správa oken nástrojů a jejích ovládacích prvků

Ve výchozím nastavení je **panel nástrojů** sbalen na levou stranu integrovaného vývojového prostředí (IDE) sady Visual Studio a zobrazí se, když je kurzor přesunut. **Panel nástrojů** můžete připnout (kliknutím na ikonu **připnutí** na panelu nástrojů), takže zůstane otevřený při přesunu kurzoru. Můžete také uvolnit okno **panelu nástrojů** a přetáhnout ho kamkoli na obrazovku. **Panel nástrojů** můžete ukotvit, uvolnit a skrýt tak, že kliknete pravým tlačítkem myši na jeho panel nástrojů a vyberete jednu z možností.

Můžete změnit uspořádání položek na kartě **panelu nástrojů** nebo přidat vlastní karty a položky pomocí následujících příkazů v místní nabídce, která se zobrazí po kliknutí pravým tlačítkem myši:

- **Přejmenovat položku** – Přejmenuje vybranou položku.

- **Zobrazit vše** – zobrazí všechny možné ovládací prvky (nikoli pouze ty, které se vztahují k aktuálnímu návrháři).

- **Zobrazení seznamu** – zobrazí ovládací prvky ve svislém seznamu. Pokud není zaškrtnuto, zobrazí ovládací prvky vodorovně.

- **Zvolit položky** – otevře dialogové okno **zvolit položky sady nástrojů** , ve kterém můžete určit položky, které se zobrazí v **sadě nástrojů**. Můžete zobrazit nebo skrýt položku zaškrtnutím nebo zrušením zaškrtnutí jejího políčka.

- **Seřadit položky abecedně** – Seřadí položky podle názvu.

- **Resetovat panel nástrojů** – obnoví výchozí nastavení a položky **sady nástrojů** .

- **Přidat tabulátor** – přidá novou kartu **panelu nástrojů** .

- **Nahoru – přesune** vybranou položku nahoru.

- **Přesunout dolů** – Přesune vybranou položku dolů.

## <a name="create-and-distribute-custom-toolbox-controls"></a>Vytvoření a distribuce vlastních ovládacích prvků nástrojů

Můžete vytvořit vlastní ovládací prvky **sady nástrojů** , počínaje buď se šablonou projektu založenou na [Windows Presentation Foundation](../../extensibility/creating-a-wpf-toolbox-control.md) nebo na [model Windows Forms](../../extensibility/creating-a-windows-forms-toolbox-control.md). Vlastní ovládací prvek pak můžete distribuovat do svého ostatními týmuu nebo ho publikovat na webu pomocí [instalačního programu ovládacích prvků sady nástrojů](https://download.microsoft.com/download/8/3/6/836657BD-9CCB-4ED4-B9D2-FB769473B284/TCI_whitepaper.docx).

## <a name="help-on-toolbox-tabs"></a>Nápověda k karty panelu nástrojů

Následující témata obsahují další informace o některých dostupných kartách **sady nástrojů** :

- [Panel nástrojů, karta Data](../../ide/reference/toolbox-data-tab.md)
- [Panel nástrojů, karta Součásti](../../ide/reference/toolbox-components-tab.md)
- [Panel nástrojů, karta HTML](../../ide/reference/toolbox-html-tab.md)

## <a name="see-also"></a>Viz také:

- [Zvolit položky panelu nástrojů, komponenty WPF](choose-toolbox-items-wpf-components.md)
