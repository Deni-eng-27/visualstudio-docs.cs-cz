---
title: Dialogové okno informace o sestavení | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vb.ProjectPropertiesAssemblyInfo
helpviewer_keywords:
- Assembly Information dialog box
ms.assetid: 8f1f6449-e03d-4a5b-9076-d3b1f84ada48
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 616a46b4d8349bd2c385fda0dd36e6dc69fa60af
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59663869"
---
# <a name="assembly-information-dialog-box"></a>Dialogové okno Informace o sestavení
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

**Informace o sestavení** dialogové okno se používá k určení hodnoty [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] globálního sestavení atributy, které jsou uloženy v souboru AssemblyInfo automaticky vytvořené pomocí projektu. V **Průzkumníku řešení**, soubor se nachází v **Můj projekt** uzel v [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] (klikněte na tlačítko **zobrazit všechny soubory** zobrazíte jeho); je umístěn v rámci  **Vlastnosti** v [!INCLUDE[csprcs](../../includes/csprcs-md.md)]. Další informace o atributech sestavení naleznete v tématu [atributy](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205).  
  
 Pro přístup k tomuto dialogovému oknu, vyberte uzel projektu v **Průzkumníka řešení**a potom na **projektu** nabídky, klikněte na tlačítko **vlastnosti**. Když **Návrháře projektu** se zobrazí, klikněte na tlačítko **aplikace** kartu. Na **aplikace** stránky, klikněte na tlačítko **informace o sestavení** tlačítko.  
  
## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní  
 **Název**  
 Určuje název pro manifest sestavení. Odpovídá <xref:System.Reflection.AssemblyTitleAttribute>.  
  
 **Popis**  
 Určuje volitelný popis pro manifest sestavení. Odpovídá <xref:System.Reflection.AssemblyDescriptionAttribute>.  
  
 **Společnosti**  
 Určuje název společnosti pro manifest sestavení. Odpovídá <xref:System.Reflection.AssemblyCompanyAttribute>.  
  
 **Produkt**  
 Určuje název produktu pro manifest sestavení. Odpovídá <xref:System.Reflection.AssemblyProductAttribute>.  
  
 **Copyright**  
 Určuje autorských právech pro manifest sestavení. Odpovídá <xref:System.Reflection.AssemblyCopyrightAttribute>.  
  
 **Ochranné známky**  
 Určuje ochranná známka pro manifest sestavení. Odpovídá <xref:System.Reflection.AssemblyTrademarkAttribute>.  
  
 **Verze sestavení**  
 Určuje verzi sestavení. Odpovídá <xref:System.Reflection.AssemblyVersionAttribute>.  
  
 **Verze souboru**  
 Určuje číslo verze, který instruuje kompilátor, aby používaly určitou verzi prostředku verze souboru Win32. Odpovídá <xref:System.Reflection.AssemblyFileVersionAttribute>.  
  
 **GUID**  
 Jedinečný identifikátor GUID, který identifikuje sestavení. Při vytváření projektu sady Visual Studio vytvoří identifikátor GUID pro sestavení. Odpovídá <xref:System.Guid>.  
  
 **Neutrální jazyk**  
 Určuje, který jazyková verze sestavení podporuje. Odpovídá <xref:System.Resources.NeutralResourcesLanguageAttribute>. Výchozí hodnota je **(žádný)**.  
  
 **Ujistěte se, sestavení viditelné modulu COM**  
 Určuje, zda bude k dispozici do modelu COM. typy v sestavení Odpovídá <xref:System.Runtime.InteropServices.ComVisibleAttribute>.  
  
## <a name="see-also"></a>Viz také  
 [Stránka aplikace, Návrhář projektu (Visual Basic)](../../ide/reference/application-page-project-designer-visual-basic.md)   
 [Atributy](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205)
