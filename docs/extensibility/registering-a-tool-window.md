---
title: Registrace okno nástroje | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- tool windows, registering managed
- tool windows, registering
ms.assetid: 8c8c4a24-3da4-497b-9db2-0ddd7cfbfdd2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 637f0635a4f1e04df7495ab00b4e79b59d97ee1b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="registering-a-tool-window"></a>Registrace okno nástroje
Můžete zaregistrovat váš nástroj windows pomocí <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> a  <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowVisibilityAttribute>  
  
## <a name="example"></a>Příklad  
  
```csharp  
  
[ProvideToolWindow(typeof(PersistedWindowPane), Style = MsVsShell.VsDockStyle.Tabbed, Window = "3ae79031-e1bc-11d0-8f78-00a0c9110057")]
[ProvideToolWindow(typeof(DynamicWindowPane), PositionX=250, PositionY=250, Width=160, Height=180, Transient=true)]
[ProvideToolWindowVisibility(typeof(DynamicWindowPane), /*UICONTEXT_SolutionExists*/"f1536ef8-92ec-443c-9ed7-fdadf150da82")]  
[ProvideMenuResource(1000, 1)]  
[PackageRegistration(UseManagedResourcesOnly = true)]  
[Guid("01069CDD-95CE-4620-AC21-DDFF6C57F012")]  
public class PackageToolWindow : Package  
{  
```  
  
 Ve výše, kódu <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> zaregistruje nástroj windows PersistedWindowPane a DynamicWindowPane pomocí sady Visual Studio. Okno trvalou nástroje je ukotvena a na kartách s **Průzkumníku**, a dynamické okno bude mít výchozí počáteční pozice a velikosti. Okno dynamické přišla přechodný, což naznačuje, že nebyl vytvořen při spuštění. To umožňuje zápis hodnoty DontForceCreate ToolWindows klíče v registru systému. Další informace najdete v tématu [konfigurace zobrazení okna nástroj](../extensibility/tool-window-display-configuration.md).
