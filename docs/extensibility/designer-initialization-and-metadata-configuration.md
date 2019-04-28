---
title: Inicializace návrháře a konfigurace metadat | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- designers [Visual Studio SDK], initializing
- designers [Visual Studio SDK], configuring metadata
ms.assetid: f7fe9a7e-f669-4642-ad5d-186b2e6e6ec9
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4ed1852780e8045f298ed30f10ace5d971776294
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62864082"
---
# <a name="designer-initialization-and-metadata-configuration"></a>Návrháře konfigurace inicializace a metadat

Manipulace s metadata a filtrování atributů přiřazených pomocí návrháře nebo součástí návrháře poskytuje mechanismus pro aplikace definovat, jaké nástroje jsou používány konkrétní návrháře pro zpracování různých <xref:System.Type> objektů (například datové struktury třídy, nebo grafické entity), když je k dispozici návrháře a konfigurace integrovaném vývojovém prostředí sady Visual Studio pro podporu návrháře (pro instanci, která **nástrojů** kategorie nebo karta je k dispozici).

[!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] Poskytuje několik mechanismů, aby se usnadnilo řízení Inicializace návrháře nebo součástí návrháře a manipulaci s jeho metadata službou VSPackage.

## <a name="initialize-metadata-and-configuration-information"></a>Inicializace metadat a informace o konfiguraci
 Protože jsou načteny na vyžádání, rozšíření VSPackages nemusí byly načteny prostředí sady Visual Studio před instance návrháře. Proto nelze použít standardní mechanismus konfigurace Návrhář nebo návrháře komponenty pro vytváření, což je pro zpracování rozšíření VSPackages <xref:System.ComponentModel.Design.IDesignerEventService.DesignerCreated> událostí. Místo toho VSPackage implementuje instance <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension> rozhraní a registruje sama sebe poskytnout vlastní úpravy, označované jako rozšíření povrchu návrhu.

### <a name="customize-initialization"></a>Přizpůsobení inicializace

Přizpůsobení návrháře, komponenty nebo plochu návrháře zahrnuje:

1. Úprava metadata návrháře a efektivně mění způsob, jakým určitým <xref:System.Type> je nedostupná nebo převést.

    To se obvykle provádí prostřednictvím <xref:System.Drawing.Design.UITypeEditor> nebo <xref:System.ComponentModel.TypeConverter> mechanismy.

    Například, když <xref:System.Windows.Forms>-založené na návrháři jsou inicializovány, prostředí Visual Studio upraví <xref:System.Drawing.Design.UITypeEditor> pro <xref:System.Web.UI.WebControls.Image> objekty používané pomocí návrháře pro použití resource Manageru k získání rastrové obrázky, spíše než v systému souborů.

2. Integrace s prostředím, například přihlášení k odběru událostí nebo získávání informací o konfiguraci projektu. Můžete získat informace o konfiguraci projektu a přihlášení k odběru událostí prostřednictvím provedeného <xref:System.ComponentModel.Design.ITypeResolutionService> rozhraní.

3. Změny uživatelského prostředí aktivací odpovídající **nástrojů** kategorií nebo omezení použitelnosti návrháře použitím instance <xref:System.ComponentModel.ToolboxItemFilterAttribute> třídy do návrháře.

### <a name="designer-initialization-by-a-vspackage"></a>Inicializace návrháře pomocí VSPackage

VSPackage partnerova návrháře inicializace:

1. Vytváří se implementaci objektu <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension> třídy.

   > [!NOTE]
   > <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension> Třída by měla být implementována nikdy na stejný objekt jako <xref:Microsoft.VisualStudio.Shell.Package> třídy.

2. Probíhá registrace třídy, která implementuje <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension> jako poskytují podporu pro rozšíření návrháře sady VSPackage. Registrace s použitím instance třídy <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtensionAttribute>, <xref:Microsoft.VisualStudio.Shell.ProvideObjectAttribute>, a <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> do třídy, která poskytuje implementaci sady VSPackage <xref:Microsoft.VisualStudio.Shell.Package>.

Vždy, když Návrhář nebo součástí návrháře se vytvoří, prostředí Visual Studio:

- Přistupuje k každý poskytovatel surface rozšíření vzoru.

- Vytvoří a inicializuje instanci poskytovatele každý návrhové plochy rozšíření <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension> objektu.

- Každý poskytovatel rozšíření povrchu návrhu volá <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension.OnDesignerCreated%2A> metoda nebo <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension.OnComponentCreated%2A> – metoda (podle potřeby).

Při implementaci <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension> objektu jako člena sady VSPackage, je důležité si uvědomit, že:

- Prostředí sady Visual Studio neposkytuje žádné kontrolu nad metadat jaký nebo jiná nastavení konfigurace a konkrétní `DesignSurfaceExtension` upraví poskytovatele. Je možné pro dva nebo více `DesignSurfaceExtension` poskytovatelé úpravy stejné funkce Návrhář konfliktní způsoby s finální úpravy se konečná. Že je neurčité, které změna naposledy provedena.

- Je možné explicitně omezit implementace <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension> objekt konkrétní návrháři použitím instance <xref:System.ComponentModel.ToolboxItemFilterAttribute> pro tuto implementaci. Další informace o **nástrojů** položky filtrování, najdete v článku <xref:System.ComponentModel.ToolboxItemFilterAttribute> a <xref:System.ComponentModel.ToolboxItemFilterType>.

## <a name="additional-metadata-provisioning"></a>Zřízení dalších metadat

VSPackage můžete změnit konfiguraci Návrhář nebo součástí návrháře jinak než v době návrhu.

<xref:Microsoft.VisualStudio.Shell.Design.ProvideDesignerMetadataAttribute> Třídy lze použít prostřednictvím kódu programu nebo použitá na VSPackage, která poskytuje návrháře.

Instance <xref:Microsoft.VisualStudio.Shell.Design.ProvideDesignerMetadataAttribute> třída se používá k úpravě metadat komponenty vytvořené na návrhové ploše. Jeden například nahradit výchozí prohlížeč vlastnost používá <xref:System.Windows.Forms.CommonDialog> objekty s prohlížečem, který vlastní vlastnosti.

Úpravy poskytované instance <xref:Microsoft.VisualStudio.Shell.Design.ProvideDesignerMetadataAttribute> použitý pro provádění na VSPackage <xref:Microsoft.VisualStudio.Shell.Package> může mít jednu ze dvou oborů:

- Global – pro všechny nové instance dané komponenty.

- Místní--týkající se pouze instance komponenty vytvořen na návrhové ploše poskytuje aktuální VSPackage.

`IsGlobal` Vlastnost <xref:Microsoft.VisualStudio.Shell.Design.ProvideDesignerMetadataAttribute> instance použít pro provádění na VSPackage <xref:Microsoft.VisualStudio.Shell.Package> určuje tento obor.

Použití atributu k implementaci <xref:Microsoft.VisualStudio.Shell.Package> s <xref:Microsoft.VisualStudio.Shell.Design.ProvideDesignerMetadataAttribute.IsGlobal%2A> vlastnost <xref:Microsoft.VisualStudio.Shell.Design.ProvideDesignerMetadataAttribute> objekt nastaven `true`, níže, změní prohlížeče, aby celé prostředí sady Visual Studio:

`[ProvideDesignerMetadata(typeof(Color), typeof(CustomBrowser),`   `IsGlobal=true`  `)]`

`internal class MyPackage : Package {}`

Pokud globální příznak byla nastavena na `false`, pak je lokální vzhledem k aktuální návrhář nepodporuje aktuální VSPackage změnu metadat:

`[ProvideDesignerMetadata(typeof(Color), typeof(CustomBrowser),`   `IsGlobal=false`  `)]`

`internal class MyPackage : Package {}`

> [!NOTE]
> Návrhové ploše podporuje pouze vytváření komponent, a proto pouze součásti může mít místních metadat. V předchozím příkladu jsme se pokouší změnit vlastnost, jako `Color` vlastnosti objektu. Pokud `false` byla předána pro globální příznak `CustomBrowser` by nikdy zobrazeny, protože návrhář vytvoří nikdy ve skutečnosti instance `Color`. Nastavení globální příznak `false` je užitečné pro součásti, například ovládací prvky, časovačů a dialogových oknech.

## <a name="see-also"></a>Viz také:

- <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension>
- <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtensionAttribute>
- <xref:System.ComponentModel.ToolboxItemFilterType>
- [Rozšíření podpory během návrhu](https://msdn.microsoft.com/Library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)