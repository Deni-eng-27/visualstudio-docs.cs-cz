---
title: Vazba s daty v Návrháři XAML
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- VS.XamlDesigner.DataBinding
dev_langs:
- CSharp
- VB
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 58f83616985556d762ae05a0a97c6263e2e6d7a4
ms.sourcegitcommit: 90c3187d804ad7544367829d07ed4b47d3f8a72d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2019
ms.locfileid: "68821558"
---
# <a name="walkthrough-bind-to-data-in-xaml-designer"></a>Návod: Vazba s daty v Návrháři XAML

V Návrhář XAML můžete nastavit vlastnosti datové vazby pomocí návrhové plochy a okno Vlastnosti. Příklad v tomto návodu ukazuje, jak vytvořit vazby dat k ovládacímu prvku. Konkrétně návod ukazuje, jak vytvořit jednoduchou třídu nákupního košíku s názvem `ItemCount` [DependencyProperty](xref:Windows.UI.Xaml.DependencyProperty) `ItemCount` a pak vytvořit vazby vlastnosti na vlastnost **text** ovládacího prvku [TextBlock](xref:Windows.UI.Xaml.Controls.TextBlock) .

## <a name="to-create-a-class-to-use-as-a-data-source"></a>Vytvoření třídy, která bude použita jako zdroj dat

1. Na **souboru** nabídce zvolte **nový** > **projektu**.

1. V dialogovém **okně Nový projekt** zvolte buď uzel  **C# vizuál** , nebo **Visual Basic** , rozbalte uzel **Windows Desktop** a pak zvolte šablonu **aplikace WPF** .

1. Pojmenujte projekt **BindingTest**a pak klikněte na tlačítko **OK** .

1. Otevřete soubor **MainWindow.XAML.cs** (nebo **MainWindow. vb**) a přidejte následující kód. V C#přidejte kód do `BindingTest` oboru názvů (před poslední pravou závorku v souboru). V Visual Basic stačí přidat novou třídu.

   ```csharp
   public class ShoppingCart : DependencyObject
   {
       public int ItemCount
       {
           get { return (int)GetValue(ItemCountProperty); }
           set { SetValue(ItemCountProperty, value); }
       }

       public static readonly DependencyProperty ItemCountProperty =
            DependencyProperty.Register("ItemCount", typeof(int),
            typeof(ShoppingCart), new PropertyMetadata(0));
   }
   ```

   ```vb
   Public Class ShoppingCart
       Inherits DependencyObject

       Public Shared ReadOnly ItemCountProperty As DependencyProperty = DependencyProperty.Register(
            "ItemCount", GetType(Integer), GetType(ShoppingCart), New PropertyMetadata(0))
       Public Property ItemCount As Integer
           Get
               ItemCount = CType(GetValue(ItemCountProperty), Integer)
           End Get
           Set(value As Integer)
               SetValue(ItemCountProperty, value)
           End Set
       End Property
   End Class
   ```

   Tento kód nastaví hodnotu 0 jako výchozí počet položek pomocí objektu [hodnotu PropertyMetadata](xref:Windows.UI.Xaml.PropertyMetadata) .

1. V nabídce **soubor** klikněte na příkaz **sestavit** > **sestavení řešení**.

## <a name="to-bind-the-itemcount-property-to-a-textblock-control"></a>Svázání vlastnosti vlastnost ItemCount s ovládacím prvkem TextBlock

1. V Průzkumník řešení otevřete místní nabídku pro **MainWindow. XAML** a klikněte na tlačítko **Návrhář zobrazení**.

1. V sadě nástrojů vyberte ovládací prvek [mřížky](xref:Windows.UI.Xaml.Controls.Grid) a přidejte jej do formuláře.

1. Když vyberete, v okno Vlastnosti klikněte na tlačítko **Nový** vedle vlastnosti DataContext. `Grid`

1. V dialogovém okně **Vybrat objekt** se ujistěte, že je zaškrtnuto políčko **Zobrazit všechna sestavení** , zvolte **ShoppingCart** pod oborem názvů **BindingTest** a pak klikněte na tlačítko **OK** .

     Na následujícím obrázku je znázorněno dialogové okno **Vybrat objekt** s vybraným **ShoppingCart** .

     ![Výběr objektu – dialogové okno](../designers/media/blendselectobject.png)

1. V sadě **nástrojů**vyberte `TextBlock` ovládací prvek, který chcete přidat do formuláře.

1. V ovládacím prvku vyberte v okno Vlastnosti značku vlastnosti napravo od vlastnosti text a pak zvolte **vytvořit datovou vazbu**. `TextBlock` (Značka vlastnosti vypadá jako malá box.)

1. V dialogovém okně vytvořit datovou vazbu vyberte v poli **cesta** vlastnost **vlastnost ItemCount: (Int32)** a pak klikněte na tlačítko **OK** .

     Na následujícím obrázku je znázorněno dialogové okno **vytvořit datovou vazbu** s vybranou vlastností **vlastnost ItemCount** .

     ![Dialog vytvořit datovou vazbu – dialogové okno](../designers/media/xaml_create_data_binding.png)

1. Stisknutím klávesy **F5** spusťte aplikaci.

     `TextBlock` Ovládací prvek by měl zobrazit výchozí hodnotu 0 jako text.

## <a name="see-also"></a>Viz také:

- [Vytvoření uživatelského rozhraní pomocí Návrháře XAML](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)
- [Dialogové okno Přidat převaděč hodnot](https://msdn.microsoft.com/library/c5f3d110-a541-4b55-8bca-928f77778af8)