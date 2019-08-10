---
title: Uzly návrháře shaderů
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: f5192fbd-c78f-40a8-a4d4-443209610268
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 775d447b3e513e15eeafb1bfd90c54e3ffa70770
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68925758"
---
# <a name="shader-designer-nodes"></a>Uzly návrháře shaderu
Články v této části dokumentace obsahují informace o různých uzlech návrháře shaderů, které lze použít k vytvoření grafických efektů.

## <a name="nodes-and-node-types"></a>Uzly a typy uzlů
Návrhář shaderu představuje vizuální efekty jako graf. Tyto grafy jsou sestaveny z uzlů, které jsou výslovně vybrány a propojeny způsobem, aby dosáhly zamýšleného efektu. Každý uzel představuje buď část informací, nebo matematickou funkci a spojení mezi nimi představují způsob, jakým informace tok sestaví a vytváří výsledek. Návrhář shaderu poskytuje šest různých typů uzlů – filtry, uzly textury, parametry, konstanty, uzly nástrojů a matematické uzly – a do každého typu patří několik jednotlivých uzlů. Tyto uzly a typy uzlů jsou popsány v dalších článcích v této části. Další informace najdete v odkazech na konci tohoto dokumentu.

## <a name="node-structure"></a>Struktura uzlu
Všechny uzly se skládají z kombinace běžných prvků. Každý uzel má alespoň jeden výstupní terminál na pravé straně (s výjimkou konečného uzlu Color, který představuje výstup shaderu). Uzly, které reprezentují výpočty nebo vzorkovače s texturou, mají vstupní terminály na levé straně, ale uzly reprezentující informace nemají žádné vstupní terminály. Výstupní terminály jsou připojeny ke vstupním terminálům, aby bylo možné přesouvat informace z jednoho uzlu do druhého.

### <a name="promotion-of-inputs"></a>Propagace vstupů
Vzhledem k tomu, že návrhář shaderu musí nakonec vytvořit zdrojový kód HLSL, aby se efekt mohl použít v hře nebo aplikaci, podléhají uzly návrháře shaderů pravidla propagace typu, která používá HLSL. Vzhledem k tomu, že grafický hardware pracuje hlavně na hodnotách s plovoucí desetinnou čárkou, typ propagace `int` mezi různými typy – `float` například `double`od do `float`nebo od do – je neobvyklá. Jelikož hardware grafiky používá stejnou operaci na více částech informací najednou, může dojít k jinému druhu propagace, ve kterém se kratší počet vstupů prodlouží, aby odpovídaly velikosti nejdelšího vstupu. Způsob prodloužení závisí na typu vstupu a také na samotné operaci:

- **Pokud je menší typ skalární hodnota, pak:**

     Hodnota skalárního typu je replikována do vektoru, který má stejnou velikost jako větší vstup. Například skalární vstup 5,0 se zobrazí vektor (5,0, 5,0, 5,0), pokud je největší vstup operace vektorem tří prvků bez ohledu na to, co je operace.

- **Pokud je menší typ vektor a operace je multiplikativní (\*,/,% a tak dále), pak:**

     Hodnota vektoru je zkopírována do počátečních prvků vektoru, který se rovná velikosti většímu vstupu, a koncové prvky jsou nastaveny na 1,0. Například vektorové vstupy (5,0, 5,0) se stávají vektorem (5,0, 5,0, 1,0, 1,0), když se vynásobí vektorem čtyř elementů. Tím se zachová třetí a čtvrtá prvky výstupu pomocí multiplikativní identity, 1,0.

- **Pokud je menší typ vektor a operace je aditivní (+,-a tak dále), pak:**

     Hodnota vektoru je zkopírována do počátečních prvků vektoru, který se rovná velikosti většímu vstupu, a koncové prvky jsou nastaveny na 0,0. Například vektorové vstupy (5,0, 5,0) se stávají vektorem (5,0, 5,0, 0,0, 0,0) při přidání do vektoru se čtyřmi prvky. Tím se zachová třetí a čtvrtá prvky výstupu pomocí doplňkové identity, 0,0.

## <a name="related-topics"></a>Související témata

|Název|Popis|
|-----------|-----------------|
|[Uzly konstanty](../designers/constant-nodes.md)|Popisuje uzly, které lze použít k reprezentaci hodnot literálů a interpolované informace o stavu vrcholu ve výpočtech shaderu. Vzhledem k tomu, že stav vrcholu je interpolované – a proto se pro každý pixel liší, každá instance pixel-shader obdrží jinou verzi konstanty.|
|[Uzly parametru](../designers/parameter-nodes.md)|Popisuje uzly, které lze použít k reprezentaci pozice kamery, vlastností materiálu, parametrů osvětlení, času a dalších informací o stavu aplikace ve výpočtech shaderu.|
|[Uzly textury](../designers/texture-nodes.md)|Popisuje uzly, které lze použít k vzorkování různých typů textury a geometrií a k vytváření nebo transformaci souřadnic textury běžnými způsoby.|
|[Matematické uzly](../designers/math-nodes.md)|Popisuje uzly, které lze použít k provádění algebraických, logiky, trigonometrickéch a dalších matematických operací, které jsou mapovány přímo na pokyny HLSL.|
|[Uzly nástroje](../designers/utility-nodes.md)|Popisuje uzly, které lze použít k provádění běžných výpočtů osvětlení a dalších běžných operací, které nejsou mapovány přímo na HLSL pokyny.|
|[Uzly filtru](../designers/filter-nodes.md)|Popisuje uzly, které lze použít k filtrování textur a filtrování barev.|
