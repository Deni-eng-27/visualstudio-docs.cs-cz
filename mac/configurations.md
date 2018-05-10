---
title: Principy konfigurací sestavení v sadě Visual Studio pro Mac
description: Tento článek popisuje různé konfigurace sestavení v sadě Visual Studio pro Mac
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.assetid: 78107CFA-9308-4293-A92A-9B552A259E15
ms.openlocfilehash: b0ab3786f9bbb713fdc2b4726b29148c4bcd9f34
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
---
# <a name="understanding-build-configurations"></a>Principy konfigurací sestavení

## <a name="project-build-configurations"></a>Konfigurace sestavení projektu 

Projekty mívají k více konfigurací a přepínání mezi nimi umožňuje různých výstupy v čase vytvoření buildu. Například výstup konfiguraci ladění symboly pro ladění, což ladicí program přeložit názvy funkcí, parametrů nebo proměnné z trasování zásobníku chyb aplikace. Pokud tyto další informace jsou užitečné při vývoji, vede k velikost zvýšeným souboru a není vhodné pro distribuci.

Každá platforma má konkrétní konfigurace pro jeho sestavení. 

## <a name="solution-configurations"></a>Konfigurace řešení

Konfigurace řešení se podobají konfigurace projektu použít k vytvoření vlastní konfigurace pro celý projekt. Pomocí **konfigurace mapování** v části **sestavení > Konfigurace** položky, můžete přiřadit konfigurace cílového pro každou položku řešení, jak je znázorněno na následujícím obrázku:


 ![Možnosti konfigurace mapování](media/projects-and-solutions-image3.png)

Další informace o konfiguracích najdete v tématu [nástroje Configuration Manager](https://www.youtube.com/watch?v=tjSdkqYh5Vg) video od James Montemagno.

## <a name="run-configuration"></a>Spuštění nástroje Konfigurace

V předchozích verzích nástroje Xamarin Studio můžete třeba vybrat možnost nastavte projekt jako **spouštěný projekt**, což je projekt, který je spustit nebo ladit při použití příkazu globální spustit/debug. To se indikován tučné písmo pro název projektu v panelu pro projekt.

V sadě Visual Studio pro Mac, namísto nastavování spouštěný projekt, můžete nastavit _spustit konfigurace_. Spuštění konfigurace jsou uvedeny v rozevíracím seznamu v panelu nástrojů vedle selektor sestavení konfigurace, jak je uvedeno dále:

 ![Spuštění konfigurace rozevíracího seznamu](media/projects-and-solutions-image8.png)

Spuštění konfigurace je sada možností spouštění s názvem a několik konfigurací, které jsou definovány v projektu pro jiné účely. Spuštění konfigurace jsou definovány na úrovni projektu a výchozí automaticky se vytvoří pro každý projekt, spustitelný soubor, i když je možné přidat až potřebné. Některé typy projektů automaticky generovat další spuštění konfigurace. Například může vygenerovat watchOS projekty _konfigurace přehledu a oznámení._ 
 
Konfigurace můžete sdílet s jinými vývojáři (v takovém případě konfigurace bude uložen v souboru .csproj) nebo uchovávají místně (v takovém případě budou uloženy v souboru .uživatel).

### <a name="android-run-configurations"></a>Android spustit konfigurace
 
Spuštění konfigurace pro Android projekty umožňují určit, které aktivity, služby nebo všesměrového vysílání příjemce pro spuštění při spuštění nebo ladění projektu. Můžete předat záměrné doplňující data a nastavte záměrné příznaky mohli otestovat vaše komponenty pro v různých spuštění podmínkách.

Aktivity jinak než `MainLauncher` potřebovat `Exported=true` přidat do atribut aktivity pro ladění na fyzické zařízení nebo definovali záměrné filtry.

## <a name="examples-of-data-that-might-be-included-in-run-configurations"></a>Příklady data, která může být součástí spuštění konfigurace

Následující seznam uvádí některé příklady data, která může být součástí spuštění konfigurace:

* Pravidelné projektové rozhraní .NET
    * Alternativní spuštění aplikace
    * Spustit argumenty
    * Pracovní adresář
    * Proměnné prostředí
    * Možnosti mono runtime (který se má použít, pouze pokud se používá na Mono)
* Projekt pro Android
    * Vstupní bod (aktivity, služby, příjemce)
    * Záměrné argumentů a dat
* projekt pro iOS
    * Režim (normální, načítání na pozadí)
* rozšíření projektu iOS
    * Spuštění aplikace: výchozí nebo vlastní
* WatchKit projektu
    * Režim (přehledu, oznámení)
    * Datová část oznámení
