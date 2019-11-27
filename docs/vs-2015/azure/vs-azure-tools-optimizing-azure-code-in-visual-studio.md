---
title: Optimalizace kódu Azure
description: Zjistěte, o tom, jak Azure kódu pomocí nástroje optimalizace v sadě Visual Studio byl kód, robustní a lepší výkon.
author: ghogen
manager: jillfra
ms.assetid: ed48ee06-e2d2-4322-af22-07200fb16987
ms.topic: conceptual
ms.custom: vs-azure
ms.workload: azure-vs
ms.date: 11/11/2016
ms.author: ghogen
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.openlocfilehash: b5deb4a3abc944d40fdf94f6d9b6aaf3237e6be7
ms.sourcegitcommit: bad28e99214cf62cfbd1222e8cb5ded1997d7ff0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2019
ms.locfileid: "74298983"
---
# <a name="optimizing-your-azure-code"></a>Optimalizace kódu Azure
Pokud programujete aplikace, které využívají Microsoft Azure, existují některé postupy psaní kódu, které byste měli postupovat, která pomáhá zabránit problémům s aplikací škálovatelnost, chování a výkon v cloudovém prostředí. Společnost Microsoft poskytuje nástroj Azure analýzy kódu, který rozpozná a některé z těchto problémů obvykle zjistil identifikuje a pomáhá vám je vyřešit. Můžete stáhnout nástroj v sadě Visual Studio prostřednictvím balíčku NuGet.

## <a name="azure-code-analysis-rules"></a>Pravidla analýzy kódu pro Azure
Nástroj pro analýzu kódu Azure používá následující pravidla automaticky Azure kódu označit, že najde známé problémy s dopadem na výkon. Zjištěny problémy se zobrazí jako upozornění nebo chyby kompilátoru. Opravy kódu nebo návrhy k vyřešení upozornění nebo chyby, je často zajišťována ikonou žárovky.

## <a name="avoid-using-default-in-process-session-state-mode"></a>Vyhněte se použití výchozí režim stavu relace (v rámci procesu)
### <a name="id"></a>ID
AP0000

### <a name="description"></a>Popis
Pokud používáte výchozí režim stavu relace (v rámci procesu) pro cloudové aplikace, může dojít ke ztrátě stavu relace.

Sdílejte své nápady a zpětnou vazbu na [základě názoru analýzy kódu Azure](https://go.microsoft.com/fwlink/?LinkId=403771).

### <a name="reason"></a>Důvod
Ve výchozím nastavení je zadaný v souboru web.config režim stavu relace v procesu. Navíc pokud žádná položka zadaná v konfiguračním souboru, režim stavu relace tak výchozí hodnota je v procesu. Režim v procesu ukládá stav relace v paměti na webovém serveru. Při restartování instance nebo novou instanci se používá pro vyrovnávání zatížení nebo podporu převzetí služeb při selhání, není uložen stav relace, které jsou uložené v paměti na webovém serveru. Tato situace zabrání aplikaci v právě škálovatelné v cloudu.

Stavu relace ASP.NET podporuje několik různých možností ukládání pro data o stavu relace: InProc, StateServer, systému SQL Server, vlastní a Off. Pro hostování dat v externím úložišti stavu relace, jako je třeba [zprostředkovatel stavu relací Azure pro Redis](https://go.microsoft.com/fwlink/?LinkId=401521), se doporučuje použít vlastní režim.

### <a name="solution"></a>Řešení
K ukládání stavu relace na služby managed cache service je jedním z doporučených řešení. Naučte se používat [zprostředkovatele stavu relace Azure pro Redis](https://go.microsoft.com/fwlink/?LinkId=401521) k uložení stavu relace. Můžete také ukládat stav relace v jiných zdrojů, ujistěte se, že je vaše aplikace v cloudu škálovatelný. Pokud se chcete dozvědět víc o alternativních řešeních, přečtěte si [režimy stavu relace](https://msdn.microsoft.com/library/ms178586).

## <a name="run-method-should-not-be-async"></a>Spuštění metody by neměly být asynchronní.
### <a name="id"></a>ID
AP1000

### <a name="description"></a>Popis
Vytvořte asynchronní metody (například [await](https://msdn.microsoft.com/library/hh156528.aspx)) mimo metodu [Run ()](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) a potom zavolejte asynchronní metody z rutiny [Run ()](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx). Deklarace metody [[Run ()](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx)](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) jako Async způsobí, že role pracovního procesu vstoupí do smyčky restart.

Sdílejte své nápady a zpětnou vazbu na [základě názoru analýzy kódu Azure](https://go.microsoft.com/fwlink/?LinkId=403771).

### <a name="reason"></a>Důvod
Volání asynchronních metod uvnitř metody [Run ()](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) způsobí, že běhové prostředí cloudové služby recykluje roli pracovního procesu. Když se spustí role pracovního procesu, provede se všechny provádění programu uvnitř metody [Run ()](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) . Ukončení metody [Run ()](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) způsobí restart role pracovního procesu. Když modul runtime role pracovního procesu dosáhne asynchronní metody, odešle všechny operace po asynchronní metody a pak vrátí. Tím dojde k ukončení role pracovního procesu z metody [[[[Run ()](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx)](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx)](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx)](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) a k restartování. Role pracovního procesu v další iteraci provádění volání asynchronní metody znovu a restartuje, způsobuje tak recyklování znovu i role pracovního procesu.

### <a name="solution"></a>Řešení
Všechny asynchronní operace umístěte mimo metodu [Run ()](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) . Pak zavolejte refaktoringovou asynchronní metodu z metody [[Run ()](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx)](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) , jako je například RunAsync (). Wait. Nástroj pro analýzu kódu Azure vám může pomoci vyřešit tento problém.

Následující fragment kódu ukazuje kód opravu tohoto problému:

```csharp
public override void Run()
{
    RunAsync().Wait();
}

public async Task RunAsync()
{
    //Asynchronous operations code logic
    // This is a sample worker implementation. Replace with your logic.

    Trace.TraceInformation("WorkerRole1 entry point called");

    HttpClient client = new HttpClient();

    Task<string> urlString = client.GetStringAsync("https://msdn.microsoft.com");

    while (true)
    {
        Thread.Sleep(10000);
        Trace.TraceInformation("Working");

        string stream = await urlString;
    }

}
```

## <a name="use-service-bus-shared-access-signature-authentication"></a>Ověřování pomocí služby Service Bus sdílený přístupový podpis
### <a name="id"></a>ID
AP2000

### <a name="description"></a>Popis
Pro ověřování pomocí sdíleného přístupového podpisu (SAS). Access Control Service (ACS) je zastaralé pro ověřování pomocí služby service bus.

Sdílejte své nápady a zpětnou vazbu na [základě názoru analýzy kódu Azure](https://go.microsoft.com/fwlink/?LinkId=403771).

### <a name="reason"></a>Důvod
Pro zvýšení zabezpečení Azure Active Directory nahrazuje ověřování ACS s ověřováním SAS. Další informace o plánu přechodu najdete v tématu [Azure Active Directory budoucnosti služby ACS](https://cloudblogs.microsoft.com/enterprisemobility/2013/06/22/azure-active-directory-is-the-future-of-acs/) .

### <a name="solution"></a>Řešení
Použijte ověřování SAS ve svých aplikacích. Následující příklad ukazuje, jak používat existující token SAS pro přístup k oboru názvů služby Service bus nebo entity.

```csharp
MessagingFactory listenMF = MessagingFactory.Create(endpoints, new StaticSASTokenProvider(subscriptionToken));
SubscriptionClient sc = listenMF.CreateSubscriptionClient(topicPath, subscriptionName);
BrokeredMessage receivedMessage = sc.Receive();
```

V následujících tématech pro další informace.

* Přehled najdete v tématu [ověřování pomocí sdíleného přístupového podpisu s Service Bus](https://msdn.microsoft.com/library/dn170477.aspx) .
* [Jak používat ověřování pomocí sdíleného přístupového podpisu s Service Bus](https://msdn.microsoft.com/library/dn205161.aspx)

## <a name="consider-using-onmessage-method-to-avoid-receive-loop"></a>Zvažte možnost vyhnout "smyčka příjmu" OnMessage – metoda
### <a name="id"></a>ID
AP2002

### <a name="description"></a>Popis
Aby nedocházelo k tomu **, že volání metody "** Receive", je lepším řešením pro příjem zpráv než volání metody **Receive** . Pokud však musíte použít metodu **Receive** a zadáte nevýchozí dobu čekání serveru, ujistěte se, že doba čekání serveru je delší než jedna minuta.

Sdílejte své nápady a zpětnou vazbu na [základě názoru analýzy kódu Azure](https://go.microsoft.com/fwlink/?LinkId=403771).

### <a name="reason"></a>Důvod
Při volání **metody**"klient spustí interní čerpadlo zpráv, které se neustále dotazuje na frontu nebo odběr. Tato "message pump" obsahuje nekonečnou smyčku, která vydává volání pro příjem zpráv. Pokud vyprší časový limit volání, odešle nové volání. Interval časového limitu je určen hodnotou vlastnosti [OperationTimeout](https://msdn.microsoft.com/library/microsoft.servicebus.messaging.messagingfactorysettings.operationtimeout.aspx) [MessagingFactory](https://msdn.microsoft.com/library/microsoft.servicebus.messaging.messagingfactory.aspx), která je používána.

Výhodou použití rutiny **informování** v porovnání s **příjmem** je, že uživatelé nemusejí provádět ruční dotazování na zprávy, zpracovávat výjimky, zpracovávat paralelní zpracování více zpráv a doplňovat zprávy.

Pokud zavoláte **Receive** bez použití výchozí hodnoty, ujistěte se, že hodnota *ServerWaitTime* je větší než jedna minuta. Nastavení *ServerWaitTime* na více než jednu minutu zabraňuje serveru v vypršení časového limitu před úplným přijetím zprávy.

### <a name="solution"></a>Řešení
Podrobnosti najdete na následující příklady kódu pro použití, doporučených. Další podrobnosti najdete v tématu [Metoda QueueClient.-Message (Microsoft. ServiceBus. Messaging)](https://msdn.microsoft.com/library/microsoft.servicebus.messaging.queueclient.onmessage.aspx)a [QueueClient. Receive (Microsoft. ServiceBus. Messaging)](https://msdn.microsoft.com/library/microsoft.servicebus.messaging.queueclient.receive.aspx).

Pokud chcete zlepšit výkon infrastruktury zasílání zpráv Azure, přečtěte si Úvod do modelu návrhu [asynchronního zasílání zpráv](https://msdn.microsoft.com/library/dn589781.aspx).

Následuje příklad použití zprávy- **Message** k přijetí zpráv.

```csharp
void ReceiveMessages()
{
    // Initialize message pump options.
    OnMessageOptions options = new OnMessageOptions();
    options.AutoComplete = true; // Indicates if the message-pump should call complete on messages after the callback has completed processing.
    options.MaxConcurrentCalls = 1; // Indicates the maximum number of concurrent calls to the callback the pump should initiate.
    options.ExceptionReceived += LogErrors; // Enables you to get notified of any errors encountered by the message pump.

    // Start receiving messages.
    QueueClient client = QueueClient.Create("myQueue");
    client.OnMessage((receivedMessage) => // Initiates the message pump and callback is invoked for each message that is received, calling close on the client will stop the pump.
    {
        // Process the message.
    }, options);
    Console.WriteLine("Press any key to exit.");
    Console.ReadKey();
```

Následuje příklad použití **příjmu** s výchozím časem čekání serveru.

```csharp
string connectionString =
CloudConfigurationManager.GetSetting("Microsoft.ServiceBus.ConnectionString");

QueueClient Client =
    QueueClient.CreateFromConnectionString(connectionString, "TestQueue");

while (true)
{
   BrokeredMessage message = Client.Receive();
   if (message != null)
   {
      try
      {
         Console.WriteLine("Body: " + message.GetBody<string>());
         Console.WriteLine("MessageID: " + message.MessageId);
         Console.WriteLine("Test Property: " +
            message.Properties["TestProperty"]);

         // Remove message from queue
         message.Complete();
      }

      catch (Exception)
      {
         // Indicate a problem, unlock message in queue
         message.Abandon();
      }
   }
```

Následuje příklad použití **příjmu** s nevýchozí dobou čekání serveru.

```csharp
while (true)
{
   BrokeredMessage message = Client.Receive(new TimeSpan(0,1,0));

   if (message != null)
   {
      try
      {
         Console.WriteLine("Body: " + message.GetBody<string>());
         Console.WriteLine("MessageID: " + message.MessageId);
         Console.WriteLine("Test Property: " +
            message.Properties["TestProperty"]);

         // Remove message from queue
         message.Complete();
      }

      catch (Exception)
      {
         // Indicate a problem, unlock message in queue
         message.Abandon();
      }
   }
}
```

## <a name="consider-using-asynchronous-service-bus-methods"></a>Zvažte použití asynchronních metod služby Service Bus
### <a name="id"></a>ID
AP2003

### <a name="description"></a>Popis
Použití asynchronních metod služby Service Bus ke zlepšení výkonu pomocí zasílání zprostředkovaných zpráv.

Sdílejte své nápady a zpětnou vazbu na [základě názoru analýzy kódu Azure](https://go.microsoft.com/fwlink/?LinkId=403771).

### <a name="reason"></a>Důvod
Použití asynchronních metod umožňuje souběžnosti program aplikace, protože provádění každé volání nebrání v hlavním vlákně. Při použití služby Service Bus messaging metody, provádění operace (odesílání, příjem, odstranit, atd.) trvá určitou dobu. Tento čas zahrnuje zpracování operace ve službě Service Bus kromě latenci požadavku a odpovědi. Pokud chcete zvýšit počet operací za čas, musí současně provést operace. Další informace najdete v tématu [osvědčené postupy pro zlepšení výkonu pomocí Service Bus](https://msdn.microsoft.com/library/azure/hh528527.aspx)zprostředkovaných zpráv.

### <a name="solution"></a>Řešení
Informace o použití doporučené asynchronní metody naleznete v tématu [Třída QueueClient (Microsoft. ServiceBus. Messaging)](https://msdn.microsoft.com/library/microsoft.servicebus.messaging.queueclient.aspx) .

Pokud chcete zlepšit výkon infrastruktury zasílání zpráv Azure, přečtěte si Úvod do modelu návrhu [asynchronního zasílání zpráv](https://msdn.microsoft.com/library/dn589781.aspx).

## <a name="consider-partitioning-service-bus-queues-and-topics"></a>Vezměte v úvahu dělení front služby Service Bus a témat
### <a name="id"></a>ID
AP2004

### <a name="description"></a>Popis
Oddíl fronty služby Service Bus a témat pro zajištění lepšího výkonu pomocí zasílání zpráv Service Bus.

Sdílejte své nápady a zpětnou vazbu na [základě názoru analýzy kódu Azure](https://go.microsoft.com/fwlink/?LinkId=403771).

### <a name="reason"></a>Důvod
Dělení front a témat Service Bus, zvýšíte dostupnost propustnosti a služba výkon, protože celkovou propustnost dělené fronty nebo tématu je už omezený výkon zprostředkovatele nebo úložiště zpráv. Kromě toho dočasnému výpadku úložiště nevyužívá dělená fronta nebo téma není k dispozici. Další informace najdete v tématu [dělení entit zasílání zpráv](https://msdn.microsoft.com/library/azure/dn520246.aspx).

### <a name="solution"></a>Řešení
Následující fragment kódu ukazuje, jak rozdělit entit pro zasílání zpráv.

```csharp
// Create partitioned topic.
NamespaceManager ns = NamespaceManager.CreateFromConnectionString(myConnectionString);
TopicDescription td = new TopicDescription(TopicName);
td.EnablePartitioning = true;
ns.CreateTopic(td);
```

Další informace najdete v tématu [dělené a neService Bus fronty a témata | Microsoft Azure blog](https://azure.microsoft.com/blog/2013/10/29/partitioned-service-bus-queues-and-topics/) a podívejte se na ukázku [fronty rozdělené na oddíly Microsoft Azure Service Bus](https://code.msdn.microsoft.com/windowsazure/Service-Bus-Partitioned-7dfd3f1f) .

## <a name="do-not-set-sharedaccessstarttime"></a>Nenastavujte SharedAccessStartTime
### <a name="id"></a>ID
AP3001

### <a name="description"></a>Popis
Byste neměli používat SharedAccessStartTimeset na aktuální čas k okamžitému spuštění zásady sdíleného přístupu. Stačí tuto vlastnost nastavte, pokud chcete spustit později zásady sdíleného přístupu.

Sdílejte své nápady a zpětnou vazbu na [základě názoru analýzy kódu Azure](https://go.microsoft.com/fwlink/?LinkId=403771).

### <a name="reason"></a>Důvod
Synchronizace hodin počítače způsobí, že mírné časový rozdíl mezi datovými centry. Například by logicky domníváte, že nastavení času spuštění úložiště zásady SAS jako aktuální čas pomocí DateTime.Now nebo podobné metody způsobí, že zásady SAS se projeví okamžitě. Mírné časové rozdíly mezi datovými centry však může způsobit problémy s tímto, protože některé datacenter dobu může být mírně vyšší než čas spuštění, zatímco jiní jej před jeho. V důsledku toho můžete zásady SAS vyprší rychle (nebo dokonce hned) Pokud je nastavená doba života zásad příliš krátký.

Další informace o použití sdíleného přístupového podpisu v Azure Storage najdete v tématu [Úvod do tabulky SAS (sdílený přístupový podpis), zařazení do fronty a aktualizace do objektu BLOB SAS-Microsoft Azure Storage týmu domů-MSDN websites](https://blogs.msdn.microsoft.com/windowsazurestorage/2012/06/12/introducing-table-sas-shared-access-signature-queue-sas-and-update-to-blob-sas/).

### <a name="solution"></a>Řešení
Odeberte příkaz, který nastaví počáteční čas zásady sdíleného přístupu. Nástroj pro analýzu kódu Azure obsahuje opravu tohoto problému. Další informace o správě zabezpečení najdete ve [vzorovém vzoru osobního](https://msdn.microsoft.com/library/dn568102.aspx)vzoru.

Následující fragment kódu ukazuje kód opravu tohoto problému.

```csharp
// The shared access policy provides
// read/write access to the container for 10 hours.
blobPermissions.SharedAccessPolicies.Add("mypolicy", new SharedAccessBlobPolicy()
{
   // To ensure SAS is valid immediately, don’t set start time.
   // This way, you can avoid failures caused by small clock differences.
   SharedAccessExpiryTime = DateTime.UtcNow.AddHours(10),
   Permissions = SharedAccessBlobPermissions.Write |
      SharedAccessBlobPermissions.Read
});
```

## <a name="shared-access-policy-expiry-time-must-be-more-than-five-minutes"></a>Sdílené zásady přístupu čas vypršení platnosti musí být více než pět minut
### <a name="id"></a>ID
AP3002

### <a name="description"></a>Popis
Může být co nejvíce pět minut rozdíl v hodin mezi datacentry na různých místech kvůli Stav známý jako "posun hodin." Abyste zabránili SAS token zásady vypršení platnosti dříve, než plánované, nastavte čas vypršení platnosti bude víc než pět minut.

Sdílejte své nápady a zpětnou vazbu na [základě názoru analýzy kódu Azure](https://go.microsoft.com/fwlink/?LinkId=403771).

### <a name="reason"></a>Důvod
Datová centra v různých umístěních po celém světě synchronizovat signál hodiny. Protože může zabrat určitý čas hodiny signálu projít do různých umístění, může být čas odchylky mezi datacentry v různých geografických umístěních i když všechno, co údajně synchronizována. Tento rozdíl času může mít vliv sdílený přístup počáteční čas a vypršení platnosti interval zásad. Proto aby zásady sdíleného přístupu projeví se okamžitě, nezadávejte čas spuštění. Kromě toho Ujistěte se, že doba vypršení platnosti je více než 5 minut, aby počáteční vypršení časového limitu.

Další informace o použití sdíleného přístupového podpisu ve službě Azure Storage najdete v tématu [Úvod do tabulky SAS (sdílený přístupový podpis), zařazení do fronty a aktualizace do objektu BLOB SAS-Microsoft Azure Storage blogové Blogy domů-MSDN websites](https://blogs.msdn.microsoft.com/windowsazurestorage/2012/06/12/introducing-table-sas-shared-access-signature-queue-sas-and-update-to-blob-sas/).

### <a name="solution"></a>Řešení
Další informace o správě zabezpečení najdete v článku [vzor návrhu osobního Key Pattern](https://msdn.microsoft.com/library/dn568102.aspx).

Následuje příklad nezadáte čas spuštění zásady sdíleného přístupu.

```csharp
// The shared access policy provides
// read/write access to the container for 10 hours.
blobPermissions.SharedAccessPolicies.Add("mypolicy", new SharedAccessBlobPolicy()
{
   // To ensure SAS is valid immediately, don’t set start time.
   // This way, you can avoid failures caused by small clock differences.
   SharedAccessExpiryTime = DateTime.UtcNow.AddHours(10),
   Permissions = SharedAccessBlobPermissions.Write |
      SharedAccessBlobPermissions.Read
});
```

Následuje příklad určující čas spuštění zásady sdíleného přístupu s doba vypršení platnosti zásada, která je větší než pět minut.

```csharp
// The shared access policy provides
// read/write access to the container for 10 hours.
blobPermissions.SharedAccessPolicies.Add("mypolicy", new SharedAccessBlobPolicy()
{
   // To ensure SAS is valid immediately, don’t set start time.
   // This way, you can avoid failures caused by small clock differences.
  SharedAccessStartTime = new DateTime(2014,1,20),
 SharedAccessExpiryTime = new DateTime(2014, 1, 21),
   Permissions = SharedAccessBlobPermissions.Write |
      SharedAccessBlobPermissions.Read
});
```

Další informace najdete v tématu [Vytvoření a použití sdíleného přístupového podpisu](https://msdn.microsoft.com/library/azure/jj721951.aspx).

## <a name="use-cloudconfigurationmanager"></a>Použití CloudConfigurationManager
### <a name="id"></a>ID
AP4000

### <a name="description"></a>Popis
Použití třídy [ConfigurationManager](https://msdn.microsoft.com/library/system.configuration.configurationmanager\(v=vs.110\).aspx) pro projekty, jako je například web Azure a Azure Mobile Services, nezavádí běhové problémy. Jako osvědčený postup je ale vhodné použít cloudové[ConfigurationManager](https://msdn.microsoft.com/library/system.configuration.configurationmanager\(v=vs.110\).aspx) jako jednotný způsob správy konfigurací pro všechny cloudové aplikace Azure.

Sdílejte své nápady a zpětnou vazbu na [základě názoru analýzy kódu Azure](https://go.microsoft.com/fwlink/?LinkId=403771).

### <a name="reason"></a>Důvod
CloudConfigurationManager čte konfigurační soubor vhodné prostředí aplikace.

[CloudConfigurationManager](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.cloudconfigurationmanager.aspx)

### <a name="solution"></a>Řešení
Refaktorujte kód pro použití [třídy CloudConfigurationManager](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.cloudconfigurationmanager.aspx). Nástroj pro analýzu kódu Azure poskytuje kód opravu tohoto problému.

Následující fragment kódu ukazuje kód opravu tohoto problému. Nahradit

`var settings = ConfigurationManager.AppSettings["mySettings"];`

with

`var settings = CloudConfigurationManager.GetSetting("mySettings");`

Tady je příklad toho, jak uložit nastavení konfigurace v souboru App.config nebo Web.config. Přidání nastavení na sekci appSettings v konfiguračním souboru. Následuje soubor Web.config pro předchozí příklad kódu.

```xml
<appSettings>
    <add key="webpages:Version" value="3.0.0.0" />
    <add key="webpages:Enabled" value="false" />
    <add key="ClientValidationEnabled" value="true" />
    <add key="UnobtrusiveJavaScriptEnabled" value="true" />
    <add key="mySettings" value="[put_your_setting_here]"/>
  </appSettings>
```

## <a name="avoid-using-hard-coded-connection-strings"></a>Vyhněte se používání pevně zakódovaných propojovacích řetězců
### <a name="id"></a>ID
AP4001

### <a name="description"></a>Popis
Pokud používáte pevně zakódovaných propojovacích řetězců a budete je muset aktualizovat později, budete muset provést změny zdrojového kódu a znovu zkompilovat aplikaci. Nicméně pokud uchováváte připojovací řetězce v konfiguračním souboru, můžete je později změníte stačí jednoduše aktualizovat konfigurační soubor.

Sdílejte své nápady a zpětnou vazbu na [základě názoru analýzy kódu Azure](https://go.microsoft.com/fwlink/?LinkId=403771).

### <a name="reason"></a>Důvod
Pevně kódováno pomocí připojovací řetězce je chybný postup, protože zavádí problémy při připojovací řetězce musí být rychle změnit. Kromě toho pokud projekt musí být vráceny se změnami do správy zdrojového kódu, zavést pevně zakódovaných propojovacích řetězců ohrožení zabezpečení, protože řetězce si můžou prohlédnout ve zdrojovém kódu.

### <a name="solution"></a>Řešení
Připojovací řetězce Store v konfiguračních souborů nebo prostředí Azure.

* Pro samostatné aplikace pomocí souboru app.config pro uložení nastavení připojovacího řetězce.
* Pro službu IIS hostované webové aplikace slouží k ukládání připojovacích řetězců souboru web.config.
* Pro aplikace ASP.NET vNext slouží k ukládání připojovacích řetězců configuration.json.

Informace o použití konfiguračních souborů, jako je web. config nebo App. config, najdete v tématu [ASP.NET – pokyny pro konfiguraci webové konfigurace](https://msdn.microsoft.com/library/vstudio/ff400235\(v=vs.100\).aspx). Informace o tom, jak proměnné prostředí Azure fungují, najdete v tématu [weby Azure: jak fungují řetězce aplikace a připojovací řetězce](https://azure.microsoft.com/blog/2013/07/17/windows-azure-web-sites-how-application-strings-and-connection-strings-work/). Informace o ukládání připojovacího řetězce ve správě zdrojového kódu naleznete v tématu [zamezení vkládání citlivých informací, jako jsou připojovací řetězce v souborech, které jsou uloženy v úložišti zdrojového kódu](https://docs.microsoft.com/aspnet/aspnet/overview/developing-apps-with-windows-azure/building-real-world-cloud-apps-with-windows-azure/source-control).

## <a name="use-diagnostics-configuration-file"></a>Použití diagnostického konfiguračního souboru
### <a name="id"></a>ID
AP5000

### <a name="description"></a>Popis
Namísto konfigurace nastavení diagnostiky ve vašem kódu, jako s využitím Microsoft.WindowsAzure.Diagnostics programování rozhraní API, měli byste nakonfigurovat v souboru diagnostics.wadcfg nastavení diagnostiky. (Nebo, pokud používáte Azure SDK 2.5 diagnostics.wadcfgx). Tímto způsobem můžete změnit nastavení diagnostiky bez nutnosti znovu kompilovat kód.

Sdílejte své nápady a zpětnou vazbu na [základě názoru analýzy kódu Azure](https://go.microsoft.com/fwlink/?LinkId=403771).

### <a name="reason"></a>Důvod
Předtím, než Azure SDK 2.5, (ta používá Azure diagnostics 1.3), Azure Diagnostics (WAD) může nakonfigurovat pomocí několika různými způsoby: přidání do objektu blob konfigurace ve službě storage pomocí imperativního kódu, deklarativní konfigurace nebo výchozí konfigurace. Upřednostňovaným způsobem konfigurace diagnostiky je však použít konfigurační soubor XML (Diagnostics. wadcfg nebo Diagnostics. wadcfgx pro sadu SDK 2,5 a novější) v projektu aplikace. V takovém případě soubor diagnostics.wadcfg zcela definuje konfiguraci a můžeme je aktualizovat a znovu nasadit kdykoli. Kombinování použití konfiguračního souboru Diagnostics. wadcfg pomocí programových metod nastavení konfigurací pomocí tříd [DiagnosticMonitor](https://msdn.microsoft.com/library/microsoft.windowsazure.diagnostics.diagnosticmonitor.aspx)nebo [RoleInstanceDiagnosticManager](https://msdn.microsoft.com/library/microsoft.windowsazure.diagnostics.management.roleinstancediagnosticmanager.aspx) může vést k nejasnostem. Další informace najdete v tématu [inicializace nebo změna konfigurace Azure Diagnostics](https://msdn.microsoft.com/library/azure/hh411537.aspx) .

Od verze 1.3 WAD (je součástí Azure SDK 2.5), je už nebude možné použít ke konfiguraci diagnostiky kódu. V důsledku toho můžete zadat pouze konfiguraci při použití nebo rozšíření diagnostiky se aktualizuje.

### <a name="solution"></a>Řešení
Pomocí návrháře konfigurace diagnostiky přesuňte nastavení diagnostiky do konfiguračního souboru diagnostiky (Diagnostics. wadcfg nebo Diagnostics. wadcfgx pro sadu SDK 2,5 a novější). Doporučuje se také nainstalovat [sadu Azure SDK 2,5](https://go.microsoft.com/fwlink/?LinkId=513188) a použít nejnovější diagnostické funkce.

1. V místní nabídce pro roli, kterou chcete konfigurovat, zvolte Vlastnosti a pak zvolte na kartě konfigurace.
2. V části **Diagnostika** se ujistěte, že je zaškrtnuté políčko **Povolit diagnostiku** .
3. Klikněte na tlačítko **Konfigurovat** .

   ![Přístup k možnost povolení diagnostiky](./media/vs-azure-tools-optimizing-azure-code-in-visual-studio/IC796660.png)

   Další informace najdete v tématu [Konfigurace diagnostiky pro Azure Cloud Services a Virtual Machines](vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines.md) .

## <a name="avoid-declaring-dbcontext-objects-as-static"></a>Vyhněte se deklarace objektů DbContext jako statické
### <a name="id"></a>ID
AP6000

### <a name="description"></a>Popis
Šetří paměť, zabráníte tak deklarace objektů DBContext jako statické.

Sdílejte své nápady a zpětnou vazbu na [základě názoru analýzy kódu Azure](https://go.microsoft.com/fwlink/?LinkId=403771).

### <a name="reason"></a>Důvod
Objekty DBContext ukládání výsledků dotazu z každé volání. Statické objekty DBContext není odstraněn, dokud je doména aplikace uvolněna. Statický objekt DBContext, proto může spotřebovat velké množství paměti.

### <a name="solution"></a>Řešení
Deklarujte DBContext jako lokální proměnné nebo nestatické instance pole, použijte pro úlohy a nechat ji zrušit, po použití.

V následujícím příkladu třída kontroleru MVC ukazuje, jak použít objekt DBContext.

```csharp
public class BlogsController : Controller
    {
        //BloggingContext is a subclass to DbContext
        private BloggingContext db = new BloggingContext();
        // GET: Blogs
        public ActionResult Index()
        {
            //business logics…
            return View();
        }
        protected override void Dispose(bool disposing)
        {
            if (disposing)
            {
                db.Dispose();
            }
            base.Dispose(disposing);
        }
    }
```

## <a name="next-steps"></a>Další kroky
Další informace o optimalizaci a řešení potíží s aplikacemi Azure najdete v tématu [řešení potíží s webovou aplikací v Azure App Service pomocí sady Visual Studio](/azure/app-service/web-sites-dotnet-troubleshoot-visual-studio).
