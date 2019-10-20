---
title: Zabezpečení
ms.date: 06/01/2018
ms.topic: conceptual
helpviewer_keywords:
- security [Visual Studio], applications
- application design, securability
ms.assetid: 7d32c4cf-8bec-4307-a2a8-42f0ceddf3eb
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 605a8301e0a016699822e32e24f82592862bb765
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72621615"
---
# <a name="secure-applications"></a>Zabezpečené aplikace

Zabezpečení byste měli věnovat pozornost ve všech aspektech vývoje aplikace od návrhu až po nasazení. Začněte tím, že spustíte aplikaci Visual Studio co nejdříve. Viz [uživatelská oprávnění](../ide/user-permissions-and-visual-studio.md).

Abyste mohli efektivně vyvíjet bezpečné aplikace, měli byste znát základní principy konceptů zabezpečení a funkce zabezpečení platforem, pro které vyvíjíte. Také je třeba porozumět bezpečným technikám kódování.

## <a name="code-for-security"></a>Kód pro zabezpečení

Většina chyb kódování, které vedou k ohrožení zabezpečení, je způsobená tím, že vývojáři při práci s uživatelským vstupem vytvářejí nesprávné předpoklady nebo protože plně nerozumí platformě, pro kterou vyvíjí.

- [Pokyny pro bezpečné kódování](/dotnet/standard/security/secure-coding-guidelines) popisuje různé způsoby, jak může být kód .NET navržený pro práci se systémem zabezpečení.
- [Osvědčené postupy C++ zabezpečení](/cpp/top/security-best-practices-for-cpp) nástroje obsahují informace o nástrojích zabezpečení a C++ postupech pro vývojáře.

## <a name="build-for-security"></a>Sestavit pro zabezpečení

Zabezpečení je také důležitým aspektem procesu sestavení. Několik dalších kroků může zlepšit zabezpečení nasazené aplikace a pomáhat zabránit neoprávněným zpětným inženýrům, falšování a jiným útokům:

- [Dotfuscator](dotfuscator/index.md) je zdarma a pomáhá chránit sestavení .NET před zpětným technickým a neoprávněným použitím, jako je například neoprávněné ladění.
- [Podpis se silným názvem](managing-assembly-and-manifest-signing.md) se dá použít k jednoznačné identifikaci softwarových komponent a k zabránění falšování názvů.

## <a name="see-also"></a>Viz také:

- [Zabezpečení v .NET](/dotnet/standard/security/index)
- [Zabezpečení Azure](/azure/security/)
- [Průvodce zabezpečením pro Windows 10 Mobile](/windows/security/threat-protection/windows-10-mobile-security-guide)
- [Funkce zabezpečení platformy Apache Cordova](/visualstudio/cross-platform/tools-for-cordova/security/best-practices?view=toolsforcordova-2017)
- [ASP.NET Core zabezpečení](/aspnet/core/security/?view=aspnetcore-2.1)
- [model Windows Forms zabezpečení](/dotnet/framework/winforms/windows-forms-security)