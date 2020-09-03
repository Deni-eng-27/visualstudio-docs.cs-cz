---
title: Datová vazba WPF s přehledem LINQ to XML | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 3bf80845-891b-41de-a71b-4080b5bd3ea6
caps.latest.revision: 5
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: c0cbd93f2d32c06ba52b2c47c1af8f326948609a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "75843931"
---
# <a name="wpf-data-binding-with-linq-to-xml-overview"></a>Přehled datové vazby WPF s LINQ to XML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V tomto tématu se seznámíte s funkcemi dynamické vazby dat v <xref:System.Xml.Linq> oboru názvů. Tyto funkce lze použít jako zdroj dat pro prvky uživatelského rozhraní (UI) v Windows Presentation Foundation (WPF).

## <a name="xaml-and-linq-to-xml"></a>XAML a LINQ to XML
 Jazyk Extensible Application Markup Language (XAML) (XAML) je dialekt XML vytvořený Microsoftem za účelem podpory technologií .NET Framework 3,0. Používá se v WPF k vyjádření prvků uživatelského rozhraní a souvisejících funkcí, jako jsou události a datové vazby. V programovací model Windows Workflow Foundation se XAML používá pro reprezentaci struktury programu, například řízení programu (*pracovní postupy*). XAML umožňuje, aby byly deklarativní aspekty technologie odděleny od souvisejícího procedurálního kódu, který definuje více individuální chování programu.

 Existují dva široké způsoby, kterými může XAML a LINQ to XML interagovat:

- Vzhledem k tomu, že soubory XAML jsou ve správném formátu XML, mohou být dotazovány a manipulovány prostřednictvím technologií XML, jako je LINQ to XML.

- Vzhledem k tomu, že LINQ to XML dotazy reprezentují zdroj dat, lze tyto dotazy použít jako zdroj dat pro datovou vazbu pro prvky uživatelského rozhraní WPF.

  Tato dokumentace popisuje druhý scénář.

## <a name="data-binding-in-the-windows-presentation-foundation"></a>Datová vazba v Windows Presentation Foundation
 Datová vazba WPF umožňuje prvku uživatelského rozhraní přidružit jednu z jejích vlastností ke zdroji dat. Jednoduchým příkladem je, že <xref:System.Windows.Controls.Label> text představuje hodnotu veřejné vlastnosti v uživatelsky definovaném objektu. Datová vazba WPF spoléhá na následující komponenty:

|Komponenta|Popis|
|---------------|-----------------|
|Cíl vazby|Prvek uživatelského rozhraní, který má být přidružen ke zdroji dat. Vizuální prvky v subsystému WPF jsou odvozeny z <xref:System.Windows.UIElement> třídy.|
|Cílová vlastnost|*Vlastnost závislosti* cíle vazby, která odráží hodnotu zdroje vazby dat. Vlastnosti závislosti jsou přímo podporovány <xref:System.Windows.DependencyObject> třídou, která <xref:System.Windows.UIElement> je odvozena z.|
|Zdroj vazby|Zdrojový objekt pro jednu nebo více hodnot, které jsou zadány do prvku uživatelského rozhraní pro prezentaci. WPF automaticky podporuje následující typy jako vazby zdrojů: objekty CLR, ADO.NET datové objekty, data XML (z XPath nebo LINQ to XML dotazů) nebo jiné <xref:System.Windows.DependencyObject> .|
|Zdrojová cesta|Vlastnost zdroje vazby, která se překládá na hodnotu nebo sadu hodnot, které mají být vázány.|

 Vlastnost závislosti je koncept specifický pro WPF, který představuje dynamicky vypočítanou vlastnost prvku uživatelského rozhraní. Například vlastnosti závislosti mají často výchozí hodnoty nebo hodnoty, které jsou poskytovány nadřazeným prvkem. Tyto speciální vlastnosti jsou zálohovány instancemi <xref:System.Windows.DependencyProperty> třídy (a nikoli polí jako se standardními vlastnostmi). Další informace najdete v tématu [Přehled vlastností závislosti](https://msdn.microsoft.com/library/d119d00c-3afb-48d6-87a0-c4da4f83dee5).

### <a name="dynamic-data-binding-in-wpf"></a>Dynamická datová vazba v subsystému WPF
 Ve výchozím nastavení se datové vazby projeví pouze v případě, že je inicializován cílový prvek uživatelského rozhraní. Tato metoda se nazývá *jednorázová* vazba. Pro většinu účelů to není dostačující. řešení vázání dat obvykle vyžaduje, aby se změny dynamicky rozšířily v době běhu pomocí jednoho z následujících postupů:

- *Jednosměrná* vazba způsobí, že se změny na jedné straně šíří automaticky. Nejčastěji se změny zdroje projeví v cíli, ale v některých případech může být tato změna užitečná.

- V *obousměrné* vazbě se změny zdroje automaticky rozšíří do cíle a změny cíle se automaticky rozšíří do zdroje.

  Aby mohlo dojít k jednosměrné nebo obousměrné vazbě, musí zdroj implementovat mechanismus pro oznamování změn, například implementací <xref:System.ComponentModel.INotifyPropertyChanged> rozhraní nebo pomocí *PropertyNameChanged* vzoru pro každou podporovanou vlastnost.

  Další informace o datové vazbě v subsystému WPF naleznete v tématu [datová vazba (WPF)](https://msdn.microsoft.com/library/90f79b97-17e7-40d1-abf0-3ba600ad1d7e).

## <a name="dynamic-properties-in-linq-to-xml-classes"></a>Dynamické vlastnosti v třídách LINQ to XML
 Většina tříd LINQ to XML nesplňuje správné dynamické zdroje dat WPF: některé z nejužitečnějších informací jsou k dispozici pouze prostřednictvím metod (a nikoli vlastností) a vlastnosti v těchto třídách neimplementují upozornění na změny. Aby bylo možné podporovat datovou vazbu WPF, LINQ to XML zpřístupňuje sadu *dynamických vlastností*.

 Tyto dynamické vlastnosti jsou speciální vlastnosti běhu, které duplikují funkce existujících metod a vlastností v <xref:System.Xml.Linq.XAttribute> <xref:System.Xml.Linq.XElement> třídách a. Byly přidány do těchto tříd pouze v případě, že jim umožní působit jako dynamické zdroje dat pro WPF. Aby bylo možné splnit tuto potřebu, všechny tyto dynamické vlastnosti implementují oznámení o změnách. Podrobný odkaz na tyto dynamické vlastnosti je k dispozici v další části [LINQ to XML dynamické vlastnosti](../designers/linq-to-xml-dynamic-properties.md).

> [!NOTE]
> Mnohé ze standardních veřejných vlastností, které se nacházejí v různých třídách v <xref:System.Xml.Linq> oboru názvů, lze použít pro jednorázovou datovou vazbu. Mějte ale na paměti, že ani zdroj ani cíl se v rámci tohoto schématu dynamicky neaktualizuje.

### <a name="accessing-dynamic-properties"></a>Přístup k dynamickým vlastnostem
 Dynamické vlastnosti v <xref:System.Xml.Linq.XAttribute> <xref:System.Xml.Linq.XElement> třídách a nelze použít jako standardní vlastnosti. Například v jazycích, které odpovídají CLR, jako je C#, nemůže být:

- Přistupujte přímo v době kompilace. Dynamické vlastnosti jsou pro kompilátor a Visual Studio IntelliSense neviditelné.

- Zjištěné nebo dostupné v době běhu pomocí reflexe .NET Dokonce i v době běhu nejsou ve smyslu základního CLR k dispozici žádné vlastnosti.

  V jazyce C# mohou být dynamické vlastnosti k dispozici pouze v době běhu prostřednictvím funkcí poskytovaných <xref:System.ComponentModel> oborem názvů.

  Na rozdíl od dynamických vlastností zdroje XML je však k dispozici prostřednictvím jednoduchého zápisu v následujícím tvaru:

```
<object>.<dynamic-property>
```

 Dynamické vlastnosti těchto dvou tříd buď přeložit na hodnotu, kterou lze použít přímo, nebo na indexer, který musí být dodán s indexem pro získání výsledné hodnoty nebo kolekce hodnot. Druhá syntaxe má podobu:

```
<object>.<dynamic-property>[<index-value>]
```

 Další informace najdete v tématu [LINQ to XML dynamické vlastnosti](../designers/linq-to-xml-dynamic-properties.md).

 Chcete-li implementovat dynamickou vazbu WPF, budou dynamické vlastnosti použity v zařízeních poskytovaných <xref:System.Windows.Data> oborem názvů, zejména <xref:System.Windows.Data.Binding> třídou.

## <a name="see-also"></a>Viz také
 [Datová vazba WPF s LINQ to XML](../designers/wpf-data-binding-with-linq-to-xml.md) [LINQ to XML dynamické vlastnosti](../designers/linq-to-xml-dynamic-properties.md) [XAML ve](https://msdn.microsoft.com/library/5d858575-a83b-42df-ad3f-047ed2d6e3c8) [vazbě dat WPF (WPF)](https://msdn.microsoft.com/library/90f79b97-17e7-40d1-abf0-3ba600ad1d7e) [pomocí značek pracovního postupu](https://msdn2.microsoft.com/library/ms735921(vs.90).aspx)
