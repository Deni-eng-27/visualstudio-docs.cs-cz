---
title: IPropertyProxyEESide::GetManagedViewerCreationData | Dokumentace Microsoftu
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
- IPropertyProxyEESide::GetManagedViewerCreationData
helpviewer_keywords:
- IPropertyProxyEESide::GetManagedViewerCreationData
ms.assetid: c4eb4d60-8816-4d52-bc8d-dffd4f066499
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 90087bfad956427ef3ff59fd7ffdc8b92c9f5687
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42671137"
---
# <a name="ipropertyproxyeesidegetmanagedviewercreationdata"></a>IPropertyProxyEESide::GetManagedViewerCreationData
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IPropertyProxyEESide::GetManagedViewerCreationData](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ipropertyproxyeeside-getmanagedviewercreationdata).  
  
Aby bylo možné vytvořit instanci tohoto prohlížeče načte informace o prohlížeči pro tento typ vlastnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetManagedViewerCreationData(  
   BSTR*                  assemName,  
   IEEDataStorage**       assemBytes,  
   IEEDataStorage**       assemPdb,  
   BSTR*                  className,  
   ASSEMBLYLOCRESOLUTION* alr,  
   BOOL*                  replacementOk  
);  
```  
  
```csharp  
int GetManagedViewerCreationData(  
   out string                     assemName,  
   out IEEDataStorage             assemBytes,  
   out IEEDataStorage             assemPdb,  
   out string                     className,  
   out enum_ASSEMBLYLOCRESOLUTION alr,  
   out int                        replacementOk  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `assemName`  
 [out] Vrátí název sestavení, která uchovává tento objekt.  
  
 `assemBytes`  
 [out] Vrátí [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) objekt, který obsahuje počet bajtů sestavení tohoto objektu (to je hodnota null, pokud nejsou k dispozici žádné bajtů).  
  
 `assemPdb`  
 [out] Vrátí `IEEDataStorage` objekt, který obsahuje symbol ukládání informací pro tento objekt (to je hodnota null, pokud je k dispozici žádné úložiště symbolů).  
  
 `className`  
 [out] Vrací název třídy obsahující tento objekt.  
  
 `alr`  
 [out] Vrátí hodnotu z [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md) výčet označující umístění sestavení.  
  
 `replacementOk`  
 [out] Vrátí nenulovou hodnotu (`TRUE`) Pokud je hodnota tohoto objektu můžete změnit; nula (`FALSE`) je-li objekt je jen pro čtení.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda používá k vytvoření instance spravovaný prohlížeč vizualizérů typů.  
  
## <a name="see-also"></a>Viz také  
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)

