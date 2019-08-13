---
title: Stránka Sestavení, návrhář projektu (C#)
ms.date: 06/20/2017
ms.technology: vs-ide-compile
ms.topic: reference
f1_keywords:
- cs.ProjectPropertiesBuild
helpviewer_keywords:
- Build options [C#]
- Project Designer, Build page
ms.assetid: 77ff1bfc-d633-4634-ba29-9afdb6d7e362
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 146d98701f144aacf0ff073c3099b2239ebd1872
ms.sourcegitcommit: 85d66dc9fea3fa49018263064876b15aeb6f9584
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/24/2019
ms.locfileid: "68461458"
---
# <a name="build-page-project-designer-c"></a>Stránka Sestavení, návrhář projektu (C#)

Pomocí stránky **sestavení** **Návrháře projektu** Určete vlastnosti konfigurace sestavení projektu. Tato stránka se vztahuje [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] pouze na projekty.

Pro přístup na stránku **sestavení** vyberte uzel projektu (nikoli uzel **řešení** ) v **Průzkumník řešení**. Pak v nabídce zvolte možnost **zobrazení**, **stránky vlastností** . Když se zobrazí Návrhář projektu, klikněte na kartu **sestavení** .

[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]

## <a name="configuration-and-platform"></a>Konfigurace a platforma

Následující možnosti umožňují vybrat konfiguraci a platformu pro zobrazení nebo úpravu.

> [!NOTE]
> V případě zjednodušených konfigurací sestavení Určuje projektový systém, zda má být vytvořena verze ladění nebo vydání. Proto tyto možnosti nejsou zobrazeny. Další informace najdete v tématu [jak: Nastavte konfiguraci](../../debugger/how-to-set-debug-and-release-configurations.md)ladění a vydání.

**Konfigurace**

Určuje, která nastavení konfigurace se mají zobrazit nebo upravit. Nastavení může být **aktivní (ladění)** (Toto je výchozí nastavení), **ladění**, **vydání**nebo **všechny konfigurace**.

**Platformy**

Určuje, která nastavení platformy se mají zobrazit nebo upravit. Výchozí nastavení je **aktivní (libovolný procesor)** . Aktivní platformu můžete změnit pomocí **Configuration Manager**. Další informace najdete v tématu [jak: Vytvářejte a upravujte konfigurace](../../ide/how-to-create-and-edit-configurations.md).

## <a name="general"></a>Obecné

Následující možnosti umožňují nakonfigurovat několik C# nastavení kompilátoru.

**Symboly podmíněné kompilace**

Určuje symboly, na kterých se má provést Podmíněná kompilace. Symboly oddělujte středníkem (";"). Další informace naleznete v tématu [/define (C# možnosti kompilátoru)](/dotnet/csharp/language-reference/compiler-options/define-compiler-option).

**Definovat konstantu DEBUG**

Definuje ladění jako symbol ve všech souborech zdrojového kódu ve vaší aplikaci. Výběr této možnosti je stejný jako při `/define:DEBUG` použití možnosti příkazového řádku.

**Definovat konstantu TRACE**

Definuje TRACE jako symbol ve všech souborech zdrojového kódu ve vaší aplikaci. Výběr této možnosti je stejný jako při `/define:TRACE` použití možnosti příkazového řádku.

**Cíl platformy**

Určuje procesor, na který má výstupní soubor cílit. Zvolte **x86** pro libovolný 32 procesor kompatibilní s procesorem Intel, zvolte **x64** pro libovolný 64 procesor kompatibilního s procesorem Intel, zvolte **ARM** pro PROCESORy ARM nebo zvolte **Libovolný procesor** , abyste určili, že je přípustný libovolný procesor. **Libovolný procesor** je výchozí hodnota pro projekty, protože umožňuje aplikaci běžet na nejširší škále hardwaru.

Další informace naleznete v tématu [/Platform (C# možnosti kompilátoru)](/dotnet/csharp/language-reference/compiler-options/platform-compiler-option).

**Preferovat 32 – bit**

Pokud je zaškrtnuto políčko **Prefer32-bit** , aplikace běží jako 32ová aplikace v 32 i v 64 bitových verzích systému Windows. Pokud políčko není zaškrtnuto, aplikace bude spuštěna jako 32ská aplikace v 32 verzích systému Windows a jako aplikace 64 64 v systému Windows v 16bitovém verzích.

Pokud aplikaci spouštíte jako 64ovou aplikaci, je velikost ukazatele Dvojitá a problémy s kompatibilitou můžou nastat i u jiných knihoven, které jsou výhradně 32 bitové. Je vhodné spustit 64ovou aplikaci pouze v případě, že potřebuje více než 4 GB paměti nebo 64 instrukcí, což přináší výrazné zlepšení výkonu.

Toto zaškrtávací políčko je k dispozici pouze v případě, že jsou splněné všechny následující podmínky:

- Na **stránce sestavení**je seznam **cílů platformy** nastavený na **Libovolný procesor**.

- Na **stránce aplikace**se v seznamu **Typ výstupu** určuje, že projekt je aplikace.

- Na **stránce aplikace**se v seznamu **cílový rámec** určuje .NET Framework 4,5.

**Povolení nezabezpečeného kódu**

Umožňuje kompilaci kódu, který [nebezpečný](/dotnet/csharp/language-reference/keywords/unsafe) používá klíčové slovo Další informace naleznete v tématu [/unsafe (C# možnosti kompilátoru)](/dotnet/csharp/language-reference/compiler-options/unsafe-compiler-option).

**Optimalizovat kód**

Povolte nebo zakažte optimalizace prováděné kompilátorem, abyste mohli zmenšit, rychleji a zefektivnit výstupní soubor. Další informace naleznete v tématu [/optimize (C# možnosti kompilátoru)](/dotnet/csharp/language-reference/compiler-options/optimize-compiler-option).

## <a name="errors-and-warnings"></a>Chyby a upozornění

Následující nastavení jsou použita ke konfiguraci chyb a možností upozornění pro proces sestavení.

**Úroveň upozornění**

Určuje úroveň, která se má zobrazit pro upozornění kompilátoru. Další informace naleznete v tématu [/warn (C# možnosti kompilátoru)](/dotnet/csharp/language-reference/compiler-options/warn-compiler-option).

**Potlačit upozornění**

Blokuje schopnost kompilátoru generovat jedno nebo více upozornění. Více čísel upozornění oddělte čárkou nebo středníkem. Další informace naleznete v tématu [/nowarn (C# možnosti kompilátoru)](/dotnet/csharp/language-reference/compiler-options/nowarn-compiler-option).

## <a name="treat-warnings-as-errors"></a>Zpracovávat upozornění jako chyby

Následující nastavení slouží k určení, která upozornění jsou považována za chyby. Vyberte jednu z následujících možností, která určuje, za jakých podmínek se má v případě, že se při sestavení vyskytne upozornění, vrátit chybu. Další informace naleznete v tématu [/warnaserror (C# možnosti kompilátoru)](/dotnet/csharp/language-reference/compiler-options/warnaserror-compiler-option).

**Žádné**

Nezpracovává žádná upozornění jako chyby.

**Konkrétní upozornění**

Zpracovává zadaná upozornění jako chyby. Více čísel upozornění oddělte čárkou nebo středníkem.

**Vše**

Zpracovává všechna upozornění jako chyby.

## <a name="output"></a>Výstup

Následující nastavení se používají ke konfiguraci možností výstupu pro proces sestavení.

**Výstupní cesta**

Určuje umístění výstupních souborů pro tuto konfiguraci projektu. Do tohoto pole zadejte cestu k výstupu sestavení nebo klikněte na tlačítko **Procházet** a zadejte cestu. Cesta je relativní; Pokud zadáte absolutní cestu, bude uložena jako relativní. Výchozí cesta je bin\Debug nebo bin\Release\\.

V případě zjednodušených konfigurací sestavení Určuje projektový systém, zda má být vytvořena verze ladění nebo vydání. Příkaz **Build** z nabídky **ladění** (F5) vloží sestavení do umístění ladění bez ohledu na **výstupní cestu** , kterou zadáte. Příkaz **Build** v nabídce **sestavení** však vloží do umístění, které zadáte. Další informace najdete v tématu [Principy konfigurací sestavení](../../ide/understanding-build-configurations.md).

**Soubor dokumentace XML**

Určuje název souboru, do kterého se budou zpracovávat komentáře k dokumentaci. Další informace naleznete v tématu [/doc (C# možnosti kompilátoru)](/dotnet/csharp/language-reference/compiler-options/doc-compiler-option).

**Registrovat pro zprostředkovatele komunikace s objekty COM**

Označuje, že vaše spravovaná aplikace bude vystavovat objekt COM (obálka s možnou sadou COM), která umožňuje objektu COM pracovat s vaší spravovanou aplikací. Vlastnost **Typ výstupu** na [stránce aplikace](../../ide/reference/application-page-project-designer-visual-basic.md) **Návrháře projektu** pro tuto aplikaci je nutné nastavit na **knihovnu tříd** , aby byla k dispozici vlastnost **Register pro zprostředkovatele komunikace s objekty COM** . Pro ukázkovou třídu, kterou můžete zahrnout do [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] aplikace a zveřejnit jako objekt modelu COM, viz [příklad třídy com](/dotnet/csharp/programming-guide/interop/example-com-class).

**Generovat sestavení serializace**

Určuje, zda kompilátor použije XML Serializer Generator Tool (Sgen. exe) k vytvoření sestavení serializace XML. Sestavení serializace mohou zlepšit výkon <xref:System.Xml.Serialization.XmlSerializer> při spuštění v případě, že jste tuto třídu použili k serializaci typů ve vašem kódu. Ve výchozím nastavení je tato možnost nastavena na hodnotu **auto**, která určuje, že sestavení serializace budou generována pouze <xref:System.Xml.Serialization.XmlSerializer> v případě, že jste použili ke kódování typů v kódu do XML. **Off** určuje, že sestavení serializace nikdy nebyla vygenerována bez ohledu na to <xref:System.Xml.Serialization.XmlSerializer>, zda váš kód používá. **V** určuje, zda mají být sestavení serializace vždy vygenerována. Sestavení serializace jsou `TypeName`pojmenována. XmlSerializers. dll. Další informace najdete v tématu [XML Serializer Generator Tool (Sgen. exe)](/dotnet/framework/serialization/xml-serializer-generator-tool-sgen-exe).

**Pokročilé**

Kliknutím zobrazíte dialogové okno [Upřesnit nastavení sestaveníC#()](../../ide/reference/advanced-build-settings-dialog-box-csharp.md) .

## <a name="see-also"></a>Viz také:

- [Referenční dokumentace k vlastnostem projektu](../../ide/reference/project-properties-reference.md)
- [Možnosti kompilátoru jazyka C#](/dotnet/csharp/language-reference/compiler-options/index)