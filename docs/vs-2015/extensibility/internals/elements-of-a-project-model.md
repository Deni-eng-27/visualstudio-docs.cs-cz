---
title: Prvky modelu projektu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], implementation considerations
- project models
- projects [Visual Studio SDK], elements
ms.assetid: a1dbe0dc-68da-45d7-8704-5b43ff7e4fc4
caps.latest.revision: 19
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d4e47712df1f76556ced8c69abb8bf5af085d01e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54755582"
---
# <a name="elements-of-a-project-model"></a>Prvky modelu projektu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Rozhraní a implementace všech projektů v [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] sdílet základní struktura: modelu projektu pro váš typ projektu. V modelu projektu, který je sady VSPackage, kterou vyvíjíte, můžete vytvořit objekty, které splňují vaše rozhodnutí o návrhu a fungují společně s globální funkce poskytované službou integrovaného vývojového prostředí. I když můžete řídit, jak je trvalý položku projektu, například můžete neovládají oznámení, že soubor musí nastavit jako trvalý. Když uživatel umístí fokus na otevřeném projektu položku a vybere **Uložit** na **souboru** nabídce [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] nabídky panelu, musí kód typu projektu zachytit příkazu v prostředí IDE, zachovat souboru, a odesílat oznámení zpět do integrovaného vývojového prostředí, že soubor je již změnit.  
  
 Vaše VSPackage komunikuje s integrovaným vývojovým prostředím prostřednictvím služeb, které poskytují přístup k rozhraní IDE. Prostřednictvím určitých služeb, monitorování a trasy například příkazy a poskytují kontextové informace pro výběrech v projektu. Všechny globální funkce integrovaného vývojového prostředí potřebné pro vaše VSPackage poskytuje služby. Další informace o službách najdete v tématu [jak: Získání služby](../../extensibility/how-to-get-a-service.md).  
  
 Další důležité informace o implementaci:  
  
- Model jeden projekt může obsahovat více než jeden typ projektu.  
  
- Typy projektů a odebrání dodatečné projektu továren jsou registrovány nezávisle na sobě identifikátory GUID.  
  
- Soubor šablony nebo Průvodce inicializovat nový soubor projektu, když uživatel vytvoří nový projekt přes musí mít každý projekt [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] uživatelského rozhraní. Například [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] šablony inicializovat, co se nakonec stanou soubory .vcproj.  
  
  Následující obrázek znázorňuje primární rozhraní, služby a objekty, které tvoří implementaci obvyklou pro projekty. Aplikace pomocné rutiny, HierUtil7, můžete použít k vytvoření základní objektů a ostatní programovací často používaný text. Další informace o pomocné rutiny HierUtil7 aplikace najdete v tématu [není v sestavení: Použití HierUtil7 projektu třídy k implementaci typu projektu (C++)](http://msdn.microsoft.com/a5c16a09-94a2-46ef-87b5-35b815e2f346).  
  
  ![Visual Studio Project Model graphic](../../extensibility/internals/media/vsprojectmodel.gif "vsProjectModel")  
  model projektu  
  
  Další informace o rozhraní a služby uvedené v předchozím diagramu a další volitelné rozhraní není zahrnuta v diagramu najdete v tématu [základní komponenty modelu projektu](../../extensibility/internals/project-model-core-components.md).  
  
  Projekty mohou podporovat příkazy a proto musí implementovat <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní k účasti v příkazu směrování přes příkaz kontextu identifikátory GUID.  
  
## <a name="see-also"></a>Viz také  
 [Kontrolní seznam: Vytvoření nových typů projektů](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [Není v sestavení: Použití HierUtil7 projektu třídy k implementaci typu projektu (C++)](http://msdn.microsoft.com/a5c16a09-94a2-46ef-87b5-35b815e2f346)   
 [Základní komponenty modelu projektu](../../extensibility/internals/project-model-core-components.md)   
 [Vytváření instancí projektu pomocí objektů pro vytváření projektů](../../extensibility/internals/creating-project-instances-by-using-project-factories.md)   
 [Postupy: Získání služby](../../extensibility/how-to-get-a-service.md)   
 [Vytváření typů projektů](../../extensibility/internals/creating-project-types.md)
