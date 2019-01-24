---
title: Zpracování příkazů | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - command handling
ms.assetid: 78f67d92-77f7-45cb-ad75-6e3346379cc3
caps.latest.revision: 21
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 563f38cd2dc3854918fe637fdc11afe1d1a49b64
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54793444"
---
# <a name="command-handling"></a>Zpracování příkazů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Editoru můžete definovat nové příkazy. Příkazy se obvykle zobrazují v nabídce, na panelu nástrojů nebo v místní nabídce.  
  
 Další informace o definování příkazů a nabídek, naleznete v tématu [příkazy, nabídky a panely nástrojů](../extensibility/internals/commands-menus-and-toolbars.md).  
  
 Služba jazyka můžete řídit, jaké kontextové nabídky se zobrazí v editoru, tím, že zachytává <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> výčtu. Alternativně můžete řídit kontextové nabídky na základě jednotlivé značky. Další informace najdete v části [důležité příkazy pro filtry služby jazyka](../extensibility/internals/important-commands-for-language-service-filters.md).  
  
## <a name="adding-commands-to-the-editor-context-menu"></a>Přidání příkazů do kontextové nabídky editoru  
 Přidání příkazu do místní nabídky, je nutné nejprve definovat sadu příkazy nabídek, které patří do konkrétní skupiny. Následující příklad je převzat ze souboru .vsct generována jako součást návodu [názorný postup: Přidávání funkcí do vlastního editoru](../extensibility/walkthrough-adding-features-to-a-custom-editor.md):  
  
 \<Menu guid="guidCustomEditorCmdSet" id="IDMX_RTF" priority="0x0000" type="Context">  
  
 \<Identifikátor guid nadřazené = "guidCustomEditorCmdSet" id = "0" / >  
  
 \<Řetězce >  
  
 \<ButtonText – > CustomEditor kontextovou nabídku\</ButtonText >  
  
 \<CommandName > CustomEditorContextMenu\</CommandName >  
  
 \</Strings>  
  
 \</ Nabídka >  
  
 \</ Nabídky >  
  
 Výše uvedený text přidá příkazu kontextové nabídky s textem **CustomEditor kontextovou nabídku**. Identifikátor GUID nabídky je, že sadu příkazů, které je vytvořené pomocí tohoto editoru, a typ je "Kontext".  
  
 Můžete použít také předdefinované příkazy, které nemusí být definovány v souboru .vsct. Například pokud si projdete soubor EditorPane.cs vygenerovaná šablona balíček Visual Studio, zjistíte, že sadu předdefinovaných příkazů, jako například <xref:Microsoft.VisualStudio.VSConstants.VSStd97CmdID> určené <xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>, jsou zpracovávány v obslužné rutiny příkazů, jako je například metoda onSelectAll.  
  
## <a name="see-also"></a>Viz také  
 [Příkazy, nabídky a panely nástrojů](../extensibility/internals/commands-menus-and-toolbars.md)
