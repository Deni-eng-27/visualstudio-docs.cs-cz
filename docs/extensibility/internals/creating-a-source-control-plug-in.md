---
title: Vytvoření modulu Plug-in správy zdrojového kódu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- plug-ins, source control
- source control plug-ins
- source control [Visual Studio SDK], plug-ins
ms.assetid: c7e69fa4-150e-469a-a6fc-fa1260bdbb07
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b8489e991a54df5b905289a64fccb0df65c3cec8
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66341929"
---
# <a name="create-a-source-control-plug-in"></a>Vytvoření modulu plug-in správy zdrojového kódu
Visual Studio SDK poskytuje prostředky, které vám umožní přidat možnost zdrojového ovládacího prvku [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE). To vám umožní používat jakékoli knihovnu DLL modulu plug-in, který splňuje pomocí rozhraní API modulu Plug-in zdroje ovládacího prvku uvedených v této dokumentaci.

## <a name="in-this-section"></a>V tomto oddílu
- [Začínáme](../../extensibility/internals/getting-started-with-source-control-plug-ins.md)

 Popisuje postup instalace modulu plug-in správy zdrojového kódu a zvýrazní aktuálně k dispozici verze rozhraní API modulu Plug-in zdroje ovládacího prvku.

- [Architektura](../../extensibility/internals/source-control-plug-in-architecture.md)

 Pomocí diagramu architektury popisují integrace správy zdrojového kódu pomocí modulu plug-in [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrovaného vývojového prostředí.

- [Příručka pro testovací](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)

 Poskytuje pokyny o tom, jak otestovat instalaci a používání modulu plug-in správy zdrojového kódu.

## <a name="related-sections"></a>Související oddíly
- [Vytvoření balíčku VSPackage správy zdrojového kódu](../../extensibility/internals/creating-a-source-control-vspackage.md)

 Popisuje, jak vytvořit ovládací prvek zdroje balíčku VSPackage, která nejen poskytuje funkce správy zdrojového kódu, ale nahrazuje [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] zdrojového ovládacího prvku uživatelského rozhraní.

- [Ovládací prvek moduly plug-in zdrojového kódu](../../extensibility/source-control-plug-ins.md)

 Obsahuje úplný seznam všech prvků v rozhraní API modulu Plug-in zdroje ovládacího prvku.

- [Správy zdrojového kódu](../../extensibility/internals/source-control.md)

 Tento článek popisuje možnosti pro implementaci správy zdrojového kódu jako integrovaná funkce [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].
