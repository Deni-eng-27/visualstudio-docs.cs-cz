---
title: Třída VsgDbg | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 6722263c-ccef-40c7-a0ae-87a863fbab00
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4051a02de6a046621e62c21b4d2399b5a2703cb8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62895189"
---
# <a name="vsgdbg-class"></a>VsgDbg – třída
Reprezentuje rozhraní pro programovací řízení součásti diagnostiky grafiky v aplikaci.

## <a name="syntax"></a>Syntaxe

```C++
class VsgDbg;
```

## <a name="members"></a>Členové
 `VsgDbg` Třída podporuje následující členy.

### <a name="public-constructors"></a>Veřejné konstruktory

|Název|Popis|
|----------|-----------------|
|[VsgDbg::VsgDbg (konstruktor)](vsgdbg-vsgdbg-constructor.md)|Vytvoří instanci objektu `VsgDbg` třídy a volitelně připraví komponentu v aplikaci diagnostiky grafiky k aktivně zachycení a zaznamenání grafických informací.|
|[VsgDbg::~VsgDbg (destruktor)](vsgdbg-tilde-vsgdbg-destructor.md)|Odstraní instanci `VsgDbg` třídy.|

### <a name="public-methods"></a>Veřejné metody

|Název|Popis|
|----------|-----------------|
|[AddMessage](addmessage.md)|Přidá vlastní zprávu pro diagnostiku grafiky HUD (zobrazení vedoucí nahoru).|
|[BeginCapture](begincapture.md)|Začne sběr intervalu, který bude končit `EndCapture`.|
|[CaptureCurrentFrame](capturecurrentframe.md)|Zaznamená zbytek aktuálního snímku do souboru protokolu grafiky.|
|[Copy (zachytávání prostřednictvím kódu programu)](copy-programmatic-capture.md)|Zkopíruje obsah aktivní grafiky (.vsglog) protokolu do nového souboru.|
|[EndCapture](endcapture.md)|Končí zachycení interval, který byl spuštěn s `BeginCapture`.|
|[Init](init.md)|Připraví komponentu v aplikaci diagnostiky grafiky k aktivně zachycení a zaznamenání grafických informací.|
|[ToggleHUD](togglehud.md)|Přepíná překrytí HUD diagnostiky grafiky, nebo vypnout.|
|[UnInit](uninit.md)|Soubor protokolu grafiky dokončí, zavře a uvolní prostředky, které byly použity při aplikaci se aktivně zaznamenávání informací grafiky.|

## <a name="remarks"></a>Poznámky
 `VsgDbg` Třída představuje rozhraní, které můžete použít k ovládání funkcí diagnostiky grafiky prostřednictvím kódu programu. Některé funkce můžete použít i v případě, že nejsou aktivně zachytávání a zaznamenávání informací grafiky; Jedná se o `AddMessage` členské funkce a `ToggleHUD` členskou funkci. Členské funkce Příprava součást diagnostiky grafiky, spuštění nebo zastavení aktivní zachycení informací grafiky v aplikaci, nebo musí být volána, zatímco tato aplikace je aktivně zachytávání a zaznamenání grafických informací do souboru protokolu grafiky.