---
title: m_stateObject pole | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: m_stateObject field, Task class [.NET Framework debug engines]
ms.assetid: 68c54b22-3e1c-4031-b9c7-b972c519d8a0
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 85e8648fd757c6cdb7910123b3cd861f7abb3371
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="mstateobject-field"></a>m_stateObject pole
Objekt, který představuje data, která budou používat akce.  
  
 **Namespace:**<xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Sestavení:** mscorlib (v mscorlib.dll)  
  
 Protože tento vnitřní člen nemůže získat přístup z rozhraní .NET Framework, je k dispozici společné Intermediate Language (soubor CIL) syntaxi.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
.field assembly object m_stateObject  
```  
  
## <a name="remarks"></a>Poznámky  
 Toto je `state` parametr ve <xref:System.Threading.Tasks.Task.%23ctor%2A> konstruktor. Je také základní pole pro <xref:System.Threading.Tasks.Task.AsyncState%2A?displayProperty=fullName> vlastnost.  
  
## <a name="see-also"></a>Viz také  
 [Task – třída](../../extensibility/debugger/task-class-internal-members.md)