---
title: Sada pravidel Smíšená doporučená pravidla
ms.date: 11/04/2016
ms.topic: reference
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3f0daaf22f3e944dd76802060c53c64d40a4da04
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72649220"
---
# <a name="mixed-recommended-rules-rule-set"></a>Sada pravidel Smíšená doporučená pravidla

Doporučená pravidla Microsoftu se zaměřují na nejběžnější a kritické problémy ve vašich C++ projektech, které podporují modul CLR (Common Language Runtime), včetně potenciálních bezpečnostních otvorů, chyb aplikací a dalších důležitých chyb logiky a návrhu. Tato sada pravidel zahrnuje všechna pravidla v sadě pravidel [smíšeného minima Rules](mixed-minimum-rules-rule-set.md) .

Zahrňte tuto sadu pravidel v jakékoli vlastní sadě pravidel, kterou vytvoříte C++ pro projekty, které podporují modul CLR (Common Language Runtime).

|Pravidlo|Popis|
|----------|-----------------|
|[C6001](../code-quality/c6001.md)|Použití neinicializované paměti|
|[C6011](../code-quality/c6011.md)|Přesměrování ukazatele null|
|[C6029](../code-quality/c6029.md)|Použití nezkontrolované hodnoty|
|[C6031](../code-quality/c6031.md)|Návratová hodnota ignorována|
|[C6053](../code-quality/c6053.md)|Nula ukončení volání|
|[C6054](../code-quality/c6054.md)|Chybí nulové zakončení.|
|[C6059](../code-quality/c6059.md)|Chybné zřetězení|
|[C6063](../code-quality/c6063.md)|Chybí argument řetězce pro formátování funkce|
|[C6064](../code-quality/c6064.md)|Chybějící argument typu Integer pro formátování funkce|
|[C6066](../code-quality/c6066.md)|Chybí argument ukazatele pro formátování funkce|
|[C6067](../code-quality/c6067.md)|Chybí argument ukazatele řetězce pro formátování funkce|
|[C6101](../code-quality/c6101.md)|Vracení neinicializované paměti|
|[C6200](../code-quality/c6200.md)|Index překračuje maximum vyrovnávací paměti.|
|[C6201](../code-quality/c6201.md)|Index překračuje maximum vyrovnávací paměti zásobníku.|
|[C6214](../code-quality/c6214.md)|Neplatné přetypování HRESULT na BOOL|
|[C6215](../code-quality/c6215.md)|Neplatné přetypování typu BOOL na HRESULT|
|[C6216](../code-quality/c6216.md)|Neplatné přetypování vložené kompilátorem typu BOOL na HRESULT|
|[C6217](../code-quality/c6217.md)|Neplatný test HRESULT s NOT|
|[C6220](../code-quality/c6220.md)|Neplatné porovnání HRESULT s-1|
|[C6226](../code-quality/c6226.md)|Neplatné přiřazení HRESULT na-1|
|[C6230](../code-quality/c6230.md)|Neplatné použití HRESULT jako Boolean|
|[C6235](../code-quality/c6235.md)|Nenulová konstanta s logickým operátorem OR|
|[C6236](../code-quality/c6236.md)|Logický operátor OR s nenulovou konstantou|
|[C6237](../code-quality/c6237.md)|Nula s logickým operátorem and ztratí vedlejší účinky|
|[C6242](../code-quality/c6242.md)|Vynucené místní unwind|
|[C6248](../code-quality/c6248.md)|Vytváření seznamu DACL s hodnotou null|
|[C6250](../code-quality/c6250.md)|Nevydané popisovače adres|
|[C6255](../code-quality/c6255.md)|Nechráněné použití alokace|
|[C6258](../code-quality/c6258.md)|Použití vlákna ukončit|
|[C6259](../code-quality/c6259.md)|Mrtvý kód v bitovém nebo omezeném přepínači|
|[C6260](../code-quality/c6260.md)|Použití aritmetických bajtů|
|[C6262](../code-quality/c6262.md)|Nadměrné využití zásobníku|
|[C6263](../code-quality/c6263.md)|Použití alokačního příkazu ve smyčce|
|[C6268](../code-quality/c6268.md)|V přetypování chybí kulaté závorky.|
|[C6269](../code-quality/c6269.md)|Byl ignorován odkaz na ukazatel.|
|[C6270](../code-quality/c6270.md)|Chybí argument typu float pro formátování funkce|
|[C6271](../code-quality/c6271.md)|Nadbytečný argument pro formátování funkce|
|[C6272](../code-quality/c6272.md)|Argument jiného než typu float pro formátování funkce|
|[C6273](../code-quality/c6273.md)|Argument jiného než typu Integer pro formátování funkce|
|[C6274](../code-quality/c6274.md)|Argument bez znaku pro formátování funkce|
|[C6276](../code-quality/c6276.md)|Neplatné přetypování řetězce|
|[C6277](../code-quality/c6277.md)|Neplatné volání funkce CreateProcess|
|[C6278](../code-quality/c6278.md)|Array – nová neshoda skalárního odstranění|
|[C6279](../code-quality/c6279.md)|Neshoda mezi skalárním a novým polem – odstranění|
|[C6280](../code-quality/c6280.md)|Neshoda přidělení paměti – neshoda|
|[C6281](../code-quality/c6281.md)|Priorita bitového vztahu|
|[C6282](../code-quality/c6282.md)|Přiřazení nahrazuje test|
|[C6283](../code-quality/c6283.md)|Primitivní pole – neshoda s novým skalárním odstraněním|
|[C6284](../code-quality/c6284.md)|Neplatný argument objektu pro formátování funkce|
|[C6285](../code-quality/c6285.md)|Logický operátor OR konstanta|
|[C6286](../code-quality/c6286.md)|Nenulový logický operátor OR neztratící vedlejší účinky|
|[C6287](../code-quality/c6287.md)|Redundantní test|
|[C6288](../code-quality/c6288.md)|Vzájemné zahrnutí přes logický operátor and je false.|
|[C6289](../code-quality/c6289.md)|Vzájemné vyloučení přes logický operátor OR je pravda.|
|[C6290](../code-quality/c6290.md)|Logický operátor NOT a Priorita|
|[C6291](../code-quality/c6291.md)|Logický operátor NOT ani Priorita|
|[C6292](../code-quality/c6292.md)|Smyčka počítá směrem nahoru od maxima|
|[C6293](../code-quality/c6293.md)|Smyčka odpočítává dolů z minima|
|[C6294](../code-quality/c6294.md)|Tělo smyčky není nikdy provedeno|
|[C6295](../code-quality/c6295.md)|Nekonečná smyčka|
|[C6296](../code-quality/c6296.md)|Smyčka se spustila jenom jednou.|
|[C6297](../code-quality/c6297.md)|Výsledek přetypování Shift na větší velikost|
|[C6299](../code-quality/c6299.md)|Bitového pole na logické porovnání|
|[C6302](../code-quality/c6302.md)|Neplatný argument řetězce znaků pro formátování funkce|
|[C6303](../code-quality/c6303.md)|Neplatný argument řetězce s velkým znakem pro formátování funkce|
|[C6305](../code-quality/c6305.md)|Neshoda s použitím velikosti a počtu|
|[C6306](../code-quality/c6306.md)|Nesprávné volání funkce argumentu proměnné|
|[C6308](../code-quality/c6308.md)|Vrácení realokace|
|[C6310](../code-quality/c6310.md)|Neplatná konstanta filtru výjimky|
|[C6312](../code-quality/c6312.md)|Výjimka při provádění smyčky pro pokračování|
|[C6314](../code-quality/c6314.md)|Priorita bitového operátoru OR|
|[C6317](../code-quality/c6317.md)|Nedoplnit|
|[C6318](../code-quality/c6318.md)|Výjimka – hledání v pokračování|
|[C6319](../code-quality/c6319.md)|Ignoruje čárkou|
|[C6324](../code-quality/c6324.md)|Kopírovat řetězec místo řetězce porovnání|
|[C6328](../code-quality/c6328.md)|Potenciální Neshoda typu argumentu|
|[C6331](../code-quality/c6331.md)|VirtualFree neplatné příznaky|
|[C6332](../code-quality/c6332.md)|Neplatný parametr VirtualFree|
|[C6333](../code-quality/c6333.md)|VirtualFree neplatná velikost|
|[C6335](../code-quality/c6335.md)|Nevrácení popisovače procesu|
|[C6381](../code-quality/c6381.md)|Chybí informace o vypnutí.|
|[C6383](../code-quality/c6383.md)|Přetečení vyrovnávací paměti počtu bajtů počtu elementů|
|[C6384](../code-quality/c6384.md)|Dělení velikosti ukazatele|
|[C6385](../code-quality/c6385.md)|Přetečení čtení|
|[C6386](../code-quality/c6386.md)|Přetečení zápisu|
|[C6387](../code-quality/c6387.md)|Neplatná hodnota parametru|
|[C6388](../code-quality/c6388.md)|Neplatná hodnota parametru|
|[C6500](../code-quality/c6500.md)|Neplatná vlastnost atributu|
|[C6501](../code-quality/c6501.md)|Konfliktní hodnoty vlastností atributu|
|[C6503](../code-quality/c6503.md)|Odkazy nemohou mít hodnotu null.|
|[C6504](../code-quality/c6504.md)|Null na bez ukazatele|
|[C6505](../code-quality/c6505.md)|Vlastnost mustcheck na void|
|[C6506](../code-quality/c6506.md)|Velikost vyrovnávací paměti na neukazateli nebo poli|
|[C6508](../code-quality/c6508.md)|Přístup pro zápis na konstantě|
|[C6509](../code-quality/c6509.md)|Vrácení se používá v předběžné podmínce.|
|[C6510](../code-quality/c6510.md)|Hodnota null byla ukončena na neukazateli.|
|[C6511](../code-quality/c6511.md)|Vlastnost mustcheck musí být Ano nebo ne.|
|[C6513](../code-quality/c6513.md)|Velikost prvku bez velikosti vyrovnávací paměti|
|[C6514](../code-quality/c6514.md)|Velikost vyrovnávací paměti překračuje velikost pole.|
|[C6515](../code-quality/c6515.md)|Velikost vyrovnávací paměti na bez ukazatele|
|[C6516](../code-quality/c6516.md)|Atribut nemá žádné vlastnosti.|
|[C6517](../code-quality/c6517.md)|Platná velikost pro vyrovnávací paměť, která není čitelná|
|[C6518](../code-quality/c6518.md)|Zapisovatelná velikost pro vyrovnávací paměť, která není zapisovatelná|
|[C6522](../code-quality/c6522.md)|Neplatný typ řetězce velikosti|
|[C6525](../code-quality/c6525.md)|Neplatná velikost řetězce nedosažitelného umístění|
|[C6527](../code-quality/c6527.md)|Neplatná Anotace: vlastnost NeedsRelease se nedá použít u hodnot typu void.|
|[C6530](../code-quality/c6530.md)|Nerozpoznaný styl řetězce formátu|
|[C6540](../code-quality/c6540.md)|Použití poznámek k atributům u této funkce zruší platnost všech existujících poznámek __declspec.|
|[C6551](../code-quality/c6551.md)|Neplatná specifikace velikosti: výraz nejde analyzovat.|
|[C6552](../code-quality/c6552.md)|Neplatný DEREF = nebo Notref =: výraz nelze analyzovat|
|[C6701](../code-quality/c6701.md)|Hodnota není platná hodnota Ano/Ne/možná.|
|[C6702](../code-quality/c6702.md)|Hodnota není řetězcová hodnota.|
|[C6703](../code-quality/c6703.md)|Hodnota není číslo.|
|[C6704](../code-quality/c6704.md)|Neočekávaná chyba výrazu poznámky|
|[C6705](../code-quality/c6705.md)|Očekávaný počet argumentů pro anotaci neodpovídá skutečnému počtu argumentů pro poznámku.|
|[C6706](../code-quality/c6706.md)|Neočekávaná chyba poznámky u poznámky|
|[C6995](../code-quality/c6995.md)|Nepovedlo se uložit soubor protokolu XML.|
|[C26100](../code-quality/c26100.md)|Podmínka časování|
|[C26101](../code-quality/c26101.md)|Selhání použití propojené operace správně|
|[C26110](../code-quality/c26110.md)|Selhání volajícího blokovat zámek|
|[C26111](../code-quality/c26111.md)|Selhání volajícího uvolnit zámek|
|[C26112](../code-quality/c26112.md)|Volající nemůže držet žádný zámek.|
|[C26115](../code-quality/c26115.md)|Selhání uvolnění zámku|
|[C26116](../code-quality/c26116.md)|Selhání získání nebo udržení zámku|
|[C26117](../code-quality/c26117.md)|Uvolňuje se neuchovávaný zámek.|
|[C26140](../code-quality/c26140.md)|Chyba anotace SAL pro Concurrency|
|[C28020](../code-quality/c28020.md)|Výraz není na tomto volání pravdivý.|
|[C28021](../code-quality/c28021.md)|Parametr, který se dá opatřit poznámkami, musí být ukazatelem.|
|[C28022](../code-quality/c28022.md)|Třídy funkcí této funkce se neshodují s třídami Functions na definici TypeDef použitou k jejímu definování.|
|[C28023](../code-quality/c28023.md)|Přiřazená nebo předaná funkce by měla mít \_Function \_class \_ anotaci pro alespoň jednu ze tříd (ES).|
|[C28024](../code-quality/c28024.md)|Ukazatel funkce, ke kterému se přiřazuje, je opatřen poznámkou se třídou Function, která není obsažena v seznamu tříd funkcí.|
|[C28039](../code-quality/c28039.md)|Typ skutečného parametru by měl přesně odpovídat typu|
|[C28112](../code-quality/c28112.md)|K proměnné, ke které se dá přistupovat přes propojenou funkci, se musí vždycky přistupovat prostřednictvím propojené funkce.|
|[C28113](../code-quality/c28113.md)|Přístup k místní proměnné prostřednictvím propojené funkce|
|[C28125](../code-quality/c28125.md)|Funkce musí být volána v rámci bloku try/except.|
|[C28137](../code-quality/c28137.md)|Argument proměnné by měl být (literál) konstanta.|
|[C28138](../code-quality/c28138.md)|Konstantní argument by měl být místo proměnné.|
|[C28159](../code-quality/c28159.md)|Zvažte místo toho použití jiné funkce.|
|[C28160](../code-quality/c28160.md)|Poznámka k chybě|
|[C28163](../code-quality/c28163.md)|Funkce by nikdy neměla být volána v rámci bloku try/except|
|[C28164](../code-quality/c28164.md)|Argument se předává funkci, která očekává ukazatel na objekt (ne ukazatel na ukazatel).|
|[C28182](../code-quality/c28182.md)|Přesměrování ukazatele s hodnotou NULL. Ukazatel obsahuje stejnou hodnotu NULL jako jiný ukazatel.|
|[C28183](../code-quality/c28183.md)|Argumentem může být jedna hodnota a je kopie hodnoty nalezené v ukazateli.|
|[C28193](../code-quality/c28193.md)|Proměnná obsahuje hodnotu, kterou je třeba prozkoumat.|
|[C28196](../code-quality/c28196.md)|Požadavek není splněn. (Výraz se nevyhodnotí jako true.)|
|[C28202](../code-quality/c28202.md)|Neplatný odkaz na nestatický člen|
|[C28203](../code-quality/c28203.md)|Nejednoznačný odkaz na člena třídy.|
|[C28205](../code-quality/c28205.md)|\_Success \_ nebo \_On \_failure \_ použito v neplatném kontextu|
|[C28206](../code-quality/c28206.md)|Levý operand ukazuje na strukturu, použijte '-> '|
|[C28207](../code-quality/c28207.md)|Levý operand je struktura, použijte '. '|
|[C28209](../code-quality/c28209.md)|Deklarace pro symbol má konfliktní deklaraci.|
|[C28210](../code-quality/c28210.md)|Poznámky pro kontext __on_failure nesmí být v explicitním předběžném kontextu.|
|[C28211](../code-quality/c28211.md)|Pro SAL_context se očekává název statického kontextu.|
|[C28212](../code-quality/c28212.md)|U poznámky se očekává výraz ukazatele.|
|[C28213](../code-quality/c28213.md)|@No__t_0Use \_decl \_annotations \_ anotace musí být použita k odkazování na předchozí deklaraci beze změny.|
|[C28214](../code-quality/c28214.md)|Názvy parametrů atributu musí být P1... P9|
|[C28215](../code-quality/c28215.md)|Typefix nelze použít na parametr, který již má typefix|
|[C28216](../code-quality/c28216.md)|Anotace Poznámka checkreturn se vztahuje pouze na následné podmínky pro konkrétní parametr funkce.|
|[C28217](../code-quality/c28217.md)|Pro funkci se počet parametrů poznámky neshoduje s počtem nalezeným v souboru.|
|[C28218](../code-quality/c28218.md)|Parametr poznámky pro parametr funkce se neshoduje s parametrem nalezeným v souboru.|
|[C28219](../code-quality/c28219.md)|Pro anotaci parametru v poznámce je očekáván člen výčtu.|
|[C28220](../code-quality/c28220.md)|Pro anotaci parametru v poznámce je očekáván celočíselný výraz.|
|[C28221](../code-quality/c28221.md)|Pro parametr v poznámce je očekáván řetězcový výraz.|
|[C28222](../code-quality/c28222.md)|pro anotaci se očekává __yes, \__no nebo \__maybe.|
|[C28223](../code-quality/c28223.md)|Nebyl nalezen očekávaný token/identifikátor pro anotaci, parametr|
|[C28224](../code-quality/c28224.md)|Poznámka vyžaduje parametry.|
|[C28225](../code-quality/c28225.md)|Nebyl nalezen správný počet požadovaných parametrů v poznámce|
|[C28226](../code-quality/c28226.md)|Anotace nemůže být také PrimOp (v aktuální deklaraci)|
|[C28227](../code-quality/c28227.md)|Anotace nemůže být také PrimOp (viz předchozí deklarace)|
|[C28228](../code-quality/c28228.md)|Parametr Anotace: v poznámkách nelze použít typ.|
|[C28229](../code-quality/c28229.md)|Poznámka nepodporuje parametry|
|[C28230](../code-quality/c28230.md)|Typ parametru nemá žádného člena.|
|[C28231](../code-quality/c28231.md)|Anotace je platná pouze pro pole.|
|[C28232](../code-quality/c28232.md)|předplatná, post nebo DEREF nejsou aplikovány na žádnou poznámku.|
|[C28233](../code-quality/c28233.md)|použití pre, post nebo DEREF pro blok|
|[C28234](../code-quality/c28234.md)|výraz __at se nedá použít u aktuální funkce.|
|[C28235](../code-quality/c28235.md)|Funkce nemůže být samostatná jako anotace.|
|[C28236](../code-quality/c28236.md)|Anotaci nelze použít ve výrazu.|
|[C28237](../code-quality/c28237.md)|Poznámka k parametru už není podporovaná.|
|[C28238](../code-quality/c28238.md)|Poznámka u parametru má více než jednu hodnotu, stringValue a longValue. Použít paramn = XXX|
|[C28239](../code-quality/c28239.md)|Poznámka u parametru má hodnotu, stringValue nebo longValue; a paramn = xxx. Použít pouze paramn = XXX|
|[C28240](../code-quality/c28240.md)|Poznámka u parametru má param2, ale ne param1.|
|[C28241](../code-quality/c28241.md)|Poznámka pro funkci v parametru nebyla rozpoznána.|
|[C28243](../code-quality/c28243.md)|Poznámka pro funkci v parametru vyžaduje více odkazů, než je skutečný typ s poznámkami. umožňuje|
|[C28244](../code-quality/c28244.md)|Anotace for Function má neanalyzovatelné parametry/externí anotaci.|
|[C28245](../code-quality/c28245.md)|Poznámka pro funkci přihlásí this na funkci bez členu.|
|[C28246](../code-quality/c28246.md)|Anotace parametru pro funkci se neshoduje s typem parametru.|
|[C28250](../code-quality/c28250.md)|Nekonzistentní Poznámka pro funkci: předchozí instance obsahuje chybu.|
|[C28251](../code-quality/c28251.md)|Nekonzistentní Poznámka pro funkci: Tato instance obsahuje chybu.|
|[C28252](../code-quality/c28252.md)|Nekonzistentní Poznámka pro funkci: parametr má v této instanci jiné anotace.|
|[C28253](../code-quality/c28253.md)|Nekonzistentní Poznámka pro funkci: parametr má v této instanci jiné anotace.|
|[C28254](../code-quality/c28254.md)|dynamic_cast < > () se v poznámkách nepodporuje.|
|[C28262](../code-quality/c28262.md)|Chyba syntaxe v poznámce byla nalezena ve funkci pro poznámku|
|[C28263](../code-quality/c28263.md)|Našla se chyba syntaxe v podmíněné poznámce pro vnitřní anotaci.|
|[C28267](../code-quality/c28267.md)|Ve funkci byla nalezena Poznámka s chybou syntaxe v poznámkách.|
|[C28272](../code-quality/c28272.md)|Poznámka pro funkci, parametr při zkoumání je nekonzistentní s deklarací funkce|
|[C28273](../code-quality/c28273.md)|V případě funkcí jsou změny nekonzistentní s deklarací funkce|
|[C28275](../code-quality/c28275.md)|Parametr pro \_Macro \_value \_ má hodnotu null.|
|[C28279](../code-quality/c28279.md)|Pro symbol byl nalezen prvek Begin bez odpovídajícího příkazu end.|
|[C28280](../code-quality/c28280.md)|Pro symbol byl nalezen znak end bez odpovídajícího prvku Begin.|
|[C28282](../code-quality/c28282.md)|Řetězce formátu musí být v předběžných podmínkách.|
|[C28285](../code-quality/c28285.md)|Pro funkci, Chyba syntaxe v parametru|
|[C28286](../code-quality/c28286.md)|Pro funkci se chyba syntaxe blíží konci.|
|[C28287](../code-quality/c28287.md)|Pro funkci, Chyba syntaxe v \_At anotace \_ () (nerozpoznaný název parametru)|
|[C28288](../code-quality/c28288.md)|Pro funkci, Chyba syntaxe v \_At anotace \_ () (neplatný název parametru)|
|[C28289](../code-quality/c28289.md)|Funkce: ReadableTo nebo Writableto nebyl neobsahovala omezení-spec jako parametr.|
|[C28290](../code-quality/c28290.md)|Anotace for Function obsahuje více externích typů, než je skutečný počet parametrů.|
|[C28291](../code-quality/c28291.md)|Hodnota post null/NotNull na DEREF Level 0 nemá význam pro funkci.|
|[C28300](../code-quality/c28300.md)|Operandy výrazu nekompatibilních typů pro operátor|
|[C28301](../code-quality/c28301.md)|Žádné poznámky pro první deklaraci funkce|
|[C28302](../code-quality/c28302.md)|V poznámce byl nalezen operátor nadbytečné \_Deref \_.|
|[C28303](../code-quality/c28303.md)|V poznámce byl nalezen nejednoznačný \_Deref operátor \_.|
|[C28304](../code-quality/c28304.md)|Byl nalezen nesprávně umístěný \_Notref operátor \_ použit na token.|
|[C28305](../code-quality/c28305.md)|Zjistila se chyba při analýze tokenu.|
|[C28306](../code-quality/c28306.md)|Poznámka k parametru je zastarávající|
|[C28307](../code-quality/c28307.md)|Poznámka k parametru je zastarávající|
|[C28350](../code-quality/c28350.md)|Poznámka popisuje situaci, která není podmíněně platná.|
|[C28351](../code-quality/c28351.md)|Poznámka popisuje, kde v podmínce nelze použít dynamickou hodnotu (proměnnou).|
|[CA1001](../code-quality/ca1001.md)|Typy, které vlastní uvolnitelné pole, by měly být uvolnitelné|
|[CA1009](../code-quality/ca1009.md)|Deklarujte správně obslužné rutiny událostí|
|[CA1016](../code-quality/ca1016.md)|Označte sestavení pomocí AssemblyVersionAttribute|
|[CA1033](../code-quality/ca1033.md)|Metody rozhraní by měly být volatelné podřízenými typy|
|[CA1049](../code-quality/ca1049.md)|Typy, které vlastní nativní prostředky, by měly být uvolnitelné|
|[CA1060](../code-quality/ca1060.md)|Přesuňte volání nespravovaných kódů do třídy NativeMethods|
|[CA1061](../code-quality/ca1061.md)|Neskrývejte metody základní třídy|
|[CA1063](../code-quality/ca1063.md)|Implementuje správně IDisposable|
|[CA1065](../code-quality/ca1065.md)|Nevyvolávejte výjimky v neočekávaných umístěních|
|[CA1301](../code-quality/ca1301.md)|Vyhněte se duplicitním akcelerátorům|
|[CA1400](../code-quality/ca1400.md)|Vstupní body volání nespravovaného kódu by měly existovat|
|[CA1401](../code-quality/ca1401.md)|Volání nespravovaných kódů by neměla být viditelná|
|[CA1403](../code-quality/ca1403.md)|Typy automatického rozložení by neměly být viditelné modelu COM|
|[CA1404](../code-quality/ca1404.md)|Volejte GetLastError ihned po volání nespravovaného kódu|
|[CA1405](../code-quality/ca1405.md)|Základní typy viditelného typu modelu COM by měly být viditelné modelu COM|
|[CA1410](../code-quality/ca1410.md)|Metody registrace modelu COM by si měly odpovídat|
|[CA1415](../code-quality/ca1415.md)|Deklarujte správně volání nespravovaných kódů|
|[CA1821](../code-quality/ca1821.md)|Odeberte prázdné finalizační metody|
|[CA1900](../code-quality/ca1900.md)|Pole typů hodnot by měla být přenosná|
|[CA1901](../code-quality/ca1901.md)|Deklarace volání nespravovaného kódu by měla být přenosná|
|[CA2002](../code-quality/ca2002.md)|Nepoužívejte zámky u objektů se slabou identitou|
|[CA2100](../code-quality/ca2100.md)|Zkontrolujte chyby zabezpečení u dotazů SQL|
|[CA2101](../code-quality/ca2101.md)|Určete zařazování pro argumenty řetězce volání nespravovaného kódu|
|[CA2108](../code-quality/ca2108.md)|Zkontrolujte deklarativní zabezpečení u typů hodnot|
|[CA2111](../code-quality/ca2111.md)|Ukazatele by neměly být viditelné|
|[CA2112](../code-quality/ca2112.md)|Zabezpečené typy by neměly vystavovat pole|
|[CA2114](../code-quality/ca2114.md)|Zabezpečení metod by mělo být nadmnožinou typu|
|[CA2116](../code-quality/ca2116.md)|Metody APTCA by měly volat pouze metody APTCA|
|[CA2117](../code-quality/ca2117.md)|Typy APTCA by měl rozšiřovat pouze základní typy APTCA|
|[CA2122](../code-quality/ca2122.md)|Nezveřejňujte nepřímo metody s požadavky propojení|
|[CA2123](../code-quality/ca2123.md)|Požadavky na propojení přepisů by měly být identické s bází|
|[CA2124](../code-quality/ca2124.md)|Zabalte ohroženou klauzuli finally do vnějšího bloku try|
|[CA2126](../code-quality/ca2126.md)|Požadavky na propojení typů vyžadují požadavky na dědičnost|
|[CA2131](../code-quality/ca2131.md)|Typy kritické pro zabezpečení se nesmí účastnit ekvivalence typů|
|[CA2132](../code-quality/ca2132.md)|Výchozí konstruktory musí být alespoň tak kritické, jako výchozí konstruktory základního typu|
|[CA2133](../code-quality/ca2133.md)|Delegáti musí mít vazbu s metodami s konzistentní transparentností|
|[CA2134](../code-quality/ca2134.md)|Metody musí při přepisování základních metod zachovávat konzistentní transparentnost|
|[CA2137](../code-quality/ca2137.md)|Transparentní metody musí obsahovat pouze ověřitelné IL|
|[CA2138](../code-quality/ca2138.md)|Transparentní metody nesmí volat metody s atributem SuppressUnmanagedCodeSecurity|
|[CA2140](../code-quality/ca2140.md)|Transparentní kód nesmí odkazovat na položky kritické pro zabezpečení|
|[CA2141](../code-quality/ca2141.md)|Transparentní metody nesmí splňovat LinkDemand.|
|[CA2146](../code-quality/ca2146.md)|Typy musí být alespoň tak kritické, jako jejich základní typy a rozhraní|
|[CA2147](../code-quality/ca2147.md)|Transparentní metody nemusí používat kontrolní příkazy zabezpečení|
|[CA2149](../code-quality/ca2149.md)|Transparentní metody nesmí provádět volání nativního kódu|
|[CA2200](../code-quality/ca2200.md)|Znovu vyvolejte pro zachování podrobností zásobníku|
|[CA2202](../code-quality/ca2202.md)|Neuvolňujte objekty několikrát|
|[CA2207](../code-quality/ca2207.md)|Inicializujte statická pole s typem hodnoty vloženě|
|[CA2212](../code-quality/ca2212.md)|Neoznačujte obsluhované komponenty pomocí WebMethod|
|[CA2213](../code-quality/ca2213.md)|Uvolnitelná pole by měla být uvolněna|
|[CA2214](../code-quality/ca2214.md)|Nevolejte přepisovatelné metody v konstruktorech|
|[CA2216](../code-quality/ca2216.md)|Uvolnitelné typy by měly deklarovat finalizační metodu|
|[CA2220](../code-quality/ca2220.md)|Finalizační metody by měly volat finalizační metodu základní třídy|
|[CA2229](../code-quality/ca2229.md)|Implementujte serializační konstruktory|
|[CA2231](../code-quality/ca2231.md)|Přetižte operátor rovnosti při přetížení ValueType.Equals|
|[CA2232](../code-quality/ca2232.md)|Označte vstupní body modelu Windows Forms pomocí STAThread|
|[CA2235](../code-quality/ca2235.md)|Označte všechna neserializovatelná pole|
|[CA2236](../code-quality/ca2236.md)|Volejte metody základní třídy u typů ISerializable|
|[CA2237](../code-quality/ca2237.md)|Označte typy ISerializable pomocí SerializableAttribute|
|[CA2238](../code-quality/ca2238.md)|Implementujte správně metody serializace|
|[CA2240](../code-quality/ca2240.md)|Implementujte správně ISerializable|
|[CA2241](../code-quality/ca2241.md)|Zadejte správné argumenty pro metody formátování|
|[CA2242](../code-quality/ca2242.md)|Testujte správně NaN|
