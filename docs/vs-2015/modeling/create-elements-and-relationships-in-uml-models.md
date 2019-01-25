---
title: Vytváření elementů a vztahů v modelech UML | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- UML API
ms.assetid: cae81d32-8cc7-4f7c-9f00-20119952bc51
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 4b31faa7c71a0f4072d922528a1abc4d040e7dae
ms.sourcegitcommit: c496a77add807ba4a29ee6a424b44a5de89025ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54834971"
---
# <a name="create-elements-and-relationships-in-uml-models"></a>Vytváření elementů a vztahů v modelech UML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V programovém kódu pro rozšíření pro Visual Studio můžete vytvářet a odstraňovat prvky a vztahy.  
  
## <a name="create-a-model-element"></a>Vytvořte Element modelu  
  
### <a name="namespace-imports"></a>Namespace importy  
 Musí zahrnovat následující `using` příkazy.  
  
 Metody vytváření jsou definovány jako rozšiřující metody v tomto oboru názvů:  
  
 `using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Uml;`  
  
### <a name="obtain-the-owner-of-the-element-you-want-to-create"></a>Získání vlastníka prvek, na který chcete vytvořit  
 Model tvoří jeden strom tak, aby měla každá položka jednoho vlastníka, s výjimkou kořen modelu. Kořen modelu má typ `IModel`, což je typ `IPackage`.  
  
 Pokud vytváříte element, který se zobrazí v diagramu konkrétní, například uživatele aktuální diagram, by měl obvykle vytvoříte ho v balíčku, který je propojený s diagramem. Příklad:  
  
```  
IPackage linkedPackage = Context.CurrentDiagram.Element as IPackage;  
```  
  
 Tato tabulka shrnuje vlastnictví společné prvky modelu:  
  
|Element, který se má vytvořit|Owner|  
|---------------------------|-----------|  
|`IActor, IUseCase, IComponent, IClass, IInterface, IEnumeration`<br /><br /> `IActivity, IInteraction`|`IPackage, IModel`|  
|`IAttribute, IOperation`|`IClass, IInterface`|  
|`IPart, IPort`|`IComponent`|  
|`IAction, IObjectNode`|`IActivity`|  
|`ILifeline, IMessage, ICombinedFragment`|`IInteraction`|  
  
### <a name="invoke-the-create-method-on-the-owner"></a>Volání metody vytvořit na vlastníka  
 Název metody je ve formátu: `Create`*OwnedType*`()`. Příklad:  
  
```  
IUseCase usecase1 = linkedPackage.CreateUseCase();  
```  
  
 Některé typy mají složitější vytvoření metody, hlavně v sekvenčních diagramech. Zobrazit [sekvenčních diagramech UML upravit s použitím rozhraní API UML](../modeling/edit-uml-sequence-diagrams-by-using-the-uml-api.md).  
  
 Pro některé typy prvků, lze změnit vlastníka elementu během celé jeho životnosti pomocí `SetOwner(newOwner)`.  
  
### <a name="set-the-name-and-other-properties"></a>Nastavte název a další vlastnosti  
  
```  
usecase1.Name = "user logs in";  
```  
  
### <a name="example"></a>Příklad  
  
```  
using Microsoft.VisualStudio.Uml.Classes;  
using Microsoft.VisualStudio.Uml.Extensions;  
...  
 void InstantiateObserverPattern (IPackage package, string namePrefix)  
 {    IInterface observer = package.CreateInterface();  
      observer.Name = namePrefix + "Observer";  
      IOperation operation = observer.CreateOperation();  
      operation.Name = "Update";  
      IClass subject = package.CreateClass();  
      subject.Name = namePrefix + "Subject"; ...  
```  
  
## <a name="create-an-association"></a>Vytvoření přidružení  
  
#### <a name="to-create-an-association"></a>Vytvoření přidružení  
  
1.  Získání vlastníka přidružení, což je obvykle balíčku nebo modelu, který obsahuje zdrojový konec relace.  
  
2.  Vyvolání požadovaná metoda vytvořit na vlastníka.  
  
3.  Nastavte vlastnosti relace, například jeho název.  
  
     Příklad:  
  
    ```  
    IAssociation association = subject.Package.CreateAssociation(subject, observer);  
    association .Name = "Observes";  
    ```  
  
4.  Nastavte vlastnosti jednotlivých konci vztahu. Vždy existují dvě `MemberEnds`. Příklad:  
  
    ```  
    association .MemberEnds[0].Name = "subject";   // role name  
    association .MemberEnds[1].Name = "observers"; // role name  
    association .MemberEnds[1].SetBounds("0..*");           
                // multiplicity defaults to "1"  
    association.MemberEnds[0].Aggregation = AggregationKind.Composite;  
    ```  
  
## <a name="create-a-generalization"></a>Vytvoření generalizace  
  
```  
IGeneralization generalization =   
  subclass.CreateGeneralization(superClass);  
```  
  
## <a name="delete-an-element-relationship-or-generalization-from-the-model"></a>Odstranění elementu, relaci nebo generalizace z modelu  
  
```  
anElement.Delete();  
```  
  
 Když odstraníte z modelu prvek:  
  
-   Každý vztah, který odkazuje na to se také odstraní.  
  
-   Také se odstraní všechny obrazce, která znázorněné v diagramu.  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření modelů a diagramů UML](../modeling/extend-uml-models-and-diagrams.md)   
 [Zobrazení modelu UML v diagramech](../modeling/display-a-uml-model-on-diagrams.md)
