---
title: Barevné zvýrazňování syntaxe ve vlastních editorech | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], custom - syntax coloring
ms.assetid: 74900b9a-baef-432a-8231-4568fb5e19ad
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 7a0233873ba5d6ea2fca746f8e12f4bf693b79da
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "64816912"
---
# <a name="syntax-coloring-in-custom-editors"></a>Barevné zvýrazňování syntaxe ve vlastních editorech
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Editory sady SDK prostředí sady Visual Studio, včetně základního editoru, používají jazykové služby k identifikaci konkrétních syntaktických položek a jejich zobrazení se zadanými barvami pro dané zobrazení dokumentu.  
  
## <a name="colorization-requirements"></a>Požadavky na zabarvení  
 Všechny editory implementující Colorizer jazykové služby musí:  
  
1. Použijte objekt implementující <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> ke správě textu, který má být zabarvení, a objekt, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> který implementuje k poskytnutí zobrazení dokumentu textu.  
  
2. Získejte rozhraní pro konkrétní jazykovou službu pomocí dotazování poskytovatele služeb VSPackage pomocí identifikačního identifikátoru GUID služby jazyka.  
  
3. Zavolejte <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.SetLanguageServiceID%2A> metodu implementující objektu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> . Tato metoda přidruží službu jazyka k <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> implementaci, kterou VSPackage používá ke správě textu, který se má obarvit.  
  
## <a name="core-editor-usage-of-a-language-services-colorizer"></a>Základní použití editoru Colorizer jazykové služby  
 Když se služba jazyka s Colorizer získá instancí základního editoru, analyzuje a vykresluje text pomocí Colorizer služby jazyka automaticky, aniž by to vyžadovalo další zásah na vaší straně.  
  
 Integrované vývojové prostředí (IDE) transparentně:  
  
- Volá Colorizer podle potřeby pro analýzu a analýzu textu při jeho přidání nebo úpravě v implementaci <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> .  
  
- Zajistí, aby se zobrazení dodané zobrazením dokumentu, které poskytuje <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> implementace, aktualizovalo a překresleno s použitím informací vrácených colorizer.  
  
## <a name="non-core-editor-usage-of-a-language-services-colorizer"></a>Nezákladní použití editoru Colorizer jazykové služby  
 Instance nezákladního editoru můžou také používat službu barevného zabarvení syntaxe služby jazyka, ale musí explicitně načítat a používat Colorizer služby a převádět jejich zobrazení dokumentů sami.  
  
 K tomu je potřeba editor, který není základní:  
  
1. Získejte objekt Colorizer jazykové služby (který implementuje `T:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer` a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer2> ). Vaše VSPackage to dělá voláním <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A> metody v rozhraní jazykové služby.  
  
2. Zavolejte <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> metodu, aby požádala o barevné zabarvení konkrétního rozsahu textu.  
  
     <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A>Metoda vrátí pole hodnot, jednu pro každé písmeno v rozsahu textu, který je barevně barevný. Určuje také rozsah textu jako konkrétní typ barevné položky, jako je například komentář, klíčové slovo nebo datový typ.  
  
3. Použijte informace o vybarvení vrácené funkcí <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> k překreslení a zobrazení jejího textu.  
  
> [!NOTE]
> Kromě použití Colorizer jazykové služby se sada VSPackage může rozhodnout použít mechanismus barevného zvýraznění textu sady Visual Studio pro obecné účely. Další informace o tomto mechanismu najdete v tématu [Použití písem a barev](../extensibility/using-fonts-and-colors.md).  
  
## <a name="see-also"></a>Viz také  
 [Barevné zvýrazňování syntaxe ve službě starší verze jazyka](../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)   
 [Implementace Obarvení syntaxe](../extensibility/internals/implementing-syntax-coloring.md)   
 [Postupy: Použití vestavěných barevných položek](../extensibility/internals/how-to-use-built-in-colorable-items.md)   
 [Vlastní položky, které lze zabarvit](../extensibility/internals/custom-colorable-items.md)
