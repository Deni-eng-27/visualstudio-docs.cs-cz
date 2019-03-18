---
title: IWebAppDiagnosticsObjectInitialization::Initialize | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IWebAppDiagnosticsObjectInitialization::Initialize
ms.assetid: 7ccfac28-9f65-4e1c-a0fb-a8a6c7f75b63
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d887872c1735aabd0bc19d8de362f10044685bac
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58147355"
---
# <a name="iwebappdiagnosticsobjectinitializationinitialize"></a>IWebAppDiagnosticsObjectInitialization::Initialize
Inicializuje objekty vytvořené pomocí [IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md).  
  
> [!IMPORTANT]
>  [Iwebappdiagnosticsobjectinitialization – rozhraní](../../winscript/reference/iwebappdiagnosticsobjectinitialization-interface.md) se nachází v souboru activdbg100.h.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Initialize(        [in, annotation("__in")] HANDLE_PTR hPassedHandle,        [in, annotation("__in")] IUnknown* pDebugApplication        );  
```  
  
#### <a name="parameters"></a>Parametry  
 `hPassedHandle`  
 Popisovač, který byl předán [IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md) metodu `hPassToObject` parametru.  
  
 `pDebugApplication`  
 PDM aplikace, pomocí kterého byl vytvořen objekt.