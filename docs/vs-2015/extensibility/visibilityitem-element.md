---
title: Visibilityitem – Element | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- VisibilityItem element (VSCT XML schema)
- VSCT XML schema elements, VisibilityItem
ms.assetid: 0932f551-972d-4194-84bb-426e3e4375e4
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f6f71e145282d1d6e340060b9798ca54c9af9f4e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54763758"
---
# <a name="visibilityitem-element"></a>VisibilityItem – element
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

`VisibilityItem` Element určuje statické viditelnost příkazů a panelů nástrojů. Každá položka identifikuje příkaz nebo nabídky a také objekt context přidružený příkaz uživatelského rozhraní. Sada Visual Studio zjistí bez načítání rozšíření VSPackages, který je definovat příkazy, nabídek a panelů nástrojů a jejich viditelnost. Využívá integrovaného vývojového prostředí <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A> metodou ke zjištění, jestli je aktivní kontext uživatelského rozhraní příkazů.  
  
 Po načtení sady VSPackage, Visual Studio očekává, že příkaz viditelnost bude určen sady VSPackage místo `VisibilityItem`. K určení přehled o svých rukou, můžete implementovat buď <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> obslužná rutina události nebo <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metoda, v závislosti na tom, jak jste implementovali svých rukou.  
  
 Příkaz nebo nabídky, která má `VisibilityItem` elementu se zobrazí pouze v případě, souvisejícího kontextu je aktivní. Můžete přidružit jediným příkazem, nabídku nebo panel nástrojů jeden nebo více kontexty příkaz uživatelského rozhraní zahrnutím záznam pro každou kombinaci kontext příkazů. Pokud příkaz nebo nabídky je spojeno s více kontexty příkaz uživatelského rozhraní, příkaz nebo nabídky je viditelné při aktivním některou z uživatelského rozhraní kontexty přidružený příkaz.  
  
 `VisibilityItem` Element platí pouze pro příkazy, nabídky a panely nástrojů, ne do skupin. Element, který nemá se souvisejícím `VisibilityItem` pokaždé, když je aktivní nabídku nadřazené je element viditelný.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<VisibilityItem  
  guid ="="cmdGuidMyProductCommands"  
  id=="cmdidAddWidget"  
  context="guidNotViewSourceMode"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|identifikátor GUID|Povinný parametr. Identifikátor GUID identifikátoru GUID a ID příkazu.|  
|id|Povinný parametr. ID identifikátoru GUID a ID příkazu.|  
|kontext|Povinný parametr. Kontext uživatelského rozhraní, ve kterém je příkaz viditelný.|  
|Podmínka|Volitelné. Zobrazit [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádná  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[VisibilityConstraints – element](../extensibility/visibilityconstraints-element.md)|`VisibilityConstraints` Prvek určuje statické viditelnost skupiny příkazů a panely nástrojů.|  
  
## <a name="remarks"></a>Poznámky  
 Standardní uživatelské rozhraní Visual Studio kontexty jsou definovány v *cestu instalace sady Visual Studio SDK*\VisualStudioIntegration\Common\Inc\vsshlids.h soubor stejně jako v <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids> a <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80> třídy. Úplnější sadu kontexty uživatelského rozhraní je definováno v <xref:Microsoft.VisualStudio.VSConstants> třídy.  
  
## <a name="example"></a>Příklad  
  
```  
<VisibilityConstraints>  
  <VisibilityItem guid="cmdSetGuidMyProductCommands"     id="cmdidAddWidget"  
    context="guidNotViewSourceMode"/>  
</VisibilityConstraints>  
```  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A>   
 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus>   
 <xref:Microsoft.VisualStudio.VSConstants>   
 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids>   
 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80>   
 [Visibilityconstraints – Element](../extensibility/visibilityconstraints-element.md)   
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
