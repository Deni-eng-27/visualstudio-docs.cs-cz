---
title: Automatické formátování ve službě starší verze jazyka | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- language services, automatic formatting
ms.assetid: c210fc94-77bd-4694-b312-045087d8a549
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 19c36f5a31c6d3ed7284922bc830ea4925da5833
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49246724"
---
# <a name="automatic-formatting-in-a-legacy-language-service"></a>Automatické formátování ve službě starší verze jazyka
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Automatické formátování, služba jazyka automaticky vloží fragment kódu, když uživatel zahájí na typ známé kód konstrukce.  
  
## <a name="automatic-formatting-behavior"></a>Chování automatické formátování  
 Například když zadáte `if`, služba jazyka automaticky vloží odpovídající složené závorky, nebo pokud stisknete klávesu ENTER, služba jazyka vynutí kurzor na nový řádek do úrovně odpovídající odsazení, podle toho, jestli předchozí řádek se otevře nový obor.  
  
 Příkaz Filtr používá pro ostatní služby jazyka je také možné pro automatické formátování. Můžete také zvýraznit odpovídající složené závorky voláním <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.HighlightMatchingBrace%2A>.  
  
## <a name="see-also"></a>Viz také  
 [Vývoj služby starší verze jazyka](../../extensibility/internals/developing-a-legacy-language-service.md)

