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
ms.openlocfilehash: e7d3a3f966563e9d32294547ad604246ccd046e3
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63446221"
---
# <a name="iwebappdiagnosticsobjectinitializationinitialize"></a>IWebAppDiagnosticsObjectInitialization::Initialize
Inicializuje objekty vytvořené pomocí [IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md).  
  
> [!IMPORTANT]
> [Iwebappdiagnosticsobjectinitialization – rozhraní](../../winscript/reference/iwebappdiagnosticsobjectinitialization-interface.md) se nachází v souboru activdbg100.h.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Initialize(        [in, annotation("__in")] HANDLE_PTR hPassedHandle,        [in, annotation("__in")] IUnknown* pDebugApplication        );  
```  
  
#### <a name="parameters"></a>Parametry  
 `hPassedHandle`  
 Popisovač, který byl předán [IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md) metodu `hPassToObject` parametru.  
  
 `pDebugApplication`  
 PDM aplikace, pomocí kterého byl vytvořen objekt.