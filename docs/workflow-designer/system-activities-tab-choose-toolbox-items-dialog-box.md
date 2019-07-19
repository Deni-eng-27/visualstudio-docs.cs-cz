---
title: 'Návrhář pracovního postupu: System.Activities, zvolit položky panelu nástrojů'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- VS.CHOOSEITEMS.SYSTEM.ACTIVITIES_COMPONENTS
- VS.CHOOSEITEMS.SYSTEM.ACTIVITIES COMPONENTS
ms.assetid: cef390cd-eeda-42e6-9d2e-18c8325a4f06
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fd25b939519bb1a1cb179ab5bbd4d20b9307f920
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2019
ms.locfileid: "66747758"
---
# <a name="systemactivities-tab-choose-toolbox-items-dialog-box"></a>Karta System.Activities, dialogové okno Zvolit položky nástrojů

Tato karta **zvolit položky nástrojů** dialogové okno zobrazí seznam aktivit Windows Workflow Foundation (WF), šablony a položky, které jsou k dispozici pro vás. Chcete-li zobrazit tento seznam, vyberte **zvolit položky nástrojů** z **nástroje** nabídky nebo kliknutím pravým tlačítkem myši **nástrojů** a vyberete **zvolit položky**zobrazíte **zvolit položky nástrojů** dialogové okno a pak vyberte jeho **System.Activities** kartu. Hned po spuštění obsahuje seznam aktivit pracovního postupu z System.Activities, System.ServiceModel.Activities a System.Activities.Core.Presentation sestavení; ale jenom poskytnuté systémem aktivity zobrazené a přidávají další sestavení zobrazí v **nástrojů** jsou ve výchozím nastavení zaškrtnuto. Naposledy přidané aktivity jsou automaticky zaškrtnuto a zobrazí se v **nástrojů** po kliknutí na **OK** v dialogovém okně. Navíc tyto položky se zobrazí v **nástrojů** pod novou kategorii, která odpovídá na obor názvů, ve které se nachází aktivity či položky nebo šablonu.

> [!WARNING]
> Pokud se pokusíte přidat sestavení, který neobsahuje žádné aktivity pracovního postupu, se zobrazí dialogové okno chyby, který vysvětluje, že sestavení neobsahuje žádné aktivity.

Toto dialogové okno je nezávislý na projekt a proto **System.Activities** kartu nadále zobrazí v samostatných XAML nebo typu projekt pracovního postupu.

Filtrování se provádí na každé kartě a není možné přidat aktivit pracovních postupů prostřednictvím **součásti .NET** kartu. Přidat prostřednictvím **System.Activities** kartě samotný.

Můžete zrušit zaškrtnutí všech položek, které nechcete a podívejte se **nástrojů** z tohoto dialogového okna kartu, nebo Alternativně můžete k tomu použít **odstranit** klikněte pravým tlačítkem na možnost nabídky v **nástrojů**a zrušením odkazu na sestavení nedojde k odstranění položky z **nástrojů**.

Vytvoření instance aktivity, přetahováním myší v Návrháři přidá sestavení, který obsahuje položku do seznamu odkazovaných sestavení automaticky. Také pokud aktivity odkazuje na sestavení C, nepřidá C do seznamu odkazovaných sestavení. Sestavení C musí být v mezipaměti GAC nebo do stejného adresáře jako aktivita B. V případě samostatné sestavení musí být v GAC nebo cest test paměti VS. Teprve pak lze je přetáhnout myší aktivity na plochu návrháře pracovního postupu.

**Panel nástrojů** nastavení se ukládají ve výchozím nastavení jako uživatelské možnosti, proto příště, když otevřete **nástrojů**, zobrazí vaše vlastní seznam aktivit pracovního postupu. Jeden vedlejším účinkem této je, že pokud jste přidali položky konkrétní doménu k **nástrojů** prostřednictvím **zvolit položky nástrojů** dialogovém okně můžete i nadále vidět tyto položky při práci Konzolová aplikace pracovního postupu i. Pokud nechcete zobrazit, odstranit je pomocí místní nabídky nebo zrušte zaškrtnutí políčka je **zvolit položky nástrojů** dialogovému oknu, protože jste si poznamenali dříve.

Sloupce v tomto dialogovém obsahují následující informace:

Name\
Obsahuje seznam aktivit pracovního postupu, které jsou aktuálně registrované na místním počítači.

Namespace\
Zobrazuje hierarchii obor názvů .NET, který definuje strukturu aktivity.

Name sestavení\
Zobrazí název a verze .NET sestavení, který obsahuje aktivitu.

Directory\
Zobrazí umístění sestavení .NET, která obsahuje aktivity pracovního postupu. Je výchozím umístěním pro všechna sestavení do globální mezipaměti sestavení.

Součástí uvedené seřadit, vyberte libovolné záhlaví sloupce.