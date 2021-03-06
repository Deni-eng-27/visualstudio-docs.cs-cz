---
title: Správa VSPackage | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, autoloading
- VSPackages, delayed loading
- delay loading
- VSPackages, loading
ms.assetid: 386e0ce5-4107-4164-b0cd-1cf43eb5e7cf
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 60745d07679ae53b85d169473ed37ab314b67624
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80702656"
---
# <a name="manage-vspackages"></a>Správa balíčků VSPackage
Ve většině případů se nemusíte starat o správu VSPackage, protože šablony projektů a položek registrují a automaticky načítají balíček. V některých případech se ale může vyžadovat, abyste se o správě balíčku dozvěděli trochu víc.

## <a name="use-the-experimental-instance"></a>Použití experimentální instance
 Další informace o experimentální instanci naleznete v [experimentální instanci](../extensibility/the-experimental-instance.md).

## <a name="register-and-unregister-vspackages"></a>Registrace a zrušení registrace VSPackage
 Chcete-li zjistit, jak zaregistrovat a zrušit registraci VSPackage a dalších typů rozšíření, přečtěte si téma [registrace a zrušení registrace VSPackage](../extensibility/registering-and-unregistering-vspackages.md).

## <a name="load-a-vspackage"></a>Načtení VSPackage
 Sady VSPackage lze nastavit na automatické načtení, pokud je zapnut konkrétní CMDUICONTEXT identifikátor GUID. Další informace najdete v tématu [načtení VSPackage](../extensibility/loading-vspackages.md).

## <a name="use-asyncpackage-to-load-vspackages-in-the-background"></a>Použití AsyncPackage k načtení VSPackage na pozadí
 `AsyncPackage`Třída umožňuje načtení balíčku ve vlákně na pozadí pro lepší rychlost odezvy uživatelského rozhraní v aplikaci Visual Studio. Další informace naleznete v tématu [How to: use AsyncPackage (načíst sady VSPackage](../extensibility/how-to-use-asyncpackage-to-load-vspackages-in-the-background.md)) na pozadí.

## <a name="rule-based-ui-context-for-extensions"></a>Kontext uživatelského rozhraní založeného na pravidlech pro rozšíření
 Kontexty uživatelského rozhraní založeného na pravidlech umožňují autorům rozšíření definovat přesné podmínky, za kterých je kontext uživatelského rozhraní aktivovaný a které přidružené sady VSPackage jsou načtené. Další informace najdete v tématu [Postupy: použití kontextu uživatelského rozhraní založeného na pravidlech pro rozšíření sady Visual Studio](../extensibility/how-to-use-rule-based-ui-context-for-visual-studio-extensions.md).

## <a name="diagnose-extension-performance"></a>Diagnostika výkonu rozšíření
Rozšíření mohou ovlivnit výkon při spuštění a zatížení řešení. Přečtěte si, jak se vypočítá dopad rozšíření sady Visual Studio a jak se dá analyzovat místně, abyste otestovali, jestli se dá rozšíření zobrazit jako rozšíření s vlivem na výkon. Další informace naleznete v tématu [How to: diagnostice Performance Extension](how-to-diagnose-extension-performance.md).

## <a name="troubleshoot-vspackages"></a>Řešení potíží s VSPackage
 Přečtěte si postupy pro řešení potíží s VSPackage, které nenačítá nebo dochází k chybám: [řešení potíží s VSPackage](../extensibility/troubleshooting-vspackages.md)

## <a name="see-also"></a>Viz také
- [Balíčky VSPackage](../extensibility/internals/vspackages.md)
