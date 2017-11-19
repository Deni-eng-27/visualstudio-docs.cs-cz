---
title: "Čtení modelů a diagramů v jiných edicích sady Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: models, versions of Visual Studio
ms.assetid: 46eee279-a9e4-4742-a024-5bd2cf032b86
caps.latest.revision: "20"
author: alexhomer1
ms.author: ahomer
manager: douge
ms.openlocfilehash: 704c69efa4e0495a1a4aa7545fa6ba100488afe9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="read-models-and-diagrams-in-other-visual-studio-editions"></a>Čtení modelů a diagramů v jiných edicích sady Visual Studio
Při otevření modelu ve verzi Visual Studia, která nepodporuje vytvoření modelu, otevře se model v režimu jen pro čtení. V tomto režimu můžete změnit rozložení diagramy, ale model nelze změnit.  
  
 Informace, které verze sady Visual Studio podporují vytváření modelu, najdete v tématu [verze podpora architektura a modelování nástroje](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
## <a name="obtaining-access-to-a-model-and-diagrams"></a>Získat přístup k modelu a diagramy  
 Číst diagram závislostí, musíte nejprve pomocí sady Visual Studio otevřete projekt modelování a potom jej otevřete v něm.  
  
 Z tohoto důvodu Pokud si chcete přečíst diagram závislostí, musí máte také přístup k modelování projektu, ve kterém byla vytvořena. To provedete buď přístup k projektu ze [!INCLUDE[esprscc](../code-quality/includes/esprscc_md.md)], nebo prostřednictvím provedeného kopírování souborů projektu.  
  
> [!NOTE]
>  To neplatí kódu maps a rozhraní .NET třídy diagramy generované z kódu. Tyto diagramy lze zobrazit nezávisle na projekt modelování.  
  
 Minimální sadu souborů, které je třeba číst diagram závislostí, vypadá takto:  
  
-   Dva diagram soubory pro diagram, který chcete číst, například **MyDiagram.classdiagram a MyDiagram.classdiagram.layout**.  
  
    > [!NOTE]
    >  Pro závislosti diagramy, měli byste také mít soubor s názvem *MyDiagram***. layerdiagram.suppressions**.  
  
-   Modelování souboru projektu (**MyModel.modelproj**)  
  
-   V kořenovém souboru modelu (**ModelDefinition\MyModel.uml**)  
  
-   Soubory balíčku pro všechny balíčky v diagramu odkazuje (**ModelDefinition\MyPackage.uml**)  
  
## <a name="changes-that-you-can-make-in-read-only-mode"></a>Změny provedené v režimu jen pro čtení  
 Pokud otevřete model a jeho diagramů ve verzi Visual Studia, která nepodporuje model vytváření, nelze změnit modelu. To znamená nelze změnit elementů a vztahů, které se zobrazují na diagramy nebo v Průzkumníku modelu. Však můžete provádět některé změny v rozložení diagramy:  
  
-   Změna uspořádání tvarů a konektory v diagramu.  
  
-   Rozbalit nebo sbalit obrazce.  
  
 Můžete uložit tyto změny. Pokud chcete provedené změny ostatním uživatelům, je nutné alespoň odeslat aktualizovaný **.layout** soubory.  
  
##  <a name="RelatedTopics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Diagramy závislost: referenční dokumentace](../modeling/layer-diagrams-reference.md)|Diagram vrstev ukazuje strukturu stávající nebo navrhované architektury. Když dojde k zapsání kódu, ho můžete automaticky ověřit diagram vrstev.|  
  
## <a name="see-also"></a>Viz také  
 [Vytváření modelů pro aplikaci](../modeling/create-models-for-your-app.md)