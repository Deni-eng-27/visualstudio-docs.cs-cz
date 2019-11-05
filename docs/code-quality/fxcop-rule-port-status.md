---
title: Stav portu pravidla FxCop
ms.date: 05/21/2019
ms.topic: reference
helpviewer_keywords:
- fxcop rules
- fxcop analyzers, ported rules
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: a33286ffb678bf37cf684bb603d81ec8091e7405
ms.sourcegitcommit: 97623fd6190c43fed0d2ee7af92b01c375282622
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/04/2019
ms.locfileid: "73568816"
---
# <a name="fxcop-rule-port-status"></a>Stav portu pravidla FxCop

Pokud jste dříve používali analýzu statického kódu v aplikaci Visual Studio, můžete si všimnout, že tato pravidla jsou k dispozici v aktuální implementaci jako [analyzátory FxCop](install-fxcop-analyzers.md). Tato stránka obsahuje seznam nakonfigurovaných pravidel a také těch, které nebyly přepsány a zda existují plány, které je mají přenést.

## <a name="ported-rules"></a>Přenesená pravidla

[Stránka pro automaticky generovanou dokumentaci](https://github.com/dotnet/roslyn-analyzers/blob/master/src/Microsoft.CodeAnalysis.FxCopAnalyzers/Microsoft.CodeAnalysis.FxCopAnalyzers.md) v úložišti Roslyn-Analyzer obsahuje nejaktuálnější seznam pravidel, která byla předaná do analyzátorů FxCop. Tato stránka obsahuje také další informace, například zda je pravidlo povoleno ve výchozím nastavení a zda má přidruženou *opravu kódu*. ([Opravy kódu](../ide/quick-actions.md) jsou dostupné opravy jedním kliknutím v nabídce ikony žárovky v aplikaci Visual Studio.)

Od data na této stránce seznam pravidel FxCop, která byla předaná do [analyzátorů FxCop](install-fxcop-analyzers.md) , zahrnují:

ID pravidla | Název
--------|---------
[CA1000](ca1000-do-not-declare-static-members-on-generic-types.md) | Nedeklarujte statické členy v obecných typech
[CA1001](ca1001-types-that-own-disposable-fields-should-be-disposable.md) | Typy, které vlastní uvolnitelné pole, by měly být uvolnitelné
[CA1003](ca1003-use-generic-event-handler-instances.md) | Použijte instance obecných obslužných rutin události
[CA1008](ca1008-enums-should-have-zero-value.md) | Výčty by měly mít nulovou hodnotu
[CA1010](ca1010-collections-should-implement-generic-interface.md) | Kolekce musí implementovat obecné rozhraní
[CA1012](ca1012-abstract-types-should-not-have-constructors.md) | Abstraktní typy by neměly mít konstruktory
[CA1014](ca1014-mark-assemblies-with-clscompliantattribute.md) | Označte sestavení pomocí CLSCompliant
[CA1016](ca1016-mark-assemblies-with-assemblyversionattribute.md) | Označit sestavení verzí sestavení
[CA1017](ca1017-mark-assemblies-with-comvisibleattribute.md) | Označte sestavení pomocí ComVisible
[CA1018](ca1018-mark-attributes-with-attributeusageattribute.md) | Označte atributy pomocí AttributeUsageAttribute
[CA1019](ca1019-define-accessors-for-attribute-arguments.md) | Definujte přístupové objekty pro argumenty atributů
[CA1024](ca1024-use-properties-where-appropriate.md) | Použijte vlastnosti, kde je to vhodné
[CA1027](ca1027-mark-enums-with-flagsattribute.md) | Označte výčty pomocí FlagsAttribute
[CA1028](ca1028-enum-storage-should-be-int32.md) | Úložiště výčtu by měl být Int32
[CA1030](ca1030-use-events-where-appropriate.md) | Použijte události, kde je to vhodné
[CA1031](ca1031-do-not-catch-general-exception-types.md) | Nezachycujte výjimky obecného typu
[CA1032](ca1032-implement-standard-exception-constructors.md) | Implementujte standardní konstruktory výjimky
[CA1033](ca1033-interface-methods-should-be-callable-by-child-types.md) | Metody rozhraní by měly být volatelné podřízenými typy
[CA1034](ca1034-nested-types-should-not-be-visible.md) | Vnořené typy by neměly být viditelné
[CA1036](ca1036-override-methods-on-comparable-types.md) | Přepište metody u srovnatelných typů
[CA1040](ca1040-avoid-empty-interfaces.md) | Vyhněte se prázdným rozhraním
[CA1041](ca1041-provide-obsoleteattribute-message.md) | Poskytněte zprávu ObsoleteAttribute
[CA1043](ca1043-use-integral-or-string-argument-for-indexers.md) | Použít celočíselný nebo řetězcový argument pro indexery
[CA1044](ca1044-properties-should-not-be-write-only.md) | Vlastnosti by neměly být pouze pro zápis
[CA1050](ca1050-declare-types-in-namespaces.md) | Deklarujte typy v oborech názvů
[CA1051](ca1051-do-not-declare-visible-instance-fields.md) | Nedeklarujte viditelná pole instance
[CA1052](ca1052-static-holder-types-should-be-sealed.md) | Statické typy držitelů by měly být statické nebo NotInheritable.
[CA1053](ca1053-static-holder-types-should-not-have-constructors.md) | Typy statických držitelů by neměly mít konstruktory (CA1053 je součást [CA1052](ca1052-static-holder-types-should-be-sealed.md) pro analyzátory FxCop).
[CA1054](ca1054-uri-parameters-should-not-be-strings.md) | Parametry identifikátoru URI by neměly být řetězce
[CA1055](ca1055-uri-return-values-should-not-be-strings.md) | Návratové hodnoty identifikátoru URI by neměly být řetězce
[CA1056](ca1056-uri-properties-should-not-be-strings.md) | Vlastnosti identifikátoru URI by neměly být řetězce
[CA1058](ca1058-types-should-not-extend-certain-base-types.md) | Typy by neměly rozšiřovat určité základní typy
[CA1060](ca1060-move-p-invokes-to-nativemethods-class.md) | Přesunout PInvoke do nativní třídy metod
[CA1061](ca1061-do-not-hide-base-class-methods.md) | Neskrývejte metody základní třídy
[CA1062](ca1062-validate-arguments-of-public-methods.md) | Ověřte argumenty veřejných metod
[CA1063](ca1063-implement-idisposable-correctly.md) | Implementovat správně IDisposable
[CA1064](ca1064-exceptions-should-be-public.md) | Výjimky by měly být veřejné
[CA1065](ca1065-do-not-raise-exceptions-in-unexpected-locations.md) | Nevyvolávejte výjimky v neočekávaných umístěních
CA1066 | Typ {0} by měl implementovat IEquatable\<T >, protože přepisuje rovnost.
CA1067 | Při implementaci IEquatable\<T přepsat Object. Equals (Object) >
[CA1068](ca1068.md) | Parametry CancellationToken musí být poslední.
CA1200 | Nepoužívejte značky cref s předponou
[CA1303](ca1303-do-not-pass-literals-as-localized-parameters.md) | Nepředávejte literály jako lokalizované parametry
[CA1304](ca1304-specify-cultureinfo.md) | Určete CultureInfo
[CA1305](ca1305-specify-iformatprovider.md) | Určete IFormatProvider
[CA1307](ca1307-specify-stringcomparison.md) | Určete StringComparison
[CA1308](ca1308-normalize-strings-to-uppercase.md) | Normalizujte řetězce na velká písmena
[CA1309](ca1309-use-ordinal-stringcomparison.md) | Použít ordinální porovnávání řetězců
[CA1401](ca1401-p-invokes-should-not-be-visible.md) | Volání nespravovaných kódů by neměla být viditelná
[CA1501](ca1501-avoid-excessive-inheritance.md) | Vyhněte se nadměrné dědičnosti
[CA1502](ca1502-avoid-excessive-complexity.md) | Vyhněte se nadměrné složitosti
[CA1505](ca1505-avoid-unmaintainable-code.md) | Vyhněte se neudržovatelnému kódu
[CA1506](ca1506-avoid-excessive-class-coupling.md) | Vyhněte se nadměrnému párování tříd
[CA1507](ca1507.md) | Použití nameof k vyjádření názvů symbolů
CA1508 | Vyhněte se neaktivnímu podmíněnému kódu
CA1509 | Neplatný záznam v souboru specifikace pravidla metrik kódu
[CA1707](ca1707-identifiers-should-not-contain-underscores.md) | Identifikátory by neměly obsahovat podtržítka
[CA1708](ca1708-identifiers-should-differ-by-more-than-case.md) | Identifikátory by se měly lišit více než použitím malých a velkých písmen
[CA1710](ca1710-identifiers-should-have-correct-suffix.md) | Identifikátory by měly mít správnou příponu
[CA1711](ca1711-identifiers-should-not-have-incorrect-suffix.md) | Identifikátory by neměly mít nesprávnou příponu
[CA1712](ca1712-do-not-prefix-enum-values-with-type-name.md) | Nezačínejte hodnoty výčtu názvem typu
[CA1714](ca1714-flags-enums-should-have-plural-names.md) | Výčty příznaků by neměly mít názvy v množném čísle
[CA1715](ca1715-identifiers-should-have-correct-prefix.md) | Identifikátory by měly mít správnou předponu
[CA1716](ca1716-identifiers-should-not-match-keywords.md) | Identifikátory by se neměly shodovat s klíčovými slovy
[CA1717](ca1717-only-flagsattribute-enums-should-have-plural-names.md) | Pouze výčty FlagsAttribute by měly mít názvy v množném čísle
[CA1720](ca1720-identifiers-should-not-contain-type-names.md) | Identifikátor obsahuje název typu.
[CA1721](ca1721-property-names-should-not-match-get-methods.md) | Názvy vlastností by se neměly shodovat s metodami Get
[CA1724](ca1724-type-names-should-not-match-namespaces.md) | Názvy typů by neměly odpovídat oborům názvů
[CA1725](ca1725-parameter-names-should-match-base-declaration.md) | Názvy parametrů by měly odpovídat základní deklaraci
[CA1801](ca1801.md) | Zkontrolujte nepoužité parametry
[CA1802](ca1802.md) | Použijte literály, kde je to vhodné
[CA1806](ca1806.md) | Neignorujte výsledky metody
[CA1810](ca1810.md) | Inicializujte odkazový typ statického pole vloženě
[CA1812](ca1812.md) | Vyhněte se nevytvořeným instancím interních tříd
[CA1813](ca1813.md) | Vyhněte se nezapečetěným atributům
[CA1814](ca1814.md) | Upřednostněte vícenásobná pole před multidimenzionálními
[CA1815](ca1815.md) | Přepište rovnosti a operátory rovnosti u typů hodnot
[CA1816](ca1816.md) | Metody Dispose by měly volat SuppressFinalize
[CA1819](ca1819.md) | Vlastnosti by neměly vracet pole
[CA1820](ca1820.md) | Testujte prázdné řetězce pomocí délky řetězce
[CA1821](ca1821.md) | Odebrat prázdné finalizační metody
[CA1822](ca1822.md) | Označte členy jako statické
[CA1823](ca1823.md) | Vyhněte se nepoužitým privátním polím
[CA1824](ca1824.md) | Označte sestavení pomocí NeutralResourcesLanguageAttribute
CA1825 | Vyhněte se přidělení pole s nulovou délkou.
CA1826 | Nepoužívejte vyčíslitelné metody pro indexované kolekce. Místo toho použijte kolekci přímo
[CA2000](ca2000.md) | Uvolňujte objekty před ztrátou oboru
[CA2002](ca2002.md) | Nepoužívejte zámky u objektů se slabou identitou
[CA2007](ca2007.md) | Zvažte možnost zavolat ConfigureAwait na očekávaný úkol.
CA2008 | Nevytvářejte úlohy bez předávání TaskScheduler
CA2009 | Nevolejte ToImmutableCollection na hodnotu neměnnécollection
CA2010 | Vždycky spotřebovat hodnotu vrácenou metodami označenými pomocí třídu PreserveSigAttribute nelze
[CA2100](ca2100.md) | Zkontrolujte chyby zabezpečení u dotazů SQL
[CA2101](ca2101.md) | Určete zařazování pro argumenty řetězce volání nespravovaného kódu
[CA2119](ca2119.md) | Zapečeťte metody, které vyhovují privátním rozhraním
[CA2153](ca2153.md) | Nezachytit poškozené výjimky stavu
[CA2200](ca2200.md) | Znovu vyvolejte pro zachování podrobností zásobníku.
[CA2201](ca2201.md) | Nevyvolávejte vyhrazené typy výjimek
[CA2207](ca2207.md) | Inicializujte statická pole s typem hodnoty vloženě
[CA2208](ca2208.md) | Vytvořte správně instance výjimky argumentu
[CA2211](ca2211.md) | Nekonstantní pole by neměla být viditelná
[CA2213](ca2213.md) | Uvolnitelná pole by měla být uvolněna
[CA2214](ca2214.md) | Nevolejte přepisovatelné metody v konstruktorech
[CA2216](ca2216.md) | Uvolnitelné typy by měly deklarovat finalizační metodu
[CA2217](ca2217.md) | Neoznačujte výčty pomocí FlagsAttribute
[CA2218](ca2218.md) | Přepište GetHashCode při přepsání Equals
[CA2219](ca2219.md) | Nevyvolávání výjimek v klauzulích finally
[CA2224](ca2224.md) | Přepište Equals při přetížení operátoru Equals
[CA2225](ca2225.md) | Přetížení operátoru mají pojmenované alternativy
[CA2226](ca2226.md) | Operátory by měly mít symetrická přetížení
[CA2227](ca2227.md) | Vlastnosti kolekce by měly být pouze pro čtení
[CA2229](ca2229.md) | Implementujte serializační konstruktory
[CA2231](ca2231.md) | Operátor přetížení se rovná překrytí typu hodnoty Equals.
[CA2234](ca2234.md) | Předání objektů identifikátoru URI systému místo řetězců
[CA2235](ca2235.md) | Označte všechna neserializovatelná pole
[CA2237](ca2237.md) | Označte typy ISerializable s serializovatelným
[CA2241](ca2241.md) | Zadejte správné argumenty pro metody formátování
[CA2242](ca2242.md) | Testujte správně NaN
[CA2243](ca2243.md) | Řetězcové literály atributů by se měly správně parsovat
CA2244 | Neduplikovat inicializace indexovaných elementů
[CA2300](ca2300.md) | Nepoužívat nezabezpečený deserializátor BinaryFormatter
[CA2301](ca2301.md) | Nevolat BinaryFormatter.Deserialize dříve, než se nastaví BinaryFormatter.Binder
[CA2302](ca2302.md) | Než zavoláte BinaryFormatter.Deserialize, ujistěte se, že je nastavený BinaryFormatter.Binder
[CA2305](ca2305.md) | Nepoužívat nezabezpečený deserializátor LosFormatter
[CA2310](ca2310.md) | Nepoužívat nezabezpečený deserializátor NetDataContractSerializer
[CA2311](ca2311.md) | Nedeserializovat dříve, než se nastaví NetDataContractSerializer.Binder
[CA2312](ca2312.md) | Před deserializací se ujistěte, že je nastavený NetDataContractSerializer.Binder
[CA2315](ca2315.md) | Nepoužívat nezabezpečený deserializátor ObjectStateFormatter
[CA2321](ca2321.md) | Nedeserializovat se třídou JavaScriptSerializer pomocí třídy SimpleTypeResolver
[CA2322](ca2322.md) | Před deserializaci se ujistěte se, že třída JavaScriptSerializer není inicializována pomocí třídy SimpleTypeResolver
[CA3001](ca3001.md) | Zkontrolujte ohrožení zabezpečení injektáží SQL v kódu
[CA3002](ca3002.md) | Zkontrolujte ohrožení zabezpečení proti XSS v kódu
[CA3003](ca3003.md) | Zkontrolujte ohrožení zabezpečení injektáží cesty k souboru v kódu
[CA3004](ca3004.md) | Zkontrolujte ohrožení zabezpečení zpřístupněním informací v kódu
[CA3005](ca3005.md) | Zkontrolujte ohrožení zabezpečení injektáží protokolu LDAP v kódu
[CA3006](ca3006.md) | Zkontrolujte ohrožení zabezpečení injektáží příkazu procesu v kódu
[CA3007](ca3007.md) | Zkontrolujte ohrožení zabezpečení otevřeným přesměrováním v kódu
[CA3008](ca3008.md) | Zkontrolujte ohrožení zabezpečení injektáží XPath v kódu
[CA3009](ca3009.md) | Zkontrolujte ohrožení zabezpečení injektáží XML v kódu
[CA3010](ca3010.md) | Zkontrolujte ohrožení zabezpečení injektáží XAML v kódu
[CA3011](ca3011.md) | Zkontrolujte ohrožení zabezpečení injektáží knihovny DLL v kódu
[CA3012](ca3012.md) | Zkontrolujte ohrožení zabezpečení injektáží regulárního výrazu v kódu
CA3061 | Nepřidávat schéma podle adresy URL
[CA3075](ca3075.md) | Nezabezpečené zpracování DTD v XML
[CA3076](ca3076.md) | Nezabezpečené zpracování skriptu XSLT
[CA3077](ca3077.md) | Nezabezpečené zpracování v návrzích rozhraní API, XmlDocument a XmlTextReader
[CA3147](ca3147.md) | Označit obslužné rutiny operací s tokenem ověření antipadělání
[CA5350](ca5350.md) | Nepoužívejte slabé kryptografické algoritmy
[CA5351](ca5351.md) | Nepoužívejte nefunkční kryptografické algoritmy.
CA5358 | Nepoužívat nezabezpečené šifrovací režimy
CA5359 | Nezakázat ověřování certifikátu
CA5360 | Nevolat nebezpečné metody v deserializaci
CA5361 | Nepovolujte používání SChannel silného šifrování.
CA5362 | Neodkazovat na sebe jako na serializovatelných třídách
CA5363 | Nezakázat ověřování žádostí
CA5364 | Nepoužívat zastaralé protokoly zabezpečení
CA5365 | Nezakázat kontrolu hlaviček protokolu HTTP
CA5366 | Použití XmlReader pro čtení XML pro datovou sadu
CA5367 | Neserializovat typy s poli ukazatelů
CA5368 | Nastavit ViewStateUserKey pro třídy odvozené ze stránky
CA5369 | Použít XmlReader pro deserializaci
CA5370 | Použití XmlReader k ověření čtecího zařízení
CA5371 | Použít XmlReader pro čtení schématu
CA5372 | Použití XmlReader pro XPathDocument
CA5373 | Nepoužívat zastaralou funkci odvození klíče
CA5374 | Nepoužívat XslTransform
CA5375 | Nepoužívat sdílený přístupový podpis účtu
CA5376 | Použití SharedAccessProtocol HttpsOnly
CA5377 | Použít zásady přístupu na úrovni kontejneru
CA5378 | Nezakazujte ServicePointManagerSecurityProtocols
CA5379 | Nepoužívejte slabý algoritmus funkce odvození klíče.
CA9999 | Neshoda verze analyzátoru

## <a name="unported-rules"></a>Nepřenosná pravidla

Sada pravidel, která se nerozšířila na [analyzátory FxCop](install-fxcop-analyzers.md) , se skládá z pravidel, která ještě nejsou, ale pořád se [můžou přenést](#rules-that-may-be-ported), a těch, které jsou zastaralé a [nebudou se přepravovat](#deprecated-rules).

### <a name="rules-that-may-be-ported"></a>Pravidla, která je možné přenést

Následující starší pravidla analýzy FxCop ještě nebyla implementována jako analyzátory, ale přesto může být. Důvodem může být blokující technický důvod nebo jednoduché pravidlo s nižší prioritou. Další informace o stavu přenosu každého pravidla získáte kliknutím na odkaz ve sloupci **problém sledování** .

ID pravidla | Problém sledování
--- | ---
[CA1002](ca1002-do-not-expose-generic-lists.md) | [https://github.com/dotnet/roslyn-analyzers/issues/369](https://github.com/dotnet/roslyn-analyzers/issues/369)
[CA1004](ca1004-generic-methods-should-provide-type-parameter.md) | [https://github.com/dotnet/roslyn-analyzers/issues/370](https://github.com/dotnet/roslyn-analyzers/issues/370)
[CA1005](ca1005-avoid-excessive-parameters-on-generic-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/371](https://github.com/dotnet/roslyn-analyzers/issues/371)
[CA1006](ca1006-do-not-nest-generic-types-in-member-signatures.md) | [https://github.com/dotnet/roslyn-analyzers/issues/372](https://github.com/dotnet/roslyn-analyzers/issues/372)
[CA1007](ca1007-use-generics-where-appropriate.md) | [https://github.com/dotnet/roslyn-analyzers/issues/373](https://github.com/dotnet/roslyn-analyzers/issues/373)
[CA1011](ca1011-consider-passing-base-types-as-parameters.md) | [https://github.com/dotnet/roslyn-analyzers/issues/375](https://github.com/dotnet/roslyn-analyzers/issues/375)
[CA1021](ca1021-avoid-out-parameters.md) | [https://github.com/dotnet/roslyn-analyzers/issues/377](https://github.com/dotnet/roslyn-analyzers/issues/377)
[CA1023](ca1023-indexers-should-not-be-multidimensional.md) | [https://github.com/dotnet/roslyn-analyzers/issues/378](https://github.com/dotnet/roslyn-analyzers/issues/378)
[CA1045](ca1045-do-not-pass-types-by-reference.md) | [https://github.com/dotnet/roslyn-analyzers/issues/391](https://github.com/dotnet/roslyn-analyzers/issues/391)
[CA1046](ca1046-do-not-overload-operator-equals-on-reference-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/392](https://github.com/dotnet/roslyn-analyzers/issues/392)
[CA1047](ca1047-do-not-declare-protected-members-in-sealed-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/393](https://github.com/dotnet/roslyn-analyzers/issues/393)
[CA1048](ca1048-do-not-declare-virtual-members-in-sealed-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/394](https://github.com/dotnet/roslyn-analyzers/issues/394)
[CA1049](ca1049-types-that-own-native-resources-should-be-disposable.md) | [https://github.com/dotnet/roslyn-analyzers/issues/395](https://github.com/dotnet/roslyn-analyzers/issues/395)
[CA1057](ca1057-string-uri-overloads-call-system-uri-overloads.md) | [https://github.com/dotnet/roslyn-analyzers/issues/401](https://github.com/dotnet/roslyn-analyzers/issues/401)
[CA1300](ca1300-specify-messageboxoptions.md) | [https://github.com/dotnet/roslyn-analyzers/issues/408](https://github.com/dotnet/roslyn-analyzers/issues/408)
[CA1301](ca1301-avoid-duplicate-accelerators.md) | [https://github.com/dotnet/roslyn-analyzers/issues/409](https://github.com/dotnet/roslyn-analyzers/issues/409)
[CA1306](ca1306-set-locale-for-data-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/414](https://github.com/dotnet/roslyn-analyzers/issues/414)
[CA1402](ca1402-avoid-overloads-in-com-visible-interfaces.md) | [https://github.com/dotnet/roslyn-analyzers/issues/418](https://github.com/dotnet/roslyn-analyzers/issues/418)
[CA1403](ca1403-auto-layout-types-should-not-be-com-visible.md) | [https://github.com/dotnet/roslyn-analyzers/issues/419](https://github.com/dotnet/roslyn-analyzers/issues/419)
[CA1404](ca1404-call-getlasterror-immediately-after-p-invoke.md) | [https://github.com/dotnet/roslyn-analyzers/issues/420](https://github.com/dotnet/roslyn-analyzers/issues/420)
[CA1405](ca1405-com-visible-type-base-types-should-be-com-visible.md) | [https://github.com/dotnet/roslyn-analyzers/issues/421](https://github.com/dotnet/roslyn-analyzers/issues/421)
[CA1407](ca1407-avoid-static-members-in-com-visible-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/423](https://github.com/dotnet/roslyn-analyzers/issues/423)
[CA1408](ca1408-do-not-use-autodual-classinterfacetype.md) | [https://github.com/dotnet/roslyn-analyzers/issues/424](https://github.com/dotnet/roslyn-analyzers/issues/424)
[CA1409](ca1409-com-visible-types-should-be-creatable.md) | [https://github.com/dotnet/roslyn-analyzers/issues/425](https://github.com/dotnet/roslyn-analyzers/issues/425)
[CA1410](ca1410-com-registration-methods-should-be-matched.md) | [https://github.com/dotnet/roslyn-analyzers/issues/426](https://github.com/dotnet/roslyn-analyzers/issues/426)
[CA1411](ca1411-com-registration-methods-should-not-be-visible.md) | [https://github.com/dotnet/roslyn-analyzers/issues/427](https://github.com/dotnet/roslyn-analyzers/issues/427)
[CA1412](ca1412-mark-comsource-interfaces-as-idispatch.md) | [https://github.com/dotnet/roslyn-analyzers/issues/428](https://github.com/dotnet/roslyn-analyzers/issues/428)
[CA1413](ca1413-avoid-non-public-fields-in-com-visible-value-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/429](https://github.com/dotnet/roslyn-analyzers/issues/429)
[CA1414](ca1414-mark-boolean-p-invoke-arguments-with-marshalas.md) | [https://github.com/dotnet/roslyn-analyzers/issues/430](https://github.com/dotnet/roslyn-analyzers/issues/430)
[CA1415](ca1415-declare-p-invokes-correctly.md) | [https://github.com/dotnet/roslyn-analyzers/issues/431](https://github.com/dotnet/roslyn-analyzers/issues/431)
[CA1500](ca1500-variable-names-should-not-match-field-names.md) | [https://github.com/dotnet/roslyn-analyzers/issues/432](https://github.com/dotnet/roslyn-analyzers/issues/432)
[CA1600](ca1600-do-not-use-idle-process-priority.md) | [https://github.com/dotnet/roslyn-analyzers/issues/438](https://github.com/dotnet/roslyn-analyzers/issues/438)
[CA1601](ca1601-do-not-use-timers-that-prevent-power-state-changes.md) | [https://github.com/dotnet/roslyn-analyzers/issues/439](https://github.com/dotnet/roslyn-analyzers/issues/439)
[CA1700](ca1700-do-not-name-enum-values-reserved.md) | [https://github.com/dotnet/roslyn-analyzers/issues/440](https://github.com/dotnet/roslyn-analyzers/issues/440)
[CA1704](ca1704-identifiers-should-be-spelled-correctly.md) | [https://github.com/dotnet/roslyn-analyzers/issues/443](https://github.com/dotnet/roslyn-analyzers/issues/443)
[CA1709](ca1709-identifiers-should-be-cased-correctly.md) | [https://github.com/dotnet/roslyn-analyzers/issues/445](https://github.com/dotnet/roslyn-analyzers/issues/445)
[CA1713](ca1713-events-should-not-have-before-or-after-prefix.md) | [https://github.com/dotnet/roslyn-analyzers/issues/449](https://github.com/dotnet/roslyn-analyzers/issues/449)
[CA1719](ca1719-parameter-names-should-not-match-member-names.md) | [https://github.com/dotnet/roslyn-analyzers/issues/453](https://github.com/dotnet/roslyn-analyzers/issues/453)
[CA1722](ca1722-identifiers-should-not-have-incorrect-prefix.md) | [https://github.com/dotnet/roslyn-analyzers/issues/455](https://github.com/dotnet/roslyn-analyzers/issues/455)
[CA1726](ca1726-use-preferred-terms.md) | [https://github.com/dotnet/roslyn-analyzers/issues/458](https://github.com/dotnet/roslyn-analyzers/issues/458)
[CA1804](ca1804.md) | [https://github.com/dotnet/roslyn-analyzers/issues/461](https://github.com/dotnet/roslyn-analyzers/issues/461)
[CA1811](ca1811.md) | [https://github.com/dotnet/roslyn-analyzers/issues/464](https://github.com/dotnet/roslyn-analyzers/issues/464)
[CA1900](ca1900.md) | [https://github.com/dotnet/roslyn-analyzers/issues/474](https://github.com/dotnet/roslyn-analyzers/issues/474)
[CA2001](ca2001.md) | [https://github.com/dotnet/roslyn-analyzers/issues/477](https://github.com/dotnet/roslyn-analyzers/issues/477)
[CA2004](ca2004.md) | [https://github.com/dotnet/roslyn-analyzers/issues/479](https://github.com/dotnet/roslyn-analyzers/issues/479)
[CA2006](ca2006.md) | [https://github.com/dotnet/roslyn-analyzers/issues/480](https://github.com/dotnet/roslyn-analyzers/issues/480)
[CA2109](ca2109.md) | [https://github.com/dotnet/roslyn-analyzers/issues/488](https://github.com/dotnet/roslyn-analyzers/issues/488)
[CA2204](ca2204.md) | [https://github.com/dotnet/roslyn-analyzers/issues/529](https://github.com/dotnet/roslyn-analyzers/issues/529)
[CA2205](ca2205.md) | [https://github.com/dotnet/roslyn-analyzers/issues/530](https://github.com/dotnet/roslyn-analyzers/issues/530)
[CA2212](ca2212.md) | [https://github.com/dotnet/roslyn-analyzers/issues/534](https://github.com/dotnet/roslyn-analyzers/issues/534)
[CA2215](ca2215.md) | [https://github.com/dotnet/roslyn-analyzers/issues/535](https://github.com/dotnet/roslyn-analyzers/issues/535)
[CA2232](ca2232.md) | [https://github.com/dotnet/roslyn-analyzers/issues/545](https://github.com/dotnet/roslyn-analyzers/issues/545)
[CA2236](ca2236.md) | [https://github.com/dotnet/roslyn-analyzers/issues/548](https://github.com/dotnet/roslyn-analyzers/issues/548)
[CA2238](ca2238.md) | [https://github.com/dotnet/roslyn-analyzers/issues/549](https://github.com/dotnet/roslyn-analyzers/issues/549)
[CA2239](ca2239.md) | [https://github.com/dotnet/roslyn-analyzers/issues/550](https://github.com/dotnet/roslyn-analyzers/issues/550)
[CA2240](ca2240.md) | [https://github.com/dotnet/roslyn-analyzers/issues/551](https://github.com/dotnet/roslyn-analyzers/issues/551)

### <a name="deprecated-rules"></a>Zastaralá pravidla

Následující starší pravidla analýzy FxCop jsou zastaralá a nebudou implementována jako analyzátory. Další informace můžete najít podle ID pravidla (například **CA1009**) na [stránce problémy GitHubu Roslyn-analyzers](https://github.com/dotnet/roslyn-analyzers/issues?utf8=%E2%9C%93&q=is:issue+label:FxCop-Port).

- [CA1009](ca1009-declare-event-handlers-correctly.md)
- [CA1020](ca1020-avoid-namespaces-with-few-types.md)
- [CA1025](ca1025-replace-repetitive-arguments-with-params-array.md)
- [CA1026](ca1026-default-parameters-should-not-be-used.md)
- [CA1035](ca1035-icollection-implementations-have-strongly-typed-members.md)
- [CA1038](ca1038-enumerators-should-be-strongly-typed.md)
- [CA1039](ca1039-lists-are-strongly-typed.md)
- [CA1059](ca1059-members-should-not-expose-certain-concrete-types.md)
- [CA1302](ca1302-do-not-hardcode-locale-specific-strings.md)
- [CA1400](ca1400-p-invoke-entry-points-should-exist.md)
- [CA1406](ca1406-avoid-int64-arguments-for-visual-basic-6-clients.md)
- [CA1504](ca1504-review-misleading-field-names.md)
- [CA1701](ca1701-resource-string-compound-words-should-be-cased-correctly.md)
- [CA1702](ca1702.md)
- [CA1703](ca1703.md)
- [CA1800](ca1800.md)
- [CA1809](ca1809.md)
- [CA1901](ca1901.md)
- [CA1903](ca1903.md)
- [CA2003](ca2003.md)
- [CA2102](ca2102.md)
- [CA2103](ca2103.md)
- [CA2104](ca2104.md)
- [CA2105](ca2105.md)
- [CA2106](ca2106.md)
- [CA2107](ca2107.md)
- [CA2108](ca2108.md)
- [CA2111](ca2111.md)
- [CA2112](ca2112.md)
- [CA2114](ca2114.md)
- [CA2115](ca2115.md)
- [CA2116](ca2116.md)
- [CA2117](ca2117.md)
- [CA2118](ca2118.md)
- [CA2120](ca2120.md)
- [CA2121](ca2121.md)
- [CA2122](ca2122.md)
- [CA2123](ca2123.md)
- [CA2124](ca2124.md)
- [CA2126](ca2126.md)
- [CA2130](ca2130.md)
- [CA2131](ca2131.md)
- [CA2132](ca2132.md)
- [CA2133](ca2133.md)
- [CA2134](ca2134.md)
- [CA2135](ca2135.md)
- [CA2136](ca2136.md)
- [CA2137](ca2137.md)
- [CA2138](ca2138.md)
- [CA2139](ca2139.md)
- [CA2140](ca2140.md)
- [CA2141](ca2141.md)
- [CA2142](ca2142.md)
- [CA2143](ca2143.md)
- [CA2144](ca2144.md)
- [CA2145](ca2145.md)
- [CA2146](ca2146.md)
- [CA2147](ca2147.md)
- [CA2149](ca2149.md)
- [CA2151](ca2151.md)
- [CA2202](ca2202.md)
- [CA2210](ca2210.md)
- [CA2220](ca2220.md)
- [CA2221](ca2221.md)
- [CA2222](ca2222.md) ([odůvodnění](https://github.com/dotnet/roslyn-analyzers/issues/1378))
- [CA2223](ca2223.md)
- [CA2228](ca2228.md)
- [CA2230](ca2230.md)
- [CA2233](ca2233.md)
- [CA5122](ca5122.md)

## <a name="see-also"></a>Viz také:

- [Pravidla Microsoft. CodeAnalysis. FxCopAnalyzers](https://github.com/dotnet/roslyn-analyzers/blob/master/src/Microsoft.CodeAnalysis.FxCopAnalyzers/Microsoft.CodeAnalysis.FxCopAnalyzers.md)
