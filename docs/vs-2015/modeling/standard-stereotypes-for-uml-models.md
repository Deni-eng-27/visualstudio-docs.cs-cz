---
title: Standardní stereotypy pro modely UML | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- UML, stereotypes
- UML diagrams, stereotypes
ms.assetid: 8a8c2321-1cae-4ba8-bb9e-23495c3404d8
caps.latest.revision: 22
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: a16c68b3b14be57fb0a6a45c740e5420a82c2ddf
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72661052"
---
# <a name="standard-stereotypes-for-uml-models"></a>Standardní stereotypy pro modely UML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete přidat stereotypy k prvkům modelu UML a poskytnout tak další informace pro čtenáře nebo pro zpracování počítačů. Stereotypy jsou definovány v profilech a jednotlivé profily poskytují sadu stereotypů. V aplikaci Visual Studio je k dispozici několik profilů. Můžete také definovat vlastní profily, které mohou obsahovat vlastní stereotypy. Další informace najdete v tématu [Definování profilu pro rozšiřování UML](../modeling/define-a-profile-to-extend-uml.md).

 Chcete-li zjistit, které verze aplikace Visual Studio tuto funkci podporují, přečtěte si téma [podpora verzí pro nástroje pro architekturu a modelování](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

## <a name="the-standard-profiles"></a>Standardní profily
 Následující profily jsou k dispozici v podporované edici sady Visual Studio, jakmile ji nainstalujete.

|Profilu|Účel|
|-------------|-------------|
|[Standard UML – profil L2](#L2)|Standardní sada stereotypů, které lze použít k přidání dalších informací o prvku nebo vztahu.|
|[Standardní profil UML L3](#L3)|Standardní sada stereotypů, které lze použít k přidání dalších informací o prvku nebo vztahu.|
|[C#Profilu](#NetProfile)|Pokud zamýšlíte, aby třída nebo jiný prvek v modelu UML představovaly kód programu, můžete to určit použitím jednoho ze stereotypů z C# profilu.<br /><br /> Tyto stereotypy také přidávají vlastnosti prvkům modelu.|

 Při vytváření nového modelu UML jsou profily standardu UML a L3 propojeny s modelem, pokud odkazy neodeberete.

 Chcete-li použít stereotypy v některém z těchto profilů, je nutné nejprve propojit profil s balíčkem nebo modelem, který obsahuje prvky, pro které chcete použít.

#### <a name="to-link-a-profile-to-a-model-or-a-package"></a>Připojení profilu k modelu nebo balíčku

1. Otevřete **Průzkumníka modelů UML**. V nabídce **Architektura** přejděte na **okna**a potom klikněte na **Průzkumník modelů UML**.

2. Vyhledejte balíček nebo model, který obsahuje všechny prvky, pro které chcete použít stereotypy v profilu.

3. Klikněte pravým tlačítkem na balíček nebo model a pak klikněte na **vlastnosti**.

4. V okně **vlastnosti** nastavte vlastnost **Profiles** na požadované profily.

#### <a name="to-remove-the-link-between-a-profile-and-a-model-or-package"></a>Odebrání propojení mezi profilem a modelem nebo balíčkem

1. V Průzkumníku modelů UML klikněte pravým tlačítkem na model nebo balíček a pak klikněte na **vlastnosti**.

2. V okno Vlastnosti nastavte vlastnost **Profiles** na prázdnou.

    > [!NOTE]
    > Profil můžete odpojit pouze v případě, že žádný z prvků v modelu nebo balíčku nepoužívá stereotypy daného profilu.

#### <a name="to-apply-a-stereotype-to-a-model-element"></a>Použití stereotypu na prvek modelu

1. Klikněte pravým tlačítkem myši na prvek modelu buď v diagramu, nebo v **Průzkumníku modelů UML**a pak klikněte na **vlastnosti**.

2. Klikněte na vlastnost **Stereotypy** a vyberte stereotypy, které chcete použít.

     Vybrané stereotypy se zobrazují v rámci «dvojité šipky» v elementu modelu pro většinu druhů elementu.

    > [!NOTE]
    > Pokud nemůžete zobrazit vlastnost **Stereotypy** , nebo pokud se stereotyp, který chcete, nezobrazuje, ověřte, zda je prvek modelu uvnitř balíčku nebo modelu, ke kterému byl příslušný profil propojen.

3. Některé Stereotypy umožňují nastavit hodnoty dalších vlastností prvku modelu. Chcete-li zobrazit tyto vlastnosti, rozbalte vlastnost **Stereotypy** .

### <a name="L2"></a>Standard UML – profil L2
 Následující Stereotypy lze použít ke specializaci významu prvků modelu UML, pokud odkaz na profil nebyl odebrán z modelu.

 Přesný význam těchto stereotypů je určen vašimi místními konvencemi a všemi nástroji, které můžete použít ke zpracování modelu.

|Stereotyp|Platí pro|Význam|
|----------------|----------------|-------------|
|pomoc|Třída|Třída, která podporuje jinou třídu, obvykle implementací další logiky. Druhá třída může mít stereotyp «Focus».|
|– volání|Závislosti|Třída klienta volá operace dodavatele.|
|vytvoření|Závislosti|Třída klienta vytváří instance dodavatele.|
|vytvoření|Zpráva|Odesílatel vytvoří příjemce.|
|vytvoření|Operace|Tato operace je konstruktorem.|
|dědí|Závislosti|Prvek klienta je zcela nebo částečně vypočítán od dodavatele.|
|způsobit|Operace|Operace zničí svou instanci.|
|dokument|Artefaktu|«Soubor», který není zdrojem nebo spustitelným souborem.|
|entita|Součást|Komponenta představuje obchodní koncept.|
|spouštěcí|Artefaktu|Spustitelný soubor».|
|– soubor|Artefaktu|Fyzický soubor.|
|fokus|Třída|Třída definující základní obchodní logiku, kterou podporuje několik "pomocných tříd»".|
|rozhraní|Balíček|Tento balíček definuje opakovaně použitelný návrhový vzor.|
|uskutečnit|Součást|Implementace «specifikace».|
|implementationClass|Třída|Třída popisuje implementaci a každá instance modulu runtime má jednu pevnou implementační třídu. Kontrast se «Type».|
|vytvořit instanci|Závislosti|Klient vytvoří instance dodavatele.|
|knihovna|Artefaktu|Knihovna «soubor».|
|metaclass|Třída|Instance této třídy jsou také třídy.|
|modelLibrary|Balíček|Obsahuje prvky modelu, které mají být použity pro import balíčků. Obvykle se definuje jako součást profilu a automaticky se naimportuje pomocí aplikačního profilu.|
|zpracování|Součást|Komponenta založená na transakcích nebo ta, která provádí vlákno.|
|realizace|Třída, rozhraní, součást|Popisuje implementaci.|
|zužte|Závislosti|Třída klienta, komponenta nebo balíček poskytuje další informace o specifikaci nebo návrhu než dodavatel.|
|zodpovědní|Závislosti|Komentář na konci závislosti určuje odpovědnost klientské třídy nebo komponenty.|
|skript|Artefaktu|Interpretované «soubor».|
|posílají|Závislosti|Zdrojová operace pošle cílový signál.|
|service|Součást|Bezstavová komponenta.|
|source|Artefaktu|Kompilovatelný «soubor».|
|specifikace|Třída, rozhraní, součást|Definuje chování komponenty nebo objektu bez nutnosti definovat, jak funguje interně.|
|provozuschopn|Součást|Součástí velkého systému. Podsystém v diagramu případu použití je komponenta se stereotypem subsystému.|
|trasování|Závislosti|Element Client je součástí návrhu, který daný dodavatel realizuje. Dva konce této závislosti jsou obvykle v různých modelech. Jeden z těchto modelů je realizace druhé.|
|– typ|Třída|Určuje chování objektu bez informování o tom, jak je implementováno. Objekt je členem typu, pokud odpovídá specifikaci.|
|nástroj|Třída|Kolekce statických funkcí. Třída nemá žádné instance.|

### <a name="L3"></a>Standardní profil UML L3
 Následující Stereotypy lze použít ke specializaci významu prvků modelu UML, pokud se profil neodkazuje z modelu.

 Přesný význam těchto stereotypů je určen vašimi místními konvencemi a všemi nástroji, které můžete použít ke zpracování modelu.

|Stereotyp|Platí pro|Popis|
|----------------|----------------|-----------------|
|buildComponent|Součást|Kolekce prvků, které slouží k definování sestavení.|
|metaModel|Vzorový|Definuje jazyk modelování, jako je například varianta UML nebo jazyk specifický pro doménu.|
|systemModel|Vzorový|Model, který je kolekcí modelů, které se vztahují ke stejnému systému, například specifikace, realizaci a sledování vztahů mezi nimi.|

## <a name="NetProfile"></a>C# Profil
 Stereotypy, které jsou definovány v tomto profilu, vám umožní určit, že prvek modelu je určen pro převod do programového kódu. Jednotlivé stereotypy definují další vlastnosti, které lze nastavit u prvku modelu.

 Aby byly tyto stereotypy k dispozici, propojte model nebo balíček C# s profilem. Pak můžete použít stereotypy pro modelování prvků v daném modelu nebo balíčku.

 Dostupné stereotypy, prvky, na které jsou použity, a další vlastnosti, které jsou k dispozici, jsou shrnuty v následující tabulce.

|Stereotyp|Platí pro|Vlastnosti|
|----------------|----------------|----------------|
|**C#Deník**|Třída UML<br /><br /> Součást|**CLR – atributy**<br /><br /> **Je částečný**<br /><br /> **Je zapečetěný**<br /><br /> **Je statický**<br /><br /> **Je nebezpečné**<br /><br /> **Viditelnost balíčku**|
|**C#nemají**|Třída UML<br /><br /> Součást|**CLR – atributy**<br /><br /> **Je částečný**<br /><br /> **Je nebezpečné**<br /><br /> **Viditelnost balíčku**|
|**C#globální členové**|Třída UML<br /><br /> Součást|**CLR – atributy**|
|**C#Prostředí**|Rozhraní UML|**CLR – atributy**<br /><br /> **Je částečný**<br /><br /> **Viditelnost balíčku**|
|**C#vytváření**|Výčet UML|**ClrAttributes**<br /><br /> **Základní typ**|
|**C#hosting**|Balíček UML|**CLR – atributy**<br /><br /> **Základní název**<br /><br /> **Používání oborů názvů**|

## <a name="see-also"></a>Viz také
 [Přidání stereotypů do prvků modelu UML](../modeling/add-stereotypes-to-uml-model-elements.md) [Přizpůsobení modelu pomocí profilů a stereotypů](../modeling/customize-your-model-with-profiles-and-stereotypes.md) [Definování profilu pro rozšiřování UML](../modeling/define-a-profile-to-extend-uml.md)
