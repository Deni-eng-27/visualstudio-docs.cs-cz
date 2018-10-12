---
title: IntelliSenseHostFlags | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IntellisenseHostFlags
helpviewer_keywords:
- IntelliSense, IntellisenseHostFlags enumeration
- IntellisenseHostFlags enumeration
ms.assetid: 0930640b-eb84-48ef-a8f7-d4268f55c99c
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2fdc08f6e71a6da718f37e88f40d71df00ee89ab
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49190993"
---
# <a name="intellisensehostflags"></a>IntelliSenseHostFlags
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Určuje příznaky hostitele technologie IntelliSense.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum IntellisenseHostFlags  
{  
    IHF_READONLYCONTEXT      = 0x00000001  
    IHF_NOSEPARATESUBJECT    = 0x00000002  
    IHF_SINGLELINESUBJECT    = 0x00000004  
    IHF_FORCECOMMITTOCONTEXT = 0x00000008  
    IHF_OVERTYPE             = 0x00000010  
};  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Členové|Popis|  
|-------------|-----------------|  
|`IHF_READONLYCONTEXT`|Vyrovnávací paměti kontextu je jen pro čtení.|  
|`IHF_NOSEPARATESUBJECT`|Žádný text předmětu. Vyrovnávací paměti kontextu obsahuje cílový IntelliSense (implikuje `!IHF_READONLYCONTEXT`).|  
|`IHF_SINGLELINESUBJECT`|Text předmětu není více-řádku podporující.|  
|`IHF_FORCECOMMITTOCONTEXT`|Stejné jako `CanCommitIntoReadOnlyBuffer`.|  
|`IHF_OVERTYPE`|Úpravy (v předmětu nebo kontext) by mělo být provedeno režim přepisování.|  
  
## <a name="requirements"></a>Požadavky  
 SingleFileeditor.idl  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.TextManager.Interop>

