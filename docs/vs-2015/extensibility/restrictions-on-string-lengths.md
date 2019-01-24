---
title: Omezení délky řetězců | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, restrictions on string lengths
ms.assetid: 877173d2-ca27-43b3-b1f4-8379f7c5e268
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a7abc4290f784808f98b2c5833c896866ab51799
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54763503"
---
# <a name="restrictions-on-string-lengths"></a>Omezení délky řetězců
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Rozhraní API modulu Plug-in zdroje ovládacího prvku omezení délky řetězce použité v různých funkcí.  
  
## <a name="string-length-values"></a>Hodnoty pro délku řetězce  
  
|Konstanta|Hodnota|  
|--------------|-----------|  
|`SCC_NAME_LEN`|31|  
|`SCC_AUXLABEL_LEN`|31|  
|`SCC_USER_LEN`|31|  
|`SCC_PRJPATH_LEN`|300|  
  
> [!NOTE]
>  Délka nezahrnuje ukončení `null`. Další konstantám s příponou "_velikost" místo "_LEN" zahrnout místa pro ukončení `null`.  
  
|Konstanta|Hodnota|  
|--------------|-----------|  
|SCC_NAME_SIZE|32|  
|SCC_AUXLABEL_SIZE|32|  
|SCC_USER_SIZE|32|  
|SCC_PRJPATH_SIZE|301|  
  
## <a name="see-also"></a>Viz také  
 [Moduly plug-in správy zdrojového kódu](../extensibility/source-control-plug-ins.md)
