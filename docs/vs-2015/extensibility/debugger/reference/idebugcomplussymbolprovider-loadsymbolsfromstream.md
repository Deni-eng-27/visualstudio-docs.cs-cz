---
title: IDebugComPlusSymbolProvider::LoadSymbolsFromStream | Dokumentace Microsoftu
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
- IDebugComPlusSymbolProvider::LoadSymbolsFromStream
- LoadSymbolsFromStream
ms.assetid: 1de272f0-24f4-4548-8b70-a205cddd4727
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ebdb09477fa5d44eeb104c0e12ae7a83ad742b3d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49203109"
---
# <a name="idebugcomplussymbolproviderloadsymbolsfromstream"></a>IDebugComPlusSymbolProvider::LoadSymbolsFromStream
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Načtení ladění symboly uvedené datového proudu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT LoadSymbolsFromStream(  
   ULONG32   ulAppDomainID,  
   GUID      guidModule,  
   ULONGLONG baseAddress,  
   IUnknown* pUnkMetadataImport,  
   IStream*  pStream  
);  
```  
  
```csharp  
int LoadSymbolsFromStream(  
   uint    ulAppDomainID,  
   Guid    guidModule,  
   ulong   baseAddress,  
   object  pUnkMetadataImport,  
   IStream pStream  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ulAppDomainID`  
 [in] Identifikátor domény aplikace.  
  
 `guidModule`  
 [in] Jedinečný identifikátor modulu.  
  
 `baseAddress`  
 [in] Adresa základní paměti.  
  
 `pUnkMetadataImport`  
 [in] Objekt, který obsahuje metadata pro symbol.  
  
 `pStream`  
 [in] Datový proud, který obsahuje symboly.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak pro tuto metodu implementovat **CDebugSymbolProvider** objekt, který zveřejňuje [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md) rozhraní. Volání metody [LoadSymbolsFromStreamWithCorModule](../../../extensibility/debugger/reference/idebugcomplussymbolprovider2-loadsymbolsfromstreamwithcormodule.md) metody.  
  
```cpp#  
HRESULT CDebugSymbolProvider::LoadSymbolsFromStream(  
    ULONG32 ulAppDomainID,  
    GUID guidModule,  
    ULONGLONG baseOffset,  
    IUnknown* pUnkMetadataImport,  
    IStream* pStream  
)  
{  
    return LoadSymbolsFromStreamWithCorModule (ulAppDomainID, guidModule, baseOffset, pUnkMetadataImport, NULL, pStream);  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)

