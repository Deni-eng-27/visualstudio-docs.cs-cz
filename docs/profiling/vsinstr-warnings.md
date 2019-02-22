---
title: Upozornění VSInstr | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- instrumentation, VSInstr tool
- warnings
- VSInstr tool
- warnings, VSInstr tool
- performance tools, VSInstr tool
ms.assetid: 47512bc9-a8e9-4628-883a-d9888edab786
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9b03b1350b4125262bedfd7fa5284c13d6d38a2e
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56615254"
---
# <a name="vsinstr-warnings"></a>Upozornění VSInstr
Následující tabulka obsahuje seznam upozornění vydané *VSInstr.exe* nástroj. Možnost NOWARN spolu s čísla upozornění můžete potlačit upozornění nezobrazovalo.

|Číslo upozornění|Popis|
|--------------------|-----------------|
|**VSP1026**|Pokrytí není podporované u knihoven, které neodkazují na MSCorLib. To je často případ přenosných knihoven.<br /><br />[/EnableCodeCoverage](/visualstudio/test/vstest-console-options) možnost příkazového řádku je vyžadována pro .NET Core.|
|**VSP2000**|Vnitřní chyba Nelze získat název souboru modulu tohoto spustitelného souboru.|
|**VSP2001**|\<název sestavení > je sestavení se silným názvem. Musí být znovu podepsat předtím, než mohou být provedeny.<br /><br /> K tomuto upozornění dochází, když je instrumentováno podepsané sestavení. Můžete použít *sn.exe* nástroj pro binární soubor znovu podepsat nebo dočasné vypnutí požadavek silným názvem. Další informace najdete v tématu [Sn.exe (nástroj pro silný název)](/dotnet/framework/tools/sn-exe-strong-name-tool).|
|**VSP2002**|Nelze nalézt funkci \<funcname > v souboru \<název souboru ><br /><br /> K tomuto upozornění dochází, pokud funkci nelze umístit do zadaného souboru.|
|**VSP2003**|Nelze nalézt žádné křížové skoky na funkci \<funcname > v souboru \<název souboru >.<br /><br /> K tomuto upozornění dochází Pokud nemůže nástroj VSInstr nezruší se tím přejde mezi. Optimalizace kódu se používají křížových skoků.|
|**VSP2004**|Funkce \<funcname > byla vyloučena prostřednictvím přepínače příkazového řádku vyloučení, ale byla požadována, protože obsahovala křížový skok.<br /><br /> K tomuto upozornění dochází, pokud byl vyloučen, pomocí možnosti vyloučit funkce, ale je potřeba během procesu instrumentace. Profiler automaticky zahrne požadované funkce.|
|**VSP2005**|Vnitřní chyba instrumentace \<text chyby ><br /><br /> Pokud nelze provést instrumentaci se objeví toto upozornění. Přečtěte si text chyby k určení, zda je možné odstranit.|
|**VSP2006**|Nelze najít soubor PDB pro \<name ><br /><br /> K tomuto upozornění dochází, pokud neexistuje na cestě pro vyhledávání nebo binárním souboru neodpovídá souboru PDB.|
|**VSP2007**|\<Název souboru > neobsahuje žádný instrumentovatelný kód.<br /><br /> Pokud funkce v binárním souboru všechny vyloučené nebo pokud zadaný soubor obsahuje pouze prostředky se objeví toto upozornění.|
|**VSP2008**|Nepovedlo se získat atributy zabezpečení z \<název >. Kód chyby: \<kód ><br /><br /> K tomuto upozornění dochází, pokud uživatel nemá oprávnění READ_DAC. Během procesu instrumentace profileru snaží se zachovat původní seznam DACL pro binární soubor. Protože nové binární soubor nahradí původní binární soubor, musí být DACL z původní binární soubor zkopírovat a použít pro nové binární soubor. To může selhat, pokud uživatel nemá přístup READ_DAC na původní binární soubor.|
|**VSP2009**|Nelze nastavit atributy zabezpečení na \<název >. Kód chyby: \<číslo chyby ><br /><br /> K tomuto upozornění dochází, pokud uživatel nemá oprávnění WRITE_DAC. Během procesu instrumentace profileru snaží se zachovat původní seznam DACL pro binární soubor. Protože nové binární soubor nahradí původní binární soubor, musí být DACL z původní binární soubor zkopírovat a použít pro nové binární soubor. To může selhat, pokud uživatel nemá přístup WRITE_DAC na nové binární soubor.|
|**VSP2010**|Žádné funkce jsou speciálně vybrané pro instrumentaci z důvodu - ZAHRNUJÍ možnosti/vyloučení|
|**VSP2011**|Zahrnutí a vyloučení funcspec \<name > neodpovídá žádné funkce|
|**VSP2012**|Na obrázku neobsahuje žádný kód, který může být instrumentováno pro pokrytí kódu.<br /><br /> Profiler není instrumentace následující typ kódu:<br /><br /> -Statické funkce CRT<br />-Spravovaných metod s NonUserCodeAttribute<br />-Spravovaných metod DebuggerHiddenAttribute – atribut<br />– MASM bloky<br /><br /> Toto upozornění je generováno, pokud po tomto filtrování, neexistuje žádný kód vlevo.|
|**VSP2013**|Instrumentace tohoto obrazu vyžaduje ji spustit jako 32bitový proces. Hlavičkové příznaky CLR byly aktualizovány tak, aby odrážely to.<br /><br /> Profiler upravuje binárního souboru, takže 64bitové operační systémy můžete otevřít v emulátoru WOW64 32bitový proces. Pro knihovny (DLL) to může selhat, pokud jsou načteny v existující 64bitového procesu. Toto upozornění upozorní uživatele závislosti.|
|**VSP2014**|Výsledný instrumentovaný obraz se zdá být neplatný a nemusí být možné spustit.<br /><br /> Tato zpráva se zobrazí při posledním instrumentované sestavení má neplatná PE hlavička.|

## <a name="see-also"></a>Viz také:
- [VSInstr](../profiling/vsinstr.md)