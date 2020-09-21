---
title: Nástroje pro lokalizaci
ms.date: 02/15/2019
ms.topic: reference
helpviewer_keywords:
- globalization [Visual Studio]
- Visual Basic code, international applications
- C#, international applications
- localization [Visual Studio]
- world-ready applications
- international applications [Visual Studio]
ms.assetid: 4d9815ae-3e80-4b4d-933d-f8309aee18d5
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: eebdccf44580442b87e3d31e33ddcd7052838306
ms.sourcegitcommit: 566144d59c376474c09bbb55164c01d70f4b621c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/19/2020
ms.locfileid: "90810898"
---
# <a name="develop-globalized-and-localized-apps"></a>Vývoj globálních a lokalizovaných aplikací

Visual Studio usnadňuje vývoj pro mezinárodní cílovou skupinu díky využití služeb integrovaných do [.NET](/dotnet/standard/globalization-localization/).

Například projektový systém pro model Windows Forms aplikace může generovat soubory prostředků pro záložní jazykovou verzi uživatelského rozhraní i pro každou další jazykovou verzi uživatelského rozhraní. Při sestavování projektu v aplikaci Visual Studio jsou soubory prostředků kompilovány z formátu XML sady Visual Studio (. resx) do mezilehlého binárního formátu (. Resources), které jsou poté vloženy do satelitních sestavení. Další informace naleznete v tématu [soubory prostředků v aplikaci Visual Studio](/dotnet/framework/resources/creating-resource-files-for-desktop-apps#VSResFiles) a [Vytváření satelitních sestavení pro aplikace klasické pracovní plochy](/dotnet/framework/resources/creating-satellite-assemblies-for-desktop-apps).

## <a name="bidirectional-languages"></a>Obousměrné jazyky

Pomocí sady Visual Studio můžete vytvářet aplikace, které správně zobrazují text v jazycích psaných zprava doleva, včetně arabštiny a hebrejštiny. U některých funkcí můžete jednoduše nastavit vlastnosti. V jiných případech je nutné implementovat funkce v kódu.

> [!NOTE]
> Aby bylo možné zadávat a zobrazovat obousměrné jazyky, musíte pracovat s verzí systému Windows, která je nakonfigurovaná s odpovídajícím jazykem. Může to být buď Anglická verze systému Windows s nainstalovanou příslušnou jazykovou sadou, nebo odpovídající lokalizovaná verze systému Windows.

### <a name="apps-that-support-bidirectional-languages"></a>Aplikace, které podporují obousměrné jazyky

- Aplikace pro Windows

   Můžete vytvářet plně obousměrné aplikace, které zahrnují podporu obousměrného textu, směr čtení zprava doleva a zrcadlení (převrácení rozložení oken, nabídek, dialogových oken atd.). S výjimkou zrcadlení jsou tyto funkce k dispozici ve výchozím nastavení nebo jako nastavení vlastností. Zrcadlení je v podstatě podporováno pro některé funkce, jako jsou například okna se zprávami. V jiných případech však musíte implementovat zrcadlení v kódu. Další informace najdete v tématu [Obousměrná podpora pro aplikace model Windows Forms](/dotnet/framework/winforms/advanced/bi-directional-support-for-windows-forms-applications).

- Webové aplikace

   Webové služby podporují posílání a přijímání textu v kódování UTF-8 a Unicode, takže jsou vhodné pro aplikace, které zahrnují obousměrné jazyky. Webové klientské aplikace spoléhají na své uživatelské rozhraní v prohlížečích, takže stupeň obousměrné podpory ve webové aplikaci závisí na tom, jak dobře podporuje prohlížeč uživatelů tyto obousměrné funkce. V aplikaci Visual Studio můžete vytvářet aplikace s podporou arabského nebo hebrejského textu, pořadí čtení zprava doleva, kódování souborů a nastavení místní kultury. Další informace najdete v tématu [Obousměrná podpora pro webové aplikace ASP.NET](/previous-versions/6eedwbtt(v=vs.140)).

> [!NOTE]
> Konzolové aplikace neobsahují podporu textu pro obousměrné jazyky. Jedná se o postup, jak systém Windows funguje s aplikacemi konzoly.

## <a name="see-also"></a>Viz také

- [Podpora obousměrných jazyků v aplikaci Visual Studio](use-bidirectional-languages.md)
- [Globalizace a lokalizace aplikací .NET](/dotnet/standard/globalization-localization/)
- [Prostředky v aplikacích .NET](/dotnet/framework/resources/)