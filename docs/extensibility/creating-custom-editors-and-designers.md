---
title: Vytváření vlastních editorů a návrhářů | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- designers [Visual Studio SDK]
- editors [Visual Studio SDK], custom
ms.assetid: b6a5e8b2-0ae1-4fc3-812d-09d40051b435
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7a6cb0d70566eaabb2ba37cb209041e03684c958
ms.sourcegitcommit: 97623fd6190c43fed0d2ee7af92b01c375282622
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/04/2019
ms.locfileid: "73568894"
---
# <a name="create-custom-editors-and-designers"></a>Vytváření vlastních editorů a návrhářů

Integrované vývojové prostředí (IDE) sady Visual Studio může hostovat různé typy editoru:

- Základní editor sady Visual Studio

- Vlastní editory

- Externí editory

- Návrháři

Následující informace vám pomohou vybrat typ editoru, který potřebujete.

## <a name="types-of-editor"></a>Typy editoru

Informace o základním editoru sady Visual Studio najdete v tématu věnovaném [rozšířenému editoru a jazykovým službám](../extensibility/extending-the-editor-and-language-services.md).

### <a name="custom-editors"></a>Vlastní editory
 Vlastní editor je ten, který je navržený tak, aby fungoval ve specializovaných případech. Můžete například vytvořit editor, jehož funkce je číst a zapisovat data do konkrétního úložiště, jako je například Microsoft Exchange Server. Vlastní editor vyberte, pokud chcete Editor, který pracuje pouze s typem projektu, nebo pokud chcete použít editor, který obsahuje pouze několik specifických příkazů. Upozorňujeme však, že uživatelé nebudou moci používat vlastní editor pro úpravu standardních [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektů.

 Vlastní editor může použít objekt pro vytváření editoru a přidat informace o editoru do registru. Typ projektu přidružený k vlastnímu editoru však může vytvořit instanci vlastního editoru jiným způsobem.

 Vlastní editor může použít buď místní aktivaci, nebo zjednodušené vkládání, aby bylo možné implementovat zobrazení.

### <a name="external-editors"></a>Externí editory
 Externí editory jsou editory, které nejsou integrovány do sady Visual Studio, jako je například Microsoft Word, Poznámkový blok nebo Microsoft FrontPage. Takový editor můžete volat, pokud například předáváte text ze sady VSPackage. Externí editory se registrují samy a můžou se používat mimo Visual Studio. Když zavoláte externí editor a může být vložen do hostitelského okna, pak se zobrazí v okně v integrovaném vývojovém prostředí (IDE). Pokud není, rozhraní IDE pro něj vytvoří samostatné okno.

 Metoda <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A> nastaví prioritu dokumentu pomocí výčtu <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY>. Pokud je zadána hodnota `DP_External`, soubor může být otevřen externím editorem.

## <a name="editor-design-decisions"></a>Editor rozhodnutí o návrhu
 Následující otázky návrhu vám pomůžou zvolit typ editoru, který nejlépe vyhovuje vaší aplikaci:

- Bude vaše aplikace ukládat data do souborů nebo ne? Pokud bude data ukládat v souborech, budou mít vlastní nebo standardní formát?

   Použijete-li standardní formát souboru, další typy projektů kromě projektu budou moci otevřít a číst a zapisovat data do nich. Pokud však použijete vlastní formát souboru, bude moci otevřít a číst a zapisovat data do nich pouze typ projektu.

   Pokud projekt používá soubory, měli byste přizpůsobit standardní editor. Pokud váš projekt nepoužívá soubory, ale spíše používá položky v databázi nebo jiném úložišti, měli byste vytvořit vlastní editor.

- Potřebuje váš Editor hostovat ovládací prvky ActiveX?

   Pokud editor hostuje ovládací prvky ActiveX, proveďte implementaci místního editoru aktivace, jak je uvedeno v [místní aktivaci](/visualstudio/misc/in-place-activation?view=vs-2015). Pokud nehostuje ovládací prvky ActiveX, použijte zjednodušený Editor vkládání nebo Přizpůsobte [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] výchozí editor.

- Bude váš Editor podporovat více zobrazení? Chcete-li zobrazit zobrazení editoru ve stejnou dobu jako výchozí editor, je nutné podporovat více zobrazení.

   Pokud váš Editor potřebuje podporovat více zobrazení, data dokumentu a objekty zobrazení dokumentu pro Editor musí být samostatné objekty. Další informace najdete v tématu [Podpora více zobrazení dokumentů](../extensibility/supporting-multiple-document-views.md).

   Pokud editor podporuje více zobrazení, plánujete pro objekt dat dokumentu použít implementaci vyrovnávací paměti textu (<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> objekt) [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] core editor? To znamená, že chcete podporovat zobrazení editoru vedle sebe pomocí základního editoru [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]? Tato možnost je základem Návrháře formulářů.

- Pokud potřebujete hostovat externí editor, můžete Editor vložit do [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]?

   Pokud může být vložena, měli byste vytvořit hostitelské okno pro externí editor a poté zavolat metodu <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3.IsDocumentInProject%2A> a nastavit hodnotu výčtu <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY> na `DP_External`. Pokud Editor nelze vložit, rozhraní IDE pro něj automaticky vytvoří samostatné okno.

## <a name="in-this-section"></a>V tomto oddílu

[Návod: Vytvoření vlastního editoru](../extensibility/walkthrough-creating-a-custom-editor.md)\
Vysvětluje, jak vytvořit vlastní editor.

[Návod: Přidání funkcí do vlastního editoru](../extensibility/walkthrough-adding-features-to-a-custom-editor.md)\
Vysvětluje, jak přidat funkce do vlastního editoru.

[Inicializace a konfigurace metadat návrháře](../extensibility/designer-initialization-and-metadata-configuration.md)\
Vysvětluje, jak inicializovat návrháře.

[Poskytněte podporu funkce zpět pro návrháře](../extensibility/supplying-undo-support-to-designers.md)\
Vysvětluje, jak poskytnout zpětnou podporu pro návrháře.

[Barevné zvýrazňování syntaxe ve vlastních editorech](../extensibility/syntax-coloring-in-custom-editors.md)\
Vysvětluje rozdíl mezi zvýrazněním syntaxe v základním editoru a ve vlastních editorech.

[Data dokumentů a zobrazení dokumentů ve vlastních editorech](../extensibility/document-data-and-document-view-in-custom-editors.md)\
Vysvětluje, jak implementovat data dokumentů a zobrazení dokumentů ve vlastních editorech.

## <a name="related-sections"></a>Související oddíly

[Starší rozhraní v editoru](/visualstudio/extensibility/legacy-interfaces-in-the-editor?view=vs-2015)\
Vysvětluje, jak přistupovat k základnímu editoru prostřednictvím starší verze rozhraní API.

[Vývoj služby starší verze jazyka](../extensibility/internals/developing-a-legacy-language-service.md)\
Vysvětluje, jak implementovat službu jazyka.

[Rozšiřování dalších částí sady Visual Studio](../extensibility/extending-other-parts-of-visual-studio.md)\
Vysvětluje, jak vytvořit prvky uživatelského rozhraní, které se shodují se zbytkem [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].

## <a name="see-also"></a>Viz také:

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory>