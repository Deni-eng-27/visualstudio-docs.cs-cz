---
title: IDebugPortSupplier3 | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugPortSupplier3
helpviewer_keywords:
- IDebugPortSupplier3 interface
ms.assetid: e458cd02-2370-4435-8953-17d7a60ce152
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 14a4e9f704cc5a863030ae6041f3d93276ecf18e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669889"
---
# <a name="idebugportsupplier3"></a>IDebugPortSupplier3
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugPortSupplier3](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugportsupplier3).  
  
Toto rozhraní umožňuje volajícímu určit, zda dodavatele portu můžete zachovat porty mezi vyvolání ladicího programu (podle jejich zápis na disk) a potom získá seznam těchto zachovaných portů.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugPortSupplier3 : IDebugPortSupplier2  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Dodavatel port. Tento vlastní port implementuje toto rozhraní pro podporu uchování nebo ukládání informací o portu na disk. Toto rozhraní musí být implementováno na stejný objekt jako [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md) rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) na `IDebugPortSupplier2` rozhraní k získání tohoto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Kromě metod zděděných z [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md) rozhraní, toto rozhraní podporuje následující:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[CanPersistPorts](../../../extensibility/debugger/reference/idebugportsupplier3-canpersistports.md)|Vrátí, zda dodavatele portu můžete zachovaly porty (je zápis na disk) mezi vyvolání ladicího programu.|  
|[EnumPersistedPorts](../../../extensibility/debugger/reference/idebugportsupplier3-enumpersistedports.md)|Vrátí objekt, který je možné vytvořit výčet prostřednictvím všechny porty, které byly vytvořeny na disku podle dodavatele tohoto portu.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud dodavatele portu můžete zachovat porty ve volání, musí implementovat toto rozhraní. Porty by měly být načteny při dodavatele portu je vytvořena instance a zapíšou na disk při zničení dodavatele portu.  
  
 Ladicí stroj obvykle nekomunikuje s dodavatele portu a nebude mít žádný použijte pro toto rozhraní.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)

