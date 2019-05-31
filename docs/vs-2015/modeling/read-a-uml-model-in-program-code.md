---
title: Čtení modelu UML v programovém kódu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- UML API, reading models
ms.assetid: 0f63105e-6079-498a-94f1-318c0f5f9621
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 37539ee6c031d88b9db279cc61214ac5e3077e76
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63387672"
---
# <a name="read-a-uml-model-in-program-code"></a>Čtení modelu UML v programovém kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete načíst UML model a jeho diagramy pomocí rozhraní API UML.  
  
## <a name="Reading"></a> Čtení modelu v programovém kódu  
 Přístup k obsahu modelu, aniž by se zobrazil v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] okno, použijte `ModelingProject.LoadReadOnly()`.  
  
 Příklad:  
  
```  
using Microsoft.VisualStudio.Uml.Classes;   
               // for IElement  
using Microsoft.VisualStudio.ArchitectureTools.Extensibility;   
               // for ModelingProject  
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Uml;  
               // for IModelStore  
...   
string projectPath = @"C:\MyProjectFolder\MyProject.modelproj";  
using (IModelingProjectReader projectReader =  
           ModelingProject.LoadReadOnly(projectPath))  
{  
   IModelStore store = projectReader.Store;  
   foreach (IClass umlClass in store.AllInstances<IClass>())  
   {   
       ...  
   }  
}  
```  
  
 Pokud chcete přečíst tvary v diagramu, musíte přečíst projekt a potom diagram.  
  
 Příklad:  
  
```  
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation;   
                             // for IDiagram  
...  
foreach (string diagramFile in projectReader. DiagramFileNames)  
{   
  IDiagram diagram = projectReader.LoadDiagram(diagramFile);  
  foreach (IShape<IElement> shape   
         in diagram.GetChildShapes<IElement>())  
  { ... }  
}  
```  
  
## <a name="alternative-methods"></a>Alternativní metody  
 Pro mnoho aplikací [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Modelbus umožňuje odkazovat na modely a prvky v nich s větší odolností a pružností než pomocí metod popsaných v tomto tématu. Poskytuje standardní metodu vytváření vazeb mezi libovolnými prvky, buď v jednom nebo několika modelech. Další informace najdete v tématu [modely UML integrovat s jinými modely a nástroji](../modeling/integrate-uml-models-with-other-models-and-tools.md).  
  
 Modely a diagramy můžete také otevřít v uživatelském rozhraní pomocí [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] rozhraní API. Další informace najdete v tématu [otevření modelu UML pomocí rozhraní API sady Visual Studio](../modeling/open-a-uml-model-by-using-the-visual-studio-api.md).  
  
## <a name="Standalone"></a> Samostatné aplikace  
 Příklad v předchozím oddílu bude fungovat v rozšíření sady Visual Studio. Je možné číst model v samostatné aplikaci, ale je nutné přidat některé odkazy na vaše [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] projektu.  
  
> [!NOTE]
> Podrobnosti o tom, jak přečíst model v samostatné aplikaci se pravděpodobně změní v budoucích verzích tohoto produktu. Některé funkce, které jsou k dispozici v aktuální verzi nebudou k dispozici v budoucích verzích.  
  
#### <a name="to-add-references-to-read-a-model-in-a-stand-alone-application"></a>Přidání odkazů pro čtení modelu v samostatné aplikaci.  
  
1. V Průzkumníku řešení klikněte pravým tlačítkem na projekt, ve kterém sestavujete aplikaci a potom klikněte na tlačítko **vlastnosti**. V editoru vlastností v **aplikace** kartu, nastavte **Cílová architektura** na požadovanou verzi rozhraní .NET Framework.  
  
2. Přidat [!INCLUDE[TLA2#tla_net](../includes/tla2sharptla-net-md.md)] odkazy, které potřebujete pro přístup k modelů UML, obvykle:  
  
   - Microsoft.VisualStudio.Uml.Interfaces.dll  
  
   - Microsoft.VisualStudio.ArchitectureTools.Extensibility.dll  
  
3. Kromě odkazů uvedených v předchozích částech přidejte následující odkazy projektu z **\Program Files\Microsoft sady Visual Studio [verze] \Common7\IDE\PrivateAssemblies**:  
  
   - Microsoft.VisualStudio.Uml.dll  
  
   - Microsoft.VisualStudio.TeamArchitect.ModelStore.Dsl.dll  
  
     Pokud chcete přečíst diagramy v aplikaci, můžete také vyžadovat tyto odkazy:  
  
   - Microsoft.VisualStudio.TeamArchitect.ActivityDesigner.Dsl.dll  
  
   - Microsoft.VisualStudio.TeamArchitect.ComponentDesigner.Dsl.dll  
  
   - Microsoft.VisualStudio.TeamArchitect.LogicalClassDesigner.Dsl.dll  
  
   - Microsoft.VisualStudio.TeamArchitect.SequenceDesigner.Dsl.dll  
  
   - Microsoft.VisualStudio.TeamArchitect.UseCase.Dsl.dll  
  
## <a name="see-also"></a>Viz také  
 [Programování s rozhraním API UML](../modeling/programming-with-the-uml-api.md)   
 [Rozšíření modelů a diagramů UML](../modeling/extend-uml-models-and-diagrams.md)
