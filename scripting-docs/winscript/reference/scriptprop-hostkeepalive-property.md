---
title: SCRIPTPROP_HOSTKEEPALIVE Property | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: bfa199f2-28ba-4320-bc0f-2320fad018bd
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3724bfcb1ec42617cda4c89269cb0160accafb1a
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58150202"
---
# <a name="scriptprophostkeepalive-property"></a>SCRIPTPROP_HOSTKEEPALIVE – vlastnost
Slouží k určení, zda skriptovací stroj nutné udržovat plně funkční, pokud existují zbývající odkazy.  
  
 Použití [IActiveScriptProperty::SetProperty](../../winscript/reference/iactivescriptproperty-setproperty.md) pro tuto vlastnost nastavte na `true`. Pokud je tato vlastnost nastavená na `true`, se ukládají skriptovací stroj plně funkční, dokud není alespoň jeden nezpracovaných reference na samotný skriptovací modul nebo na `IDispatch` ukazatel na objekt jazyka JavaScript, který je vytvořen pomocí skriptování modul. Pokud je tato vlastnost nastavena na `true`, byste měli nejsou explicitně zavřít nebo obnovit skriptovací stroj s použitím [IActiveScript::Close](../../winscript/reference/iactivescript-close.md) nebo [IActiveScript::SetScriptState](../../winscript/reference/iactivescript-setscriptstate.md) metody. Uvolnění posledního odkazu na objekt skript vypne skriptovací stroj.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
#define SCRIPTPROP_HOSTKEEPALIVE 0x70000004  
```  
  
## <a name="requirements"></a>Požadavky  
 Tato vlastnost se zobrazí pouze ve verzi activscp.idl, který je nainstalován pomocí [!INCLUDE[win8](../../javascript/includes/win8-md.md)], s 2707082 KB pro Internet Explorer 8 na [!INCLUDE[win7](../../winscript/reference/includes/win7-md.md)], nebo s 2722913 KB pro Internet Explorer 9 na [!INCLUDE[win7](../../winscript/reference/includes/win7-md.md)] nebo [!INCLUDE[vista_first](../../winscript/reference/includes/vista-first-md.md)].