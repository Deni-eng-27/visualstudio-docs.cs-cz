---
title: 'IDebugComPlusSymbolProvider2:: LoadSymbolsFromCallback | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- LoadSymbolsFromCallback
- IDebugComPlusSymbolProvider2::LoadSymbolsFromCallback
ms.assetid: 905315ba-8e9b-4889-b9da-98e1441950ad
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 738c9e24a8acfe33d7d3993da0eb5eb96ace1795
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80733364"
---
# <a name="idebugcomplussymbolprovider2loadsymbolsfromcallback"></a>IDebugComPlusSymbolProvider2::LoadSymbolsFromCallback
Načte symboly ladění pomocí zadané metody zpětného volání.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT LoadSymbolsFromCallback(
    ULONG32   ulAppDomainID,
    GUID      guidModule,
    IUnknown* pUnkMetadataImport,
    IUnknown* pUnkCorDebugModule,
    BSTR      bstrModuleName,
    BSTR      bstrSymSearchPath,
    IUnknown* pCallback
);
```

```csharp
int LoadSymbolsFromCallback(
    uint   ulAppDomainID,
    Guid   guidModule,
    object pUnkMetadataImport,
    object pUnkCorDebugModule,
    string bstrModuleName,
    string bstrSymSearchPath,
    object pCallback
);
```

## <a name="parameters"></a>Parametry
`ulAppDomainID`\
pro Identifikátor domény aplikace

`guidModule`\
pro Jedinečný identifikátor modulu

`pUnkMetadataImport`\
pro Objekt, který obsahuje metadata symbolu.

`pUnkCorDebugModule`\
pro Objekt, který implementuje [rozhraní ICorDebugModule](/dotnet/framework/unmanaged-api/debugging/icordebugmodule-interface).

`bstrModuleName`\
pro Název modulu

`bstrSymSearchPath`\
pro Cesta pro vyhledání souboru symbolů

`pCallback`\
pro Objekt, který představuje metodu zpětného volání.

## <a name="return-value"></a>Návratová hodnota
V případě úspěchu vrátí. `S_OK` jinak vrátí kód chyby.

## <a name="example"></a>Příklad
Následující příklad ukazuje, jak implementovat tuto metodu pro objekt **CDebugSymbolProvider** , který zpřístupňuje rozhraní [IDebugComPlusSymbolProvider2](../../../extensibility/debugger/reference/idebugcomplussymbolprovider2.md) .

```cpp
HRESULT CDebugSymbolProvider::LoadSymbolsFromCallback(
    ULONG32 ulAppDomainID,
    GUID guidModule,
    IUnknown *pMetadataImport,
    IUnknown * _pCorModule,
    BSTR bstrModule,
    BSTR bstrSearchPath,
    IUnknown *pCallback)
{
    EMIT_TICK_COUNT("Entry -- Loading symbols for the following target:");
    USES_CONVERSION;
    EmitTickCount(W2A(bstrModule));

    CAutoLock Lock(this);

    HRESULT hr = S_OK;
    CComPtr<IMetaDataImport> pMetadata;
    CComPtr<ICorDebugModule> pCorModule;

    CModule* pmodule = NULL;
    CModule* pmoduleNew = NULL;
    bool fAlreadyLoaded = false;
    Module_ID idModule(ulAppDomainID, guidModule);
    bool fSymbolsLoaded = false;
    DWORD dwCurrentState = 0;

    ASSERT(IsValidObjectPtr(this, CDebugSymbolProvider));
    ASSERT(IsValidInterfacePtr(pMetadataImport, IUnknown));

    METHOD_ENTRY( CDebugSymbolProvider::LoadSymbol );

    IfFalseGo( pMetadataImport, E_INVALIDARG );
    IfFalseGo( _pCorModule, E_INVALIDARG );

    IfFailGo( pMetadataImport->QueryInterface( IID_IMetaDataImport,
              (void**)&pMetadata) );

    IfFailGo( _pCorModule->QueryInterface( IID_ICorDebugModule,
                                           (void**)&pCorModule) );

    ASSERT(guidModule != GUID_NULL);

    fAlreadyLoaded = GetModule( idModule, &pmodule ) == S_OK;

    IfNullGo( pmoduleNew = new CModule, E_OUTOFMEMORY );

    //
    // We are now allowing modules to be created that do not have SymReaders.
    // It is likely there are a number of corner cases being ignored
    // that will require knowledge of the hr result below.
    //
    dwCurrentState = m_pSymProvGroup ? m_pSymProvGroup->GetCurrentState() : 0;
    HRESULT hrLoad = pmoduleNew->Create( idModule,
                                         dwCurrentState,
                                         pMetadata,
                                         pCorModule,
                                         bstrModule,
                                         bstrSearchPath,
                                         pCallback );

    if (hrLoad == S_OK)
    {
        fSymbolsLoaded = true;
    }

    // Remove the old module
    if (fAlreadyLoaded)
    {
        IfFailGo(pmoduleNew->AddEquivalentModulesFrom(pmodule));
        RemoveModule( pmodule );
    }

    IfFailGo( AddModule( pmoduleNew ) );

Error:

    RELEASE (pmodule);
    RELEASE (pmoduleNew);

    if (SUCCEEDED(hr) && !fSymbolsLoaded)
    {
        hr = hrLoad;
    }

    METHOD_EXIT( CDebugSymbolProvider::LoadSymbol, hr );
    EMIT_TICK_COUNT("Exit");
    return hr;
}
```

## <a name="see-also"></a>Viz také
- [IDebugComPlusSymbolProvider2](../../../extensibility/debugger/reference/idebugcomplussymbolprovider2.md)
