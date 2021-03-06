---
title: Registrace vlastního ladicího modulu | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debug engines, registering
ms.assetid: 9984cd3d-d34f-4662-9ace-31766499abf5
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a664385594f139e2c3c5a18a0d8a59e23c13df0a
ms.sourcegitcommit: 4b29efeb3a5f05888422417c4ee236e07197fb94
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/11/2020
ms.locfileid: "90011837"
---
# <a name="register-a-custom-debug-engine"></a>Registrace vlastního ladicího stroje
Ladicí modul se musí zaregistrovat jako objekt pro vytváření tříd, podle konvencí COM a také registrovat v aplikaci Visual Studio prostřednictvím podklíče registru sady Visual Studio.

> [!NOTE]
> Příklad, jak zaregistrovat ladicí stroj v ukázce TextInterpreter, který je sestaven jako součást [kurzu: sestavení ladicího stroje pomocí ATL com](/previous-versions/bb147024(v=vs.90)).

## <a name="dll-server-process"></a>Proces serveru DLL
 Ladicí stroj se obvykle nastavuje ve vlastní knihovně DLL jako server COM. V takovém případě musí ladit stroj zaregistrovat identifikátor CLSID svého objektu pro vytváření tříd pomocí modelu COM, aby k němu mohl přistupovat Visual Studio. Ladicí stroj se pak musí zaregistrovat v aplikaci Visual Studio, aby bylo možné vytvořit jakékoli vlastnosti (jinak označované jako metriky), které ladicí stroj podporuje. Volba metrik zapsaná do podklíče registru sady Visual Studio závisí na funkcích, které ladicí stroj podporuje.

 [Pomocníka sady SDK pro ladění](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) popisuje nejen umístění registru potřebná k registraci ladicího stroje. Popisuje také knihovnu *dbgmetric. lib* , která obsahuje řadu užitečných funkcí a deklarací pro vývojáře v jazyce C++, které usnadňují práci s registrem.

### <a name="example"></a>Příklad
 Následující příklad (z ukázky TextInterpreter) ukazuje, jak používat `SetMetric` funkci (z *dbgmetric. lib*) k registraci ladicího stroje se sadou Visual Studio. Předávané metriky jsou také definovány v *dbgmetric. lib*.

> [!NOTE]
> TextInterpreter je základní ladicí stroj; nenastavuje se, a proto se neregistruje – žádné další funkce. Ucelený ladicí stroj by měl celý seznam `SetMetric` volání nebo jejich ekvivalent, jeden pro každou funkci, kterou ladicí stroj podporuje.

```
// Define base registry subkey to Visual Studio.
static const WCHAR strRegistrationRoot[] = L"Software\\Microsoft\\VisualStudio\\8.0";

HRESULT CTextInterpreterModule::RegisterServer(BOOL bRegTypeLib, const CLSID * pCLSID)
{
    SetMetric(metrictypeEngine, __uuidof(Engine), metricName, L"Text File", false, strRegistrationRoot);
    SetMetric(metrictypeEngine, __uuidof(Engine), metricCLSID, CLSID_Engine, false, strRegistrationRoot);
    SetMetric(metrictypeEngine, __uuidof(Engine), metricProgramProvider, CLSID_MsProgramProvider, false, strRegistrationRoot);

    return base::RegisterServer(bRegTypeLib, pCLSID);
}
```

## <a name="see-also"></a>Viz také:
- [Vytvoření vlastního ladicího stroje](../../extensibility/debugger/creating-a-custom-debug-engine.md)
- [Pomocníka sady SDK pro ladění](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)
- [Kurz: sestavení ladicího stroje pomocí ATL COM](/previous-versions/bb147024(v=vs.90))