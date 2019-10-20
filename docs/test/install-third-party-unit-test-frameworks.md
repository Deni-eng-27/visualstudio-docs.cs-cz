---
title: Instalace systémů testování částí od třetích stran
ms.date: 04/01/2019
ms.topic: conceptual
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
author: jillre
ms.openlocfilehash: fef59c757476b46936389ca48ca2bdaf32aec729
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72653249"
---
# <a name="install-unit-test-frameworks"></a>Nainstalovat rozhraní pro testování částí

Průzkumník testů sady Visual Studio může spouštět testy z libovolného rozhraní pro testování částí, které pro něj vyvinulo rozhraní adaptéru. Instalace rozhraní zkopíruje binární soubory a přidá šablony projektů sady Visual Studio pro jazyky, které podporuje. Při vytváření projektu se šablonou je rozhraní registrováno v Průzkumníku testů.

Řešení sady Visual Studio může obsahovat projekty testování částí, které používají různá rozhraní a cílí na různé jazyky.

[MSTest](getting-started-with-unit-testing.md) je testovací rozhraní, které poskytuje Visual Studio a ve výchozím nastavení je nainstalované.

## <a name="acquire-frameworks"></a>Získat rozhraní

Nainstalujte rozhraní pro testování částí od třetích stran pomocí **Správce balíčků NuGet**.

1. Klikněte pravým tlačítkem na projekt, který bude obsahovat testovací kód a vyberte možnost **Spravovat balíčky NuGet**.

2. Ve **Správci balíčků NuGet**vyhledejte testovací rozhraní, které chcete nainstalovat, a pak klikněte na **nainstalovat**.

   ![Správce balíčků NuGet v aplikaci Visual Studio](media/vs-2019/nuget-package-manager.png)

## <a name="update-to-the-latest-test-adapters"></a>Aktualizace na nejnovější adaptéry testů

Aktualizujte na nejnovější stabilní testovací adaptér a vyzkoušejte si lepší zjišťování a provádění testů. Další informace o aktualizacích adaptérů MSTest, NUnit a xUnit test Adapters najdete v [blogu sady Visual Studio](https://devblogs.microsoft.com/visualstudio/test-experience-improvements/).

### <a name="to-update-to-the-latest-stable-test-adapter-version"></a>Aktualizace na nejnovější verzi stabilního testovacího adaptéru

1. Otevřete Správce balíčků NuGet pro vaše řešení, a to tak, že přejdete na **nástroje**  > **správce balíčků NuGet**  > **Spravovat balíčky NuGet pro řešení**.

2. Klikněte na kartu **aktualizace** a vyhledejte adaptéry MSTest, NUnit nebo xUnit test Adapters, které jsou nainstalovány.

3. Vyberte jednotlivé adaptéry testů a v rozevírací nabídce vyberte nejnovější stabilní verzi.

4. Klikněte na tlačítko **instalovat** .

   ![Upgrade testovacího adaptéru](media/install-adapter-upgrade.png)

## <a name="see-also"></a>Viz také:

- [Testování částí kódu](../test/unit-test-your-code.md)
