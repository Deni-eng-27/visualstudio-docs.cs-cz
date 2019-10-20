---
title: Služby Windows Communication Foundation a služby WCF Data Services
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
helpviewer_keywords:
- services, WCF Data
- WCF services, binding to
- WCF services, asynchronous service methods
- service references [Visual Studio]
- WCF Data Services
- asynchronous calls
- service references [Visual Studio], type sharing
- endpoints [WCF]
- asynchronous service methods
- service references [Visual Studio] endpoints
- WCF services, type sharing
- Windows Communication Foundation, in Visual Studio
- services, WCF
- WCF service, Visual Studio
- data services, WCF
- services, in Visual Studio
- data binding [Visual Studio], WCF
- service endpoints [Visual Studio]
- service references [Visual Studio], asynchronous calls
- services, Windows Communication Foundation
- type sharing in WCF services
- WCF services, endpoints
- service method, called asynchronously[Visual Studio]
ms.assetid: d56f12cb-e139-4fec-b3e4-488383356642
caps.latest.revision: 29
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 49c2dc46a3e78c5823e569aec80a3166c6e30c04
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72657819"
---
# <a name="windows-communication-foundation-services-and-wcf-data-services-in-visual-studio"></a>Služby Windows Communication Foundation a služby WCF Data Services v sadě Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio poskytuje nástroje pro práci s Windows Communication Foundation (WCF) a [!INCLUDE[ssAstoria](../includes/ssastoria-md.md)] technologie Microsoftu pro vytváření distribuovaných aplikací. V tomto tématu najdete Úvod ke službám z [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] perspektivy. Úplnou dokumentaci najdete v tématu [WCF Data Services 4,5](https://msdn.microsoft.com/library/73d2bec3-7c92-4110-b905-11bb0462357a).

## <a name="what-is-wcf"></a>Co je WCF?
 [!INCLUDE[vsindigo](../includes/vsindigo-md.md)] je sjednocený rámec pro vytváření zabezpečených, spolehlivých, transakčních a interoperabilních distribuovaných aplikací. Nahrazuje starší technologie pro komunikaci mezi procesy, jako jsou webové služby na ASMX, Vzdálená komunikace .NET, podnikové služby (DCOM) a služba MSMQ. WCF přináší funkce všech těchto technologií v rámci jednotného programovacího modelu. To zjednodušuje prostředí vývoje distribuovaných aplikací.

#### <a name="what-are-wcf-data-services"></a>Co jsou WCF Data Services
 [!INCLUDE[ssAstoria](../includes/ssastoria-md.md)] je implementace standardu protokolu OData (Open data).  WCF Data Services umožňuje vystavit tabulková data jako sadu rozhraní REST API, což vám umožní vracet data pomocí standardních příkazů HTTP, jako je GET, POST, PUT nebo DELETE. Na straně serveru WCF Data Services pro vytváření nových služeb OData nahrazuje [webový rozhraní API ASP.NET](http://www.asp.net/web-api) . Klientská knihovna WCF Data Services je nadále vhodnou volbou pro využívání služeb OData v aplikaci .NET ze sady Visual Studio (**projekt &#124; přidat odkaz na službu**). Další informace najdete v tématu [WCF Data Services 4,5](http://go.microsoft.com/fwlink/?LinkID=119952).

### <a name="wcf-programming-model"></a>Programovací model WCF
 Programovací model WCF je založen na komunikaci mezi dvěma entitami: službou WCF a klientem WCF. Programovací model je zapouzdřený v oboru názvů <xref:System.ServiceModel> v [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].

#### <a name="wcf-service"></a>Služba WCF
 Služba WCF je založena na rozhraní, které definuje kontrakt mezi službou a klientem. Je označen atributem <xref:System.ServiceModel.ServiceContractAttribute>, jak je znázorněno v následujícím kódu:

 [!code-csharp[WCFWalkthrough#6](../snippets/csharp/VS_Snippets_VBCSharp/wcfwalkthrough/cs/iservice1.cs#6)]
 [!code-vb[WCFWalkthrough#6](../snippets/visualbasic/VS_Snippets_VBCSharp/wcfwalkthrough/vb/iservice1.vb#6)]

 [!code-csharp[WCFWalkthrough#1](../snippets/csharp/VS_Snippets_VBCSharp/wcfwalkthrough/cs/iservice1.cs#1)]
 [!code-vb[WCFWalkthrough#1](../snippets/visualbasic/VS_Snippets_VBCSharp/wcfwalkthrough/vb/iservice1.vb#1)]

 Můžete definovat funkce nebo metody, které jsou zpřístupněny službou WCF jejich označením pomocí atributu <xref:System.ServiceModel.OperationContractAttribute>. Kromě toho můžete vystavit Serializovaná data tak, že označíte složený typ s atributem <xref:System.Runtime.Serialization.DataContractAttribute>. Tato možnost povolí datovou vazbu v klientovi.

 Po definování rozhraní a jeho metod jsou zapouzdřeny ve třídě, která implementuje rozhraní. Jedna třída služby WCF může implementovat několik kontraktů služeb.

 Služba WCF je vystavená pro spotřebu prostřednictvím toho, co je známé jako *koncový bod*. Koncový bod poskytuje jediný způsob, jak komunikovat se službou. k této službě nemůžete přistupovat přes přímý odkaz, stejně jako u jiných tříd.

 Koncový bod se skládá z adresy, vazby a kontraktu. Adresa určuje, kde se služba nachází; může to být adresa URL, adresa FTP nebo síťová nebo místní cesta. Vazba definuje způsob, jakým komunikujete se službou. Vazby WCF poskytují univerzální model pro určení protokolu, jako je HTTP nebo FTP, mechanismu zabezpečení, jako je například ověřování systému Windows nebo uživatelská jména a hesla, a mnoho dalšího. Kontrakt zahrnuje operace, které jsou zpřístupněny třídou služby WCF.

 Pro jednu službu WCF může být vystaveno více koncových bodů. Díky tomu můžou Různí klienti komunikovat se stejnou službou různými způsoby. Například bankovní služba může poskytovat jeden koncový bod pro zaměstnance a druhý pro externí zákazníky, přičemž každý z nich používá jinou adresu, vazbu nebo kontrakt.

#### <a name="wcf-client"></a>Klient WCF
 Klient WCF se skládá z *proxy serveru* , který umožňuje aplikaci komunikovat se službou WCF, a koncovým bodem, který odpovídá koncovému bodu definovanému pro službu. Proxy je vygenerován na straně klienta v souboru App. config a obsahuje informace o typech a metodách, které jsou zpřístupněny službou. U služeb, které zveřejňují více koncových bodů, může klient vybrat ten, který nejlépe vyhovuje jeho potřebám, například pro komunikaci přes protokol HTTP a použití ověřování systému Windows.

 Po vytvoření klienta WCF odkazujete na službu v kódu stejným způsobem jako jakýkoliv jiný objekt. Například pro volání výše uvedené metody `GetData` byste měli napsat kód, který se podobá následujícímu:

 [!code-csharp[WCFWalkthrough#3](../snippets/csharp/VS_Snippets_VBCSharp/wcfwalkthrough/cs/form1.cs#3)]
 [!code-vb[WCFWalkthrough#3](../snippets/visualbasic/VS_Snippets_VBCSharp/wcfwalkthrough/vb/form1.vb#3)]

## <a name="wcf-tools-in-visual-studio"></a>Nástroje WCF v aplikaci Visual Studio
 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] poskytuje nástroje, které vám pomůžou vytvořit služby WCF i klienty WCF. Návod, který demonstruje nástroje, naleznete [v tématu Návod: Vytvoření jednoduché služby WCF v model Windows Forms](../data-tools/walkthrough-creating-a-simple-wcf-service-in-windows-forms.md).

### <a name="creating-and-testing-wcf-services"></a>Vytváření a testování služeb WCF
 Můžete použít šablony WCF [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] jako základ k rychlému vytvoření vlastní služby. Pak můžete použít automatické hostování služby WCF a testovacího klienta WCF pro ladění a testování služby. Tyto nástroje společně poskytují rychlý a pohodlný cyklus ladění a testování a odstraňují požadavek na zápis do modelu hostování v rané fázi.

#### <a name="wcf-templates"></a>Šablony WCF
 Šablony [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] WCF poskytují základní strukturu tříd pro vývoj služeb. V dialogovém okně **Přidat nový projekt** jsou k dispozici několik šablon WCF. Patří mezi ně projekty knihovny služby WCF, weby služby WCF a šablony položek služby WCF.

 Když vyberete šablonu, přidají se soubory pro kontrakt služby, implementaci služby a konfiguraci služby. Všechny nezbytné atributy jsou již přidány, vytváření jednoduchého typu "Hello World" služby a nemusíte psát žádný kód. Budete samozřejmě chtít přidat kód pro poskytování funkcí a metod pro vaši skutečnou světovou službu, ale šablony poskytují základní základ.

 Další informace o šablonách WCF najdete v tématu [šablony pro WCF sady Visual Studio](https://msdn.microsoft.com/library/6a608575-3535-4190-89da-911e24c8374f).

#### <a name="wcf-service-host"></a>Hostitel služby WCF
 Při spuštění ladicího programu [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] (stisknutím klávesy F5) pro projekt služby WCF je hostitelský nástroj služby WCF automaticky spuštěn pro místní hostování služby. Hostitel služby WCF vypíše služby v projektu služby WCF, načte konfiguraci projektu a vytvoří instanci hostitele pro každou službu, kterou najde.

 Pomocí hostitele služby WCF můžete testovat službu WCF bez psaní dalšího kódu nebo potvrzení konkrétního hostitele během vývoje.

 Další informace o hostiteli služby WCF najdete v tématu [Hostitel služby WCF (WcfSvcHost. exe)](https://msdn.microsoft.com/library/8643a63d-a357-4c39-bd6c-cdfdf71e370e).

#### <a name="wcf-test-client"></a>Testovací klient WCF
 Nástroj testovacího klienta WCF umožňuje zadat parametry testu, odeslat tento vstup do služby WCF a zobrazit odpověď, kterou služba odesílá zpět. Nabízí praktické prostředí pro testování služeb při kombinaci s hostitelem služby WCF. Tento nástroj najdete ve složce \Common7\IDE, která je pro Visual Studio 2015 nainstalovaná na jednotce C: **C:\Program Files (x86) \Microsoft Visual Studio 14.0 \ Common7\IDE \\** .

 Když stisknete klávesu F5 k ladění projektu služby WCF, otevře se klient testu WCF a zobrazí seznam koncových bodů služby, které jsou definovány v konfiguračním souboru. Můžete testovat parametry a spustit službu a opakováním tohoto procesu průběžně testovat a ověřovat vaši službu.

 Další informace o testovacím klientovi WCF naleznete v tématu [klient testu WCF (WcfTestClient. exe)](https://msdn.microsoft.com/library/d4302855-677f-4640-aa90-c5d785d72fb7).

### <a name="accessing-wcf-services-in-visual-studio"></a>Přístup ke službám WCF v aplikaci Visual Studio
 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] zjednodušuje úlohu vytváření klientů WCF, automatické generování proxy serveru a koncového bodu pro služby, které přidáte pomocí dialogového okna **Přidat odkaz na službu** . Do souboru App. config se přidají všechny potřebné informace o konfiguraci. Ve většině případů je vše, co musíte udělat, vytvořit instanci služby, aby ji bylo možné použít.

 Dialogové okno **Přidat odkaz na službu** umožňuje zadat adresu služby nebo vyhledat službu, která je definována ve vašem řešení. Dialogové okno vrátí seznam služeb a operací poskytovaných těmito službami. Umožňuje také definovat obor názvů, pomocí kterého budete odkazovat na služby v kódu.

 Dialogové okno **konfigurace odkazů na službu** umožňuje přizpůsobit konfiguraci služby. Můžete změnit adresu pro službu, zadat úroveň přístupu, asynchronní chování a typy kontraktů zpráv a nakonfigurovat opakované použití typu.

## <a name="how-to-select-a-service-endpoint"></a>Postupy: výběr koncového bodu služby
 Některé služby Windows Communication Foundation (WCF) zpřístupňují několik koncových bodů, prostřednictvím kterých klient může komunikovat se službou. Služba může například vystavovat jeden koncový bod, který používá vazbu HTTP a uživatelské jméno/heslo a druhý koncový bod, který používá ověřování pomocí protokolu FTP a systému Windows. První koncový bod můžou použít aplikace přistupující k této službě mimo bránu firewall, zatímco druhá se může použít na intranetu.

 V takovém případě můžete zadat `endpointConfigurationName` jako parametr do konstruktoru pro odkaz na službu.

 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]

#### <a name="to-select-a-service-endpoint"></a>Výběr koncového bodu služby

1. Přidejte odkaz na službu WCF tak, že kliknete pravým tlačítkem myši na uzel projektu v Průzkumník řešení a zvolíte **Přidat odkaz na službu** .

2. V editoru kódu přidejte konstruktor pro odkaz na službu:

    ```vb
    Dim proxy As New ServiceReference.Service1Client(
    ```

    ```csharp
    ServiceReference.Service1Client proxy = new ServiceReference.Service1Client(
    ```

    > [!NOTE]
    > Nahraďte *ServiceReference* oborem názvů pro odkaz na službu a nahraďte *Service1Client* názvem služby.

3. Seznam IntelliSense se zobrazí s přetíženími pro konstruktor. Vyberte přetížení `endpointConfigurationName As String`.

4. Po přetížení zadejte `=` *ConfigurationName*, kde *ConfigurationName* je název koncového bodu, který chcete použít.

    > [!NOTE]
    > Pokud neznáte názvy dostupných koncových bodů, najdete je v souboru App. config.

#### <a name="to-find-the-available-endpoints-for-a-wcf-service"></a>Vyhledání dostupných koncových bodů pro službu WCF

1. V **Průzkumník řešení**klikněte pravým tlačítkem myši na soubor App. config pro projekt, který obsahuje odkaz na službu, a pak klikněte na tlačítko **otevřít**. Soubor se zobrazí v editoru kódu.

2. V souboru vyhledejte značku `<Client>`.

3. Vyhledejte pod značkou `<Client>` značku, která začíná na `<Endpoint>`.

     Pokud odkaz na službu poskytuje více koncových bodů, bude obsahovat dvě nebo více značek `<Endpoint`.

4. Uvnitř značky `<EndPoint>` naleznete parametr `"` `name="`*SomeService* (kde *SomeService* představuje název koncového bodu). Toto je název koncového bodu, který lze předat `endpointConfigurationName As String` přetížení konstruktoru pro odkaz na službu.

## <a name="how-to-call-a-service-method-asynchronously"></a>Postupy: asynchronní volání metody služby
 Většina metod ve službě Windows Communication Foundation (WCF) se může volat buď synchronně, nebo asynchronně. Asynchronní volání metody umožňuje, aby vaše aplikace pokračovala v práci, zatímco metoda je volána, když funguje přes pomalé připojení.

 Ve výchozím nastavení, když je přidán odkaz na službu do projektu, je nakonfigurován tak, aby volala metody synchronně. Chování můžete změnit na asynchronní volání metod změnou nastavení v dialogovém okně **Konfigurovat odkaz na službu** .

> [!NOTE]
> Tato možnost je nastavena na základě jednotlivých služeb. Pokud je jedna metoda pro službu volána asynchronně, všechny metody musí být volány asynchronně.

 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]

#### <a name="to-call-a-service-method-asynchronously"></a>Postup asynchronního volání metody služby

1. V **Průzkumník řešení**vyberte odkaz na službu.

2. V nabídce **projekt** klikněte na položku **Konfigurovat odkaz na službu**.

3. V dialogovém okně **Konfigurovat odkaz na službu** vyberte zaškrtávací políčko **Generovat asynchronní operace** .

## <a name="how-to-bind-data-returned-by-a-service"></a>Postupy: vytvoření vazby dat vrácených službou
 Data vrácená službou Windows Communication Foundation (WCF) můžete navazovat do ovládacího prvku stejně, jako můžete navazovat na ovládací prvek jakýkoliv jiný zdroj dat. Pokud přidáte odkaz na službu WCF, pokud služba obsahuje složené typy, které vracejí data, budou automaticky přidány do okna **zdroje dat** .

#### <a name="to-bind-a-control-to-single-data-field-returned-by-a-wcf-service"></a>Svázání ovládacího prvku s jedním datovým polem vráceným službou WCF

1. V nabídce **data** klikněte na možnost **Zobrazit zdroje dat**. Zobrazí se okno **zdroje dat** .

2. V okně **zdroje dat** rozbalte uzel pro svůj odkaz na službu. Zobrazí se všechny složené typy vrácené službou.

3. Rozbalte uzel pro typ. Zobrazí se datová pole pro daný typ.

4. Vyberte pole a kliknutím na šipku rozevíracího seznamu zobrazte seznam ovládacích prvků, které jsou k dispozici pro datový typ.

5. Klikněte na typ ovládacího prvku, na který chcete vytvořit propojení.

6. Přetáhněte pole na formulář. Ovládací prvek se přidá do formuláře společně s komponentou <xref:System.Windows.Forms.BindingSource> a <xref:System.Windows.Forms.BindingNavigator> komponentou.

7. Opakujte kroky 4 až 6 pro všechna další pole, která chcete vytvořit.

#### <a name="to-bind-a-control-to-composite-type-returned-by-a-wcf-service"></a>Navázání ovládacího prvku na složený typ vrácený službou WCF

1. V nabídce **data** vyberte možnost **Zobrazit zdroje dat**. Zobrazí se okno **zdroje dat** .

2. V okně **zdroje dat** rozbalte uzel pro svůj odkaz na službu. Zobrazí se všechny složené typy vrácené službou.

3. Vyberte uzel pro typ a kliknutím na šipku rozevíracího seznamu zobrazte seznam dostupných možností.

4. Klikněte na tlačítko **DataGridView** a zobrazte tak data v tabulce nebo v **podrobnostech** , aby se zobrazila data v jednotlivých ovládacích prvcích.

5. Přetáhněte uzel do formuláře. Ovládací prvky budou přidány do formuláře společně s komponentou <xref:System.Windows.Forms.BindingSource> a <xref:System.Windows.Forms.BindingNavigator> komponentou.

## <a name="how-to-configure-a-service-to-reuse-existing-types"></a>Postupy: Konfigurace služby pro opětovné použití stávajících typů
 Při přidání odkazu na službu do projektu jsou všechny typy definované ve službě generovány v místním projektu. V mnoha případech to vytvoří duplicitní typy, pokud služba používá společné typy [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] nebo když jsou typy definovány ve sdílené knihovně.

 Chcete-li se tomuto problému vyhnout, jsou typy v odkazovaných sestaveních sdíleny ve výchozím nastavení. Pokud chcete zakázat sdílení typů pro jedno nebo více sestavení, můžete tak učinit v dialogovém okně **konfigurace odkazů na službu** .

#### <a name="to-disable-type-sharing-in-a-single-assembly"></a>Zakázání sdílení typu v jednom sestavení

1. V **Průzkumník řešení**vyberte odkaz na službu.

2. V nabídce **projekt** klikněte na položku **Konfigurovat odkaz na službu**.

3. V dialogovém okně **konfigurovat odkazy na službu** vyberte možnost **znovu použít typy v zadaných odkazovaných sestaveních**.

4. Zaškrtněte políčko pro každé sestavení, ve kterém chcete povolit sdílení typů. Chcete-li zakázat sdílení typů pro sestavení, ponechejte políčko nezaškrtnuté.

#### <a name="to-disable-type-sharing-in-all-assemblies"></a>Zakázání sdílení typů ve všech sestaveních

1. V **Průzkumník řešení**vyberte odkaz na službu.

2. V nabídce **projekt** klikněte na položku **Konfigurovat odkaz na službu**.

3. V dialogovém okně **konfigurovat odkazy na službu** zrušte zaškrtnutí políčka **znovu použít typy v odkazovaných sestaveních** .

## <a name="related-topics"></a>Související témata

|Název|Popis|
|-----------|-----------------|
|[Návod: Vytvoření jednoduché služby WCF v modelu Windows Forms](../data-tools/walkthrough-creating-a-simple-wcf-service-in-windows-forms.md)|Poskytuje podrobné ukázky vytváření a používání služeb WCF v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].|
|[Návod: Vytvoření datové služby WCF pomocí WPF a Entity Framework](../data-tools/walkthrough-creating-a-wcf-data-service-with-wpf-and-entity-framework.md)|Poskytuje podrobné informace o tom, jak vytvořit a používat [!INCLUDE[ssAstoria](../includes/ssastoria-md.md)] v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].|
|[Používání vývojářských nástrojů WCF](https://msdn.microsoft.com/library/054adb87-c244-4d5a-83d1-0b2b44bd454b)|Popisuje, jak vytvářet a testovat služby WCF v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].|
|[Postupy: Přidání, aktualizace nebo odebrání odkazu na službu](https://msdn.microsoft.com/library/cacc14bd-4455-4a44-be78-d2ac16113dd9)|Popisuje, jak přidat, aktualizovat nebo odebrat služby WCF z projektu.|
|[Postupy: Přidání, aktualizace nebo odebrání odkazu na službu WCF Data Service](../data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference.md)|Popisuje, jak odkazovat a používat [!INCLUDE[ssAstoria](../includes/ssastoria-md.md)] v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].|
|[Řešení potíží s odkazy na služby](../data-tools/troubleshooting-service-references.md)|Představuje některé běžné chyby, ke kterým může dojít s odkazy na služby a jak je zabránit.|
|[Ladění služeb WCF](../debugger/debugging-wcf-services.md)|Popisuje běžné problémy s laděním a techniky, se kterými se můžete setkat při ladění služeb WCF.|
|[Přehled služby Windows Communication Foundation Authentication Service](https://msdn.microsoft.com/library/6e121a28-89e8-4974-88a8-70aaa6a7d52b)|Popisuje, jak pomocí WCF poskytnout službu role pro web.|
|[Návod: Vytvoření vícevrstvé datové aplikace](../data-tools/walkthrough-creating-an-n-tier-data-application.md)|Poskytuje podrobné pokyny pro vytvoření typové datové sady a oddělení kódu TableAdapter a datové sady do více projektů.|
|[Dialogové okno Nastavit odkaz na službu](../data-tools/configure-service-reference-dialog-box.md)|Popisuje prvky uživatelského rozhraní dialogového okna **Konfigurovat odkaz na službu** .|

## <a name="reference"></a>Odkaz
 <xref:System.ServiceModel>

 <xref:System.Data.Services>

## <a name="see-also"></a>Viz také
 [Visual Studio Data Tools for .NET](../data-tools/visual-studio-data-tools-for-dotnet.md)
