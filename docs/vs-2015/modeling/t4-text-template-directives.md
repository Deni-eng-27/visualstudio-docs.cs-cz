---
title: T4 Direktivy textové šablony | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- text templates, import directive
- text templates, include directive
- text templates, assembly directive
- text templates, output directive
- text templates, directives
- text templates, template directive
ms.assetid: 6898ee02-ebb2-4635-a4e9-350774c13cf2
caps.latest.revision: 83
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 6f5c4c474ad737add8580381e7fda5fb0b0c1afc
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60044834"
---
# <a name="t4-text-template-directives"></a>T4 – direktivy textových šablon
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Direktivy poskytují pokyny stroji, který provádí transformace textových šablon.  
  
 Direktivy mají následující syntaxi:  
  
```  
<#@ DirectiveName [AttributeName = "AttributeValue"] ... #>  
```  
  
 Všechny hodnoty atributů musejí být uzavřeny do dvojitých uvozovek. Pokud samotná hodnota obsahuje uvozovky, musejí být uvozeny znakem \.  
  
 Direktivy jsou zpravidla prvním prvkem v souboru šablony nebo vkládaném souboru. Neměli byste je umísťovat dovnitř bloku kódu `<#...#>`, ani za blok funkcí třídy `<#+...#>`.  
  
 [T4 – direktiva Template](../modeling/t4-template-directive.md)  

```  
<#@ template [language="VB"] [hostspecific="true|TrueFromBase"] [debug="true"] [inherits="templateBaseClass"] [culture="code"] [compilerOptions="options"] [visibility="internal"] [linePragmas="false"] #>  
```  
  
 [T4 – direktiva Parameter](../modeling/t4-parameter-directive.md)  

```  
<#@ parameter type="Full.TypeName" name="ParameterName" #>  
```  
  
 [T4 – direktiva Output](../modeling/t4-output-directive.md)  

```  
<#@ output extension=".fileNameExtension" [encoding="encoding"] #>  
```  
  
 [T4 – direktiva Assembly](../modeling/t4-assembly-directive.md)  

```  
<#@ assembly name="[assembly strong name|assembly file name]" #>  
```  
  
 [T4 – direktiva Import](../modeling/t4-import-directive.md)  

```  
<#@ import namespace="namespace" #>  
```  
  
 [T4 – direktiva Include](../modeling/t4-include-directive.md)  

```  
<#@ include file="filePath" #>  
```  
  
 [T4 – direktiva CleanUpBehavior](../modeling/t4-cleanupbehavior-directive.md)  

```  
<#@ CleanupBehavior processor="T4VSHost" CleanupAfterProcessingtemplate="true" #>  
```  
  
 Navíc můžete vytvářet své vlastní direktivy. Další informace najdete v tématu [vytváření vlastních procesorů textových šablon T4 – direktiva](../modeling/creating-custom-t4-text-template-directive-processors.md). Pokud pomocí sady Visualization and Modeling SDK vytvoříte jazyk domény (DSL), vygeneruje se procesor direktiv jako součást tohoto kódu DSL.
