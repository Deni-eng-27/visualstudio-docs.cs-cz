---
title: Idebugsessionprovider – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugSessionProvider interface
ms.assetid: 1b898423-7af9-44f5-8dda-987005309c99
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d6d17546d5461a1ad76b144bf2652672ab4aa675
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54345145"
---
# <a name="idebugsessionprovider-interface"></a>IDebugSessionProvider – rozhraní
Primární rozhraní poskytnuté ladicím programu integrované vývojové prostředí umožňující hostitele a jazyk zahájit ladění. Zjistí ladicí relace pro běžící aplikaci. Toto rozhraní je implementováno ladění správcem počítače.  
  
 Kromě metod zděděných z `IUnknown`, `IDebugSessionProvider` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugSessionProvider::StartDebugSession](../../winscript/reference/idebugsessionprovider-startdebugsession.md)|Spustí relaci ladění pomocí zadané aplikace.|