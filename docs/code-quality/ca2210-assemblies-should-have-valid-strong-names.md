---
title: 'CA2210: Sestavení by měla mít platné silné názvy'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AssembliesShouldHaveValidStrongNames
- CA2210
helpviewer_keywords:
- AssembliesShouldHaveValidStrongNames
- CA2210
ms.assetid: 8ed33d1c-8ec6-4b47-a692-e22dc8693088
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 54f7d3a0efc2f6199c030c8dd488de3b5b158240
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/24/2019
ms.locfileid: "71231727"
---
# <a name="ca2210-assemblies-should-have-valid-strong-names"></a>CA2210: Sestavení by měla mít platné silné názvy

|||
|-|-|
|TypeName|AssembliesShouldHaveValidStrongNames|
|CheckId|CA2210|
|Kategorie|Microsoft.Design|
|Zásadní změna|Nenarušující|

## <a name="cause"></a>příčina

Sestavení není podepsáno silným názvem, nelze ověřit silný název nebo silný název nebude platný bez aktuálního nastavení registru počítače.

## <a name="rule-description"></a>Popis pravidla

Toto pravidlo načte a ověří silný název sestavení. K porušení dojde, pokud platí některá z následujících podmínek:

- Sestavení nemá silný název.

- Sestavení bylo po podepsání změněno.

- Sestavení je podepsané se zpožděním.

- Sestavení bylo nesprávně podepsáno nebo se nezdařilo podepisování.

- Sestavení vyžaduje k předání ověření nastavení registru. Například nástroj silného názvu (Sn. exe) se použil k přeskočení ověření pro sestavení.

Silný název chrání klienty před neúmyslným načtením narušeného sestavení. Sestavení bez silných názvů by kromě velmi omezených scénářů neměla být nasazována. Pokud sdílíte nebo šíříte sestavení, která nejsou správně podepsána, může být sestavení záměrně poškozeno, modul CLR je nemusí načíst nebo uživatelé mohou být nuceni vypnout na svém počítači ověřování. Sestavení bez silného názvu má z následujících nevýhod:

- Původce nelze ověřit.

- Modul CLR (Common Language Runtime) nemůže varovat uživatele, pokud došlo ke změně obsahu sestavení.

- Nelze jej načíst do globální mezipaměti sestavení (GAC).

Všimněte si, že pro načtení a analýzu sestavení se zpožděným podpisem je nutné zakázat ověření pro sestavení.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

### <a name="create-a-key-file"></a>Vytvořit soubor klíče

Použijte jeden z následujících postupů:

- Použijte [Nástroj Assembly Linker (Al. exe)](/dotnet/framework/tools/al-exe-assembly-linker).

- Pro `/keyfile` .NET Framework 2,0 použijte možnost kompilátoru "nebo `/keycontainer` " [/keyfile (zadejte klíč nebo dvojici klíčů pro podepsání sestavení)](/cpp/build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly) nebo [/keycontainer (zadejte kontejner klíčů pro podepsání sestavení)](/cpp/build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly) možnost linkeru v aplikaci C++).

- Pro .NET Framework v 1.0 nebo v 1.1 použijte buď <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=fullName> atribut nebo. <xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=fullName>

### <a name="sign-your-assembly-with-a-strong-name-in-visual-studio"></a>Podepsání sestavení silným názvem v aplikaci Visual Studio

1. V aplikaci Visual Studio otevřete své řešení.

2. V **Průzkumník řešení**klikněte pravým tlačítkem myši na projekt a pak klikněte na **Vlastnosti.**

3. Klikněte na kartu **podepisování** a zaškrtněte políčko **podepsat sestavení** .

4. V **Možnosti zvolit soubor klíče se silným názvem**vyberte **Nový**.

   Zobrazí se okno **vytvořit klíč se silným názvem** .

5. Do klíčového **názvu souboru**zadejte název klíče se silným názvem.

6. Zvolte, zda chcete klíč chránit heslem, a poté klikněte na tlačítko **OK**.

7. V **Průzkumník řešení**klikněte pravým tlačítkem myši na projekt a potom klikněte na položku **sestavit**.

### <a name="sign-your-assembly-with-a-strong-name-outside-visual-studio"></a>Podepsání sestavení silným názvem mimo Visual Studio

Použijte [Nástroj Strong Name (Sn. exe)](/dotnet/framework/tools/sn-exe-strong-name-tool).

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Potlačí upozornění z tohoto pravidla pouze v případě, že je sestavení použito v prostředí, ve kterém není manipulace s obsahem netýká se.

## <a name="see-also"></a>Viz také:

- <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=fullName>
- <xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=fullName>
- [Postupy: Podepsat sestavení silným názvem](/dotnet/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name)
- [Sn.exe (nástroj pro silný název)](/dotnet/framework/tools/sn-exe-strong-name-tool)