---
title: m_action pole | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- m_action field, Task class [.NET Framework debug engines]
ms.assetid: 201838c2-260d-4071-b6c3-f526874e19c9
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: c9d5a55f7e91b22a5b9a867991acbfe404a660fe
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="maction-field"></a>m_action pole
Delegáta, který představuje kód na provedení v <xref:System.Threading.Tasks.Task> objektu.  
  
 **Namespace:**<xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Sestavení:** mscorlib (v mscorlib.dll)  
  
 Protože tento vnitřní člen nemůže získat přístup z rozhraní .NET Framework, je k dispozici společné Intermediate Language (soubor CIL) syntaxi.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
.field assembly object m_action  
```  
  
## <a name="remarks"></a>Poznámky  
 Toto je `action` parametr ve <xref:System.Threading.Tasks.Task.%23ctor%2A> konstruktor.  
  
## <a name="see-also"></a>Viz také  
 [Task – třída](../../extensibility/debugger/task-class-internal-members.md)