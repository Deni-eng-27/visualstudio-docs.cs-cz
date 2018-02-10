---
title: "Speciální řídicí znaky | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- special characters to escape
- msbuild, special characters to escape
ms.assetid: 5b5172c3-41e4-4f38-a16f-2aeac831a5fc
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: b79a497af179f0038f09f2455ed206a0f99aeddc
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="special-characters-to-escape"></a>Speciální řídicí znaky
Speciální znaky, je nutné uvést pouze v případě, že mají zvláštní význam v kontextu, ve kterém se právě používají. Například se tedy hvězdička (*) je speciální znak pouze v atributech "Zahrnout" a "Vyloučit" definice položky, nebo volání <xref:Microsoft.Build.Tasks.CreateItem>. Ve všech ostatních případech se tedy hvězdička považován za literálu hvězdičky. Pokud nepotřebujete, abyste se vyhnuli hvězdičky everywhere v souborech projektu, to tak neškodí.  
  
 Použít zápis %*xx* místo speciální znak, kde *xx* představuje šestnáctkové hodnoty znaků ASCII. Například jako literál znak používat hvězdičku (*), použijte hodnotu `%2A`.  
  
 Úplný seznam speciální řídicí znaky takto:  
  
|Znak|Popis|  
|---------------|-----------------|  
|%|Symbol procent, slouží k odkazování metadat.|  
|$|Dolaru slouží k odkazování vlastnosti.|  
|@|Znak, slouží k odkazování položky seznamů.|  
|(|Otevřete závorky, použít v seznamech.|  
|)|Zavřete závorky, použít v seznamech.|  
|`|Apostrof (nebo značky), používají v podmínkách a jiné výrazy.|  
|;|Středník, oddělovač seznamu.|  
|?|Otazník, zástupný znak při popisu specifikaci souboru v části na položku vložit/vyloučit.|  
|*|Znak hvězdičky zástupný znak při popisu specifikaci souboru v části na položku vložit/vyloučit.|  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vyhnuli speciální znaky v nástroji MSBuild](../msbuild/how-to-escape-special-characters-in-msbuild.md)   
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)