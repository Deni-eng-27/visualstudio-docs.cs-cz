---
title: Stránky možností a možností | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Tools Options pages [Visual Studio SDK], managed package framework support
- managed package framework, Tools Options pages support
- support, Tools Options pages
- Tools Options pages [Visual Studio SDK], layouts
- Tools Options pages [Visual Studio SDK], attributes
ms.assetid: e6c0e636-5ec3-450e-b395-fc4bb9d75918
caps.latest.revision: 35
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 4512867f636e2362aa28d52c5af28bf8eb9697f9
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "75851154"
---
# <a name="options-and-options-pages"></a>Možnosti a stránky Možnosti
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Kliknutím na **Možnosti** v nabídce **nástroje** otevřete dialogové okno **Možnosti** . Možnosti v tomto dialogovém okně se souhrnně označují jako stránky možností. Ovládací prvek strom v navigačním podokně obsahuje kategorie možností a každá kategorie obsahuje stránky možností. Když vyberete stránku, zobrazí se její možnosti v pravém podokně. Tyto stránky umožňují změnit hodnoty možností, které určují stav balíčku VSPackage.  
  
## <a name="support-for-options-pages"></a>Podpora pro stránky možností  
 <xref:Microsoft.VisualStudio.Shell.Package>Třída poskytuje podporu pro vytváření stránek možností a kategorií možností. <xref:Microsoft.VisualStudio.Shell.DialogPage>Třída implementuje stránku možností.  
  
 Výchozí implementace <xref:Microsoft.VisualStudio.Shell.DialogPage> nabídky nabízí veřejné vlastnosti pro uživatele v obecné mřížce vlastností. Toto chování můžete přizpůsobit přepsáním různých metod na stránce a vytvořením vlastní stránky možnosti, která má vlastní uživatelské rozhraní (UI). Další informace najdete v tématu [Vytvoření stránky možností](../../extensibility/creating-an-options-page.md).  
  
 <xref:Microsoft.VisualStudio.Shell.DialogPage>Třída implementuje <xref:Microsoft.VisualStudio.Shell.IProfileManager> , která poskytuje stálost pro stránky možností a také pro uživatelská nastavení. Výchozí implementace <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromStorage%2A> <xref:Microsoft.VisualStudio.Shell.IProfileManager.SaveSettingsToStorage%2A> metod a trvalé změny vlastností v registru, pokud je možné vlastnost převést na nebo z řetězce.  
  
## <a name="options-page-registry-path"></a>Možnosti cesty k registru stránky možností  
 Ve výchozím nastavení se cesta registru vlastností spravovaných pomocí stránky možnosti určuje kombinací <xref:Microsoft.VisualStudio.Shell.Package.UserRegistryRoot%2A> , slovem třídy DialogPage a názvem typu třídy stránky možnosti. Například třída stránky možnosti může být definována následujícím způsobem.  
  
 [!code-csharp[VSSDKSupportForOptionsPages#1](../../snippets/csharp/VS_Snippets_VSSDK/vssdksupportforoptionspages/cs/vssdksupportforoptionspagespackage.cs#1)]
 [!code-vb[VSSDKSupportForOptionsPages#1](../../snippets/visualbasic/VS_Snippets_VSSDK/vssdksupportforoptionspages/vb/vssdksupportforoptionspagespackage.vb#1)]  
  
 Pokud <xref:Microsoft.VisualStudio.Shell.Package.UserRegistryRoot%2A> je HKEY_CURRENT_USER \software\microsoft\visualstudio\8.0Exp, pak dvojice název vlastnosti a hodnota jsou podklíče HKEY_CURRENT_USER \software\microsoft\visualstudio\8.0exp\dialogpage\company.optionsPage.OptionsPageGeneral.  
  
 Cesta registru samotné stránky možností je určena kombinací <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A> , slovem, ToolsOptionsPages a kategoriemi a názvem stránky možností. Pokud má například stránka vlastní možnosti kategorii, moji stránku možností a <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A> je HKEY_LOCAL_MACHINE \software\microsoft\visualstudio\8.0Exp, pak stránka Options obsahuje klíč registru HKEY_LOCAL_MACHINE \Software\microsoft\visualstudio\8.0Exp\ToolsOptionsPages\My možnost Pages\Custom.  
  
## <a name="toolsoptions-page-attributes-and-layout"></a>Nástroje a možnosti – atributy a rozložení stránky  
 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute>Atribut určuje seskupení stránek vlastních možností do kategorií v navigační stromové struktuře dialogového okna **Možnosti** . <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute>Atribut přidruží stránku možností ke VSPackage, který poskytuje rozhraní. Předpokládejme následující fragment kódu:  
  
 [!code-csharp[VSSDKSupportForOptionsPages#2](../../snippets/csharp/VS_Snippets_VSSDK/vssdksupportforoptionspages/cs/vssdksupportforoptionspagespackage.cs#2)]
 [!code-vb[VSSDKSupportForOptionsPages#2](../../snippets/visualbasic/VS_Snippets_VSSDK/vssdksupportforoptionspages/vb/vssdksupportforoptionspagespackage.vb#2)]  
  
 Tato deklarace deklaruje, že MyPackage poskytuje dvě stránky možností, OptionsPageGeneral a OptionsPageCustom. V dialogovém okně **Možnosti** se obě stránky možností zobrazují v kategorii **Moje stránky** možností jako **Obecné** a **vlastní**.  
  
## <a name="option-attributes-and-layout"></a>Atributy a rozložení možností  
 Uživatelské rozhraní (UI), které stránka poskytuje, určuje vzhled možností na stránce s vlastními možnostmi. Rozložení, popisky a popis možností na stránce Obecné možnosti jsou určeny následujícími atributy:  
  
- <xref:System.ComponentModel.CategoryAttribute> Určuje kategorii možnosti.  
  
- <xref:System.ComponentModel.DisplayNameAttribute> Určuje zobrazovaný název možnosti.  
  
- <xref:System.ComponentModel.DescriptionAttribute> Určuje popis možnosti.  
  
  > [!NOTE]
  > Ekvivalentní atributy, SRCategory, LocDisplayName a SRDescription, používají řetězcové prostředky pro lokalizaci a jsou definovány v [ukázce spravovaného projektu](https://msdn.com/vsx).  
  
  Předpokládejme následující fragment kódu:  
  
  [!code-csharp[VSSDKSupportForOptionsPages#3](../../snippets/csharp/VS_Snippets_VSSDK/vssdksupportforoptionspages/cs/optionspagecustom.cs#3)]
  [!code-vb[VSSDKSupportForOptionsPages#3](../../snippets/visualbasic/VS_Snippets_VSSDK/vssdksupportforoptionspages/vb/optionspagegeneral.vb#3)]  
  
  Možnost OptionInteger se zobrazí na stránce možnosti jako **typ Integer** v kategorii **Moje možnosti** . Pokud je vybraná možnost, zobrazí se v poli Popis možnost popis, **Moje celočíselná hodnota**.  
  
## <a name="accessing-options-pages-from-another-vspackage"></a>Přístup ke stránkám možností z jiného balíčku VSPackage  
 VSPackage, který hostuje a spravuje stránku možností, lze programově přistupovat z jiného VSPackage pomocí modelu automatizace. Například v následujícím kódu je VSPackage zaregistrován jako hostující stránka možností.  
  
 [!code-csharp[VSSDKSupportForOptionsPages#4](../../snippets/csharp/VS_Snippets_VSSDK/vssdksupportforoptionspages/cs/vssdksupportforoptionspagespackage.cs#4)]
 [!code-vb[VSSDKSupportForOptionsPages#4](../../snippets/visualbasic/VS_Snippets_VSSDK/vssdksupportforoptionspages/vb/vssdksupportforoptionspagespackage.vb#4)]  
  
 Následující fragment kódu získá hodnotu OptionInteger z MyOptionPage:  
  
 [!code-csharp[VSSDKSupportForOptionsPages#5](../../snippets/csharp/VS_Snippets_VSSDK/vssdksupportforoptionspages/cs/vssdksupportforoptionspagespackage.cs#5)]
 [!code-vb[VSSDKSupportForOptionsPages#5](../../snippets/visualbasic/VS_Snippets_VSSDK/vssdksupportforoptionspages/vb/vssdksupportforoptionspagespackage.vb#5)]  
  
 Když <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> atribut zaregistruje stránku možností, je stránka registrována v klíči vlastnosti automatizace, pokud `SupportsAutomation` je argument atributu `true` . Automatizace prověřuje tuto položku registru za účelem nalezení přidruženého VSPackage a Automation pak přistupuje k vlastnosti prostřednictvím stránky hostované možnosti, v tomto případě na stránce mřížka.  
  
 Cesta k registru vlastnosti Automation je určena kombinací <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A> , slovem, vlastnosti automatizace a kategoriemi a názvem stránky možností. Pokud má například stránka Možnosti kategorii Moje kategorie, název stránky moje mřížka a <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A> HKEY_LOCAL_MACHINE \software\microsoft\visualstudio\8.0Exp, pak má vlastnost Automation klíč registru HKEY_LOCAL_MACHINE stránku Category\My gridu \software\microsoft\visualstudio\8.0Exp\AutomationProperties\My.  
  
> [!NOTE]
> Stránka kanonický název, my Category.My Grid, je hodnota podklíče názvu tohoto klíče.
