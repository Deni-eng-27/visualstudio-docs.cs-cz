---
title: Implementace generátorů tvořených jedním souborem | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- custom tools, implementing
- projects [Visual Studio SDK], extensibility
- projects [Visual Studio SDK], managed custom tools
ms.assetid: fe9ef6b6-4690-4c2c-872c-301c980d17fe
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e2ca842f05692d5d47ed42470f58f2be0bb45007
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54767216"
---
# <a name="implementing-single-file-generators"></a>Implementace generátorů tvořených jedním souborem
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vlastní nástroj – někdy označovány jako generátor tvořený jedním souborem – je možné rozšířit [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] a [!INCLUDE[csprcs](../../includes/csprcs-md.md)] systémy v projektů [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Vlastní nástroj je komponenta modelu COM, který implementuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> rozhraní. Pomocí tohoto rozhraní, transformuje vlastní nástroj jeden vstupní soubor do jednoho výstupního souboru. Výsledek transformace může být zdrojový kód nebo jakýkoli jiný výstup, který je užitečný. Dva příklady souborů vlastní nástroj vygeneruje kód se kód vygeneruje v reakci na změny vizuálního návrháře a soubory vygenerované pomocí webové služby WSDL (Description Language).  
  
 Když je načtena vlastní nástroj nebo vstupní soubor je uložen, projektový systém volá <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.Generate%2A> metody a předává odkazem na <xref:Microsoft.VisualStudio.Shell.Interop.IVsGeneratorProgress> rozhraní zpětného volání, které nástroj sestavy průběh uživateli.  
  
 Vlastní nástroj vygeneruje výstupní soubor je přidána do projektu se závislostí na vstupní soubor. Systém projektu automaticky určuje název výstupního souboru, na základě řetězce vrácené provádění vlastní nástroj <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A>.  
  
 Musíte implementovat vlastní nástroj <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> rozhraní. Volitelně podpora vlastních nástrojů <xref:Microsoft.VisualStudio.OLE.Interop.IObjectWithSite> rozhraní pro načtení informací ze zdroje než vstupní soubor. V každém případě před použitím vlastní nástroj, je nutné ho zaregistrovat pomocí systému nebo v [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] místního registru. Další informace o registraci vlastních nástrojů najdete v tématu [registrace generátorů tvořených jedním souborem](../../extensibility/internals/registering-single-file-generators.md).  
  
## <a name="see-also"></a>Viz také  
 [Určení výchozí Namespace projektu](../../misc/determining-the-default-namespace-of-a-project.md)   
 [Zveřejnění typů pro vizuální návrháře](../../extensibility/internals/exposing-types-to-visual-designers.md)
