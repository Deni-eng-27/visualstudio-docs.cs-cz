---
title: Modelu služby jazyk starší | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- language services, model
ms.assetid: d8ae1c0c-ee3d-4937-a581-ee78d0499793
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 943f0f013045e3082af3069ed4d45aaed1096869
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31131574"
---
# <a name="model-of-a-legacy-language-service"></a>Model služby jazyk starší verze
Služba jazyka definuje elementy a funkce pro konkrétní jazyk a slouží k poskytování editoru informace specifické pro daný jazyk. Například editoru musí vědět, elementy a klíčová slova jazyka za účelem podpory barevné zvýrazňování syntaxe.  
  
 Služba jazyka úzce spolupracuje s textová vyrovnávací paměť spravuje se v editoru a zobrazení, která obsahuje editor. Microsoft IntelliSense **rychlé informace** možnost je příkladem funkce poskytované služba jazyka.  
  
## <a name="a-minimal-language-service"></a>Služba minimální jazyka  
 Nejzákladnější služba jazyka obsahuje následující dva objekty:  
  
-   *Služba jazyka* implementuje <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> rozhraní. Služba jazyka obsahuje informace o jazyce, včetně názvu, přípony názvů souborů, Správce oken kódu a colorizer.  
  
-   *Colorizer* implementuje <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> rozhraní.  
  
 Následující koncepční kreslení znázorňuje model služby základní jazyk.  
  
 ![Jazyk modelu služby obrázek](../../extensibility/media/vslanguageservicemodel.gif "vsLanguageServiceModel")  
Základní jazyk modelu služby  
  
 Hostitelé okna dokumentu *dokumentu zobrazení* editoru, v tomto případě [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] základní editor. Zobrazení dokumentu a textová vyrovnávací paměť jsou vlastněny editoru. Tyto objekty pracovat s [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] prostřednictvím okna specializované dokumentu názvem *kódu – okno*. Okno kódu je součástí <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> objekt, který je vytvořen a řídí rozhraní IDE.  
  
 Při načítání souboru s příponou dané editoru vyhledá jazyk služby přidružené k rozšíření a předá ho okno kódu voláním <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetCodeWindowManager%2A> metoda. Vrátí služby jazyk *Správce oken kódu*, který implementuje <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> rozhraní.  
  
 Následující tabulka obsahuje přehled objektů v modelu.  
  
|Součást|Objekt|Funkce|  
|---------------|------------|--------------|  
|Textová vyrovnávací paměť|<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>|Datový proud Unicode pro čtení a zápis textu. Je možné použít jiné kódování textu.|  
|Kódu – okno|<xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow>|Okna dokumentu, který obsahuje jedno nebo více zobrazení textu. Když [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] je v režimu rozhraní více dokumentů (MDI), v okně kód je podřízeným MDI.|  
|Zobrazení textu|<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>|Okno, které umožňuje uživateli přejděte a zobrazit text pomocí klávesnice a myši. Zobrazení textu se uživateli zobrazí jako editor. Můžete vytvořit zobrazení textu v systému windows obyčejnou editor, ve výstupním okně a hodnot proměnných. Kromě toho můžete nakonfigurovat jeden nebo více zobrazení textu v rámci časového období kódu.|  
|Textový správce|Spravuje <xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager> služby, ze kterého můžete získat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager> ukazatele|Komponenta, která udržuje běžných informací o sdílí všechny součásti, které jsou popsané.|  
|Služba jazyka|Implementace závislé; implementuje <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo>|Objekt, který poskytuje informace pro konkrétní jazyk například zvýraznění syntaxe, dokončování a odpovídající složené závorce editoru.|  
  
## <a name="see-also"></a>Viz také  
 [Data dokumentu a zobrazení dokumentu ve vlastních editorech](../../extensibility/document-data-and-document-view-in-custom-editors.md)