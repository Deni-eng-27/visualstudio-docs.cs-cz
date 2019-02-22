---
title: DBG_ATTRIB_FLAGS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DBG_ATTRIB_FLAGS
helpviewer_keywords:
- DBGPROP_ATTRIB_FLAGS enumerations
ms.assetid: 2f13e601-dadc-476e-a8ec-01c4515082e7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 831d1326d88e70ffaba2cc0c242c55d7325be705
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56689327"
---
# <a name="dbgattribflags"></a>DBG_ATTRIB_FLAGS
Popisuje různé atributy pro [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) nebo [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) rozhraní. Člen [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktury.

## <a name="syntax"></a>Syntaxe

```cpp
#define DBG_ATTRIB_NONE                 0x0000000000000000,
#define DBG_ATTRIB_ALL                  0x00000000ffffffff,

// Attributes about the object itself

#define DBG_ATTRIB_OBJ_IS_EXPANDABLE    0x0000000000000001,
#define DBG_ATTRIB_OBJ_HAS_ID           0x0000000000000002,
#define DBG_ATTRIB_OBJ_CAN_HAVE_ID      0x0000000000000004,

// Attributes about the value of the object

#define DBG_ATTRIB_VALUE_READONLY       0x0000000000000010,
#define DBG_ATTRIB_VALUE_ERROR          0x0000000000000020,
#define DBG_ATTRIB_VALUE_SIDE_EFFECT    0x0000000000000040,
#define DBG_ATTRIB_OVERLOADED_CONTAINER 0x0000000000000080,
#define DBG_ATTRIB_VALUE_BOOLEAN        0x0000000000000100,
#define DBG_ATTRIB_VALUE_BOOLEAN_TRUE   0x0000000000000200,
#define DBG_ATTRIB_VALUE_INVALID        0x0000000000000400,
#define DBG_ATTRIB_VALUE_NAT            0x0000000000000800,
#define DBG_ATTRIB_VALUE_AUTOEXPANDED   0x0000000000001000,
#define DBG_ATTRIB_VALUE_TIMEOUT        0x0000000000002000,
#define DBG_ATTRIB_VALUE_RAW_STRING     0x0000000000004000,
#define DBG_ATTRIB_VALUE_CUSTOM_VIEWER  0x0000000000008000,

// Attributes about field access types for the object

#define DBG_ATTRIB_ACCESS_NONE          0x0000000000010000,
#define DBG_ATTRIB_ACCESS_PUBLIC        0x0000000000020000,
#define DBG_ATTRIB_ACCESS_PRIVATE       0x0000000000040000,
#define DBG_ATTRIB_ACCESS_PROTECTED     0x0000000000080000,
#define DBG_ATTRIB_ACCESS_FINAL         0x0000000000100000,
#define DBG_ATTRIB_ACCESS_ALL           0x00000000001f0000,

// Attributes for the storage types of the object

#define DBG_ATTRIB_STORAGE_NONE         0x0000000001000000,
#define DBG_ATTRIB_STORAGE_GLOBAL       0x0000000002000000,
#define DBG_ATTRIB_STORAGE_STATIC       0x0000000004000000,
#define DBG_ATTRIB_STORAGE_REGISTER     0x0000000008000000,
#define DBG_ATTRIB_STORAGE_ALL          0x000000000f000000,

// Attributes for the type modifiers on the object

#define DBG_ATTRIB_TYPE_NONE            0x0000000100000000,
#define DBG_ATTRIB_TYPE_VIRTUAL         0x0000000200000000,
#define DBG_ATTRIB_TYPE_CONSTANT        0x0000000400000000,
#define DBG_ATTRIB_TYPE_SYNCHRONIZED    0x0000000800000000,
#define DBG_ATTRIB_TYPE_VOLATILE        0x0000001000000000,
#define DBG_ATTRIB_TYPE_ALL             0x0000001f00000000,

// Attributes that describe the type of object

#define DBG_ATTRIB_DATA                 0x0000010000000000,
#define DBG_ATTRIB_METHOD               0x0000020000000000,
#define DBG_ATTRIB_PROPERTY             0x0000040000000000,
#define DBG_ATTRIB_CLASS                0x0000080000000000,
#define DBG_ATTRIB_BASECLASS            0x0000100000000000,
#define DBG_ATTRIB_INTERFACE            0x0000200000000000,
#define DBG_ATTRIB_INNERCLASS           0x0000400000000000,
#define DBG_ATTRIB_MOSTDERIVED          0x0000800000000000,
#define DBG_ATTRIB_CHILD_ALL            0x0000ff0000000000,

// Miscellaneous attributes

#define DBG_ATTRIB_MULTI_CUSTOM_VIEWERS 0x0001000000000000

typedef UINT64 DBG_ATTRIB_FLAGS;
```

```csharp
public const int DBG_ATTRIB_NONE                 = 0x0000000000000000,
public const int DBG_ATTRIB_ALL                  = 0x00000000ffffffff,

// Attributes about the object itself

public const int DBG_ATTRIB_OBJ_IS_EXPANDABLE    = 0x0000000000000001,
public const int DBG_ATTRIB_OBJ_HAS_ID           = 0x0000000000000002,
public const int DBG_ATTRIB_OBJ_CAN_HAVE_ID      = 0x0000000000000004,

// Attributes about the value of the object

public const int DBG_ATTRIB_VALUE_READONLY       = 0x0000000000000010,
public const int DBG_ATTRIB_VALUE_ERROR          = 0x0000000000000020,
public const int DBG_ATTRIB_VALUE_SIDE_EFFECT    = 0x0000000000000040,
public const int DBG_ATTRIB_OVERLOADED_CONTAINER = 0x0000000000000080,
public const int DBG_ATTRIB_VALUE_BOOLEAN        = 0x0000000000000100,
public const int DBG_ATTRIB_VALUE_BOOLEAN_TRUE   = 0x0000000000000200,
public const int DBG_ATTRIB_VALUE_INVALID        = 0x0000000000000400,
public const int DBG_ATTRIB_VALUE_NAT            = 0x0000000000000800,
public const int DBG_ATTRIB_VALUE_AUTOEXPANDED   = 0x0000000000001000,
public const int DBG_ATTRIB_VALUE_TIMEOUT        = 0x0000000000002000,
public const int DBG_ATTRIB_VALUE_RAW_STRING     = 0x0000000000004000,
public const int DBG_ATTRIB_VALUE_CUSTOM_VIEWER  = 0x0000000000008000,

// Attributes about field access types for the object

public const int DBG_ATTRIB_ACCESS_NONE          = 0x0000000000010000,
public const int DBG_ATTRIB_ACCESS_PUBLIC        = 0x0000000000020000,
public const int DBG_ATTRIB_ACCESS_PRIVATE       = 0x0000000000040000,
public const int DBG_ATTRIB_ACCESS_PROTECTED     = 0x0000000000080000,
public const int DBG_ATTRIB_ACCESS_FINAL         = 0x0000000000100000,
public const int DBG_ATTRIB_ACCESS_ALL           = 0x00000000001f0000,

// Attributes for the storage types of the object

public const int DBG_ATTRIB_STORAGE_NONE         = 0x0000000001000000,
public const int DBG_ATTRIB_STORAGE_GLOBAL       = 0x0000000002000000,
public const int DBG_ATTRIB_STORAGE_STATIC       = 0x0000000004000000,
public const int DBG_ATTRIB_STORAGE_REGISTER     = 0x0000000008000000,
public const int DBG_ATTRIB_STORAGE_ALL          = 0x000000000f000000,

// Attributes for the type modifiers on the object

public const int DBG_ATTRIB_TYPE_NONE            = 0x0000000100000000,
public const int DBG_ATTRIB_TYPE_VIRTUAL         = 0x0000000200000000,
public const int DBG_ATTRIB_TYPE_CONSTANT        = 0x0000000400000000,
public const int DBG_ATTRIB_TYPE_SYNCHRONIZED    = 0x0000000800000000,
public const int DBG_ATTRIB_TYPE_VOLATILE        = 0x0000001000000000,
public const int DBG_ATTRIB_TYPE_ALL             = 0x0000001f00000000,

// Attributes that describe the type of object

public const int DBG_ATTRIB_DATA                 = 0x0000010000000000,
public const int DBG_ATTRIB_METHOD               = 0x0000020000000000,
public const int DBG_ATTRIB_PROPERTY             = 0x0000040000000000,
public const int DBG_ATTRIB_CLASS                = 0x0000080000000000,
public const int DBG_ATTRIB_BASECLASS            = 0x0000100000000000,
public const int DBG_ATTRIB_INTERFACE            = 0x0000200000000000,
public const int DBG_ATTRIB_INNERCLASS           = 0x0000400000000000,
public const int DBG_ATTRIB_MOSTDERIVED          = 0x0000800000000000,
public const int DBG_ATTRIB_CHILD_ALL            = 0x0000ff0000000000,

// Miscellaneous attributes

public const int DBG_ATTRIB_MULTI_CUSTOM_VIEWERS = 0x0001000000000000
```

## <a name="members"></a>Členové
 DBG_ATTRIB_NONE označuje žádné atributy.

 DBG_ATTRIB_ALL označuje všechny atributy.

 DBG_ATTRIB_OBJ_IS_EXPANDABLE znamená, že odkaz nebo vlastnost má podřízené položky.

 DBG_ATTRIB_OBJ_HAS_ID označuje, zda byl vytvořen ID pro tento objekt.

 DBG_ATTRIB_OBJ_CAN_HAVE_ID označuje, že ID pro tento objekt je možné vytvořit.

 DBG_ATTRIB_VALUE_READONLY označuje, že hodnota je jen pro čtení.

 DBG_ATTRIB_VALUE_ERROR značí, že je hodnota chybu.

 DBG_ATTRIB_VALUE_SIDE_EFFECT naznačuje, že hodnocení vedlejší účinek.

 DBG_ATTRIB_OVERLOADED_CONTAINER označuje, že tato vlastnost je ve skutečnosti kontejner přetížení.

 DBG_ATTRIB_VALUE_BOOLEAN znamená, že hodnota ve `DEBUG_PROPERTY_INFO::bstrValue` je logická hodnota.

 DBG_ATTRIB_VALUE_BOOLEAN_TRUE znamená, že hodnota ve `DEBUG_PROPERTY_INFO::bstrValue` je logická hodnota a `TRUE`.

 DBG_ATTRIB_VALUE_INVALID znamená, že hodnota ve `DEBUG_PROPERTY_INFO::bstrValue` není platný.

 DBG_ATTRIB_VALUE_NAT znamená, že hodnota ve `DEBUG_PROPERTY_INFO::bstrValue` je "*není věc*" (NAT). NAT popisuje zaregistrovat u procesorů Intel 64-bit označuje příznakem odložené spekulativního výjimky.

 DBG_ATTRIB_VALUE_AUTOEXPANDED znamená, že hodnota ve `DEBUG_PROPERTY_INFO::bstrValue` byla pravděpodobně automaticky rozbaleny.

 DBG_ATTRIB_VALUE_TIMEOUT znamená, že k vyhodnocení vypršel.

 DBG_ATTRIB_VALUE_RAW_STRING znamená, že hodnota ve `DEBUG_PROPERTY_INFO::bstrValue` může být reprezentován nezpracovaného řetězce.

 DBG_ATTRIB_VALUE_CUSTOM_VIEWER znamená, že tato vlastnost má alespoň jednu vlastní prohlížeč s ním spojená.

 Určuje objekt, který nemá DBG_ATTRIB_ACCESS_NONE `public`, `private`, ani `protected` typ přístupu.

 DBG_ATTRIB_ACCESS_PUBLIC určuje objekt, který má přístup public.

 DBG_ATTRIB_ACCESS_PRIVATE určuje objekt, který má privátní přístup.

 DBG_ATTRIB_ACCESS_PROTECTED určuje objekt, který chrání přístup.

 DBG_ATTRIB_ACCESS_FINAL označuje objekt s posledním přístupem.

 Maska DBG_ATTRIB_ACCESS_ALL extrahovat přístup atributy z `DBG_ATTRIB_FLAGS`.

 DBG_ATTRIB_STORAGE_NONE znamená, že není zadaný žádný typ úložiště.

 Označuje DBG_ATTRIB_STORAGE_GLOBAL globální úložiště.

 Označuje DBG_ATTRIB_STORAGE_STATIC statického úložiště.

 Označuje DBG_ATTRIB_STORAGE_REGISTER úložiště do registru.

 Maska DBG_ATTRIB_STORAGE_ALL extrahovat úložiště atributů z `DBG_ATTRIB_FLAGS`.

 DBG_ATTRIB_TYPE_NONE označuje, že neexistuje žádná modifikátor typu.

 DBG_ATTRIB_TYPE_VIRTUAL označuje, že je virtuálního typu objektu.

 DBG_ATTRIB_TYPE_CONSTANT označuje konstantní typ objektu.

 DBG_ATTRIB_TYPE_SYNCHRONIZED označuje, že typ objektu, který se synchronizují.

 DBG_ATTRIB_TYPE_VOLATILE označuje, že typ objektu, který je typu volatile.

 Atributy DBG_ATTRIB_TYPE_ALL maska extrahovat typ ze `DBG_ATTRIB_FLAGS`.

 DBG_ATTRIB_DATA označuje, zda tento objekt je datové pole.

 DBG_ATTRIB_METHOD označuje, zda tento objekt je metoda.

 DBG_ATTRIB_PROPERTY označuje, zda tento objekt je vlastnost.

 DBG_ATTRIB_CLASS označuje, že je tento objekt třídy.

 DBG_ATTRIB_BASECLASS označuje, zda tento objekt je základní třídou.

 DBG_ATTRIB_INTERFACE označuje, zda tento objekt je rozhraní.

 DBG_ATTRIB_INNERCLASS označuje, že tento objekt je vnitřní třídu.

 DBG_ATTRIB_MOSTDERIVED znamená, že je tento objekt "*nejvíce odvozenému*". Termín "*nejvíce odvozenému*" znamená, že skutečný typ objektu a ne na typu odkaz.

 DBG_ATTRIB_CHILD_ALL označuje maskou `DBG_ATTRIB_DATA` prostřednictvím `DBG_ATTRIB_MOSTDERIVED`.

 DBG_ATTRIB_MULTI_CUSTOM_VIEWERS znamená, že objekt obsahuje více vlastních prohlížečů, které s ním spojená.

## <a name="remarks"></a>Poznámky

> [!NOTE]
>  Hodnoty v tento výčet nejsou ve skutečnosti definovány v sestavení pro jazyk C#. Definice místo toho musíte zkopírovat do zdrojového souboru.

 Tyto příznaky se taky používají k filtrování podřízených objektů objektu, například když předána jako argument [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md). Hodnoty lze kombinovat pomocí logické bitové `OR`.

 `DBG_ATTRIB_VALUE_CUSTOM_VIEWER` Příznak slouží jako ukazatel toho k [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] získat [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) rozhraní z [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) rozhraní a volání [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) seznam vlastních prohlížečů.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
- [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)
- [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)
- [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)