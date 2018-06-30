---
title: Import položek z existující stránky SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.WSPImport.SelectionDependency
- VS.SharepointTools.WSPImport.SpecifyProjectSource
- VS.SharePointTools.WSPImport.SelectionItemsToImport
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, importing items
- SharePoint development in Visual Studio, importing .wsp files
- importing items [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 21ca61f29138aee5a4c22cbf872d6698d4180d50
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120190"
---
# <a name="import-items-from-an-existing-sharepoint-site"></a>Import položek z existující stránky SharePoint
  Šablona projektu Import balíčku řešení služby SharePoint můžete znovu použít elementů, jako jsou typy obsahu a pole z existujících webů služby SharePoint v nové [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] řešení služby SharePoint. I když můžete spustit nejvíce importované řešení bez jakýchkoli úprav, existují určitá omezení a které byste měli zvážit, zejména v případě, že po importu upravíte všechny položky.  
  
> [!NOTE]  
>  Provést import znovu použitelné pracovní postupy, použijte šablonu projektu Import opakovaně použitelného pracovního postupu. [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)] [Pokyny pro import znovu použitelné pracovní postupy](../sharepoint/guidelines-for-importing-reusable-workflows.md).  
  
## <a name="supported-sharepoint-solutions"></a>Podporované řešení služby SharePoint
 [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)] plně podporuje import řešení vytvořená v [!INCLUDE[wss_14_short](../sharepoint/includes/wss-14-short-md.md)] a [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)].  
  
 [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)] nepodporuje import řešení vytvořená v následujících aplikacích:  
  
-   [!INCLUDE[winshare3](../sharepoint/includes/winshare3-md.md)]  
  
-   [!INCLUDE[offshare7](../sharepoint/includes/offshare7-md.md)]  
  
-   [!INCLUDE[vs_orcas_long](../sharepoint/includes/vs-orcas-long-md.md)]  
  
-   Microsoft SharePoint Designer 2007  
  
-   [!INCLUDE[vs_dev10_long](../sharepoint/includes/vs-dev10-long-md.md)]  
  
 I když můžete často úspěšně importovat řešení, které jsou vytvořené pomocí těchto aplikací, které tuto funkci je netestováno a není podporována.  
  
## <a name="item-import-restrictions"></a>Omezení import položek
 I když většina SharePoint – položky lze importovat z existující *WSP* souboru následující položky nejsou podporovány a může vyžadovat změny pro práci správně:  
  
-   Entity služby BDC  
  
-   Kód přidružení workflow – elementy  
  
-   Pracovní postupy kódu  
  
-   Visual webových částí (.ascx)  
  
-   Webové služby (*.asmx*)  
  
-   Typ obsahu vazby  
  
-   Přijímače událostí  
  
-   Seznam definic (šablony)  
  
-   Definice webů  
  
 Při exportu řešení z [!INCLUDE[wss_14_short](../sharepoint/includes/wss-14-short-md.md)] nebo [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)], tyto položky jsou automaticky vyloučeny z *WSP* souboru. Ale jiné *WSP* soubory vytvořené z nepodporované nástrojů může obsahovat tyto položky. (Viz "Řešení služby SharePoint podporováno" dříve v tomto tématu.)  
  
## <a name="what-happens-when-you-import-a-solution"></a>Co se stane, když importujete řešení
 Při importu řešení pomocí šablony importem balíčku řešení služby SharePoint, [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] zkopíruje všechny obsahu *WSP* importovat soubor a pokusí sloučit a zachovat tolik přidružení a odkazů mezi elementy a jejich soubory míře.  
  
 Zkopírujte všechny importované položky do příslušné složky v **Průzkumníku řešení**. Například typy obsahu objeví ve složce **typů obsahu** a instancí seznamu se zobrazí pod **seznam instancí**. Soubory spojené s importované položky jsou také zkopírován do složky položky. Například instance importované seznam obsahuje její moduly, formuláře a stránky ASPX.  
  
### <a name="dependent-items"></a>Závislé položky
 Když vyberete položku v Průvodci importem balíčku řešení služby SharePoint, ale ne jeho závislé položky, okno se zprávou vás upozorní, že závislé položky musí také vybrat před importem.  
  
### <a name="what-are-features"></a>Jaké jsou funkce?
 SharePoint Designer uživatelé mohou vidět neočekávané souborech s názvem *funkce*, se zobrazí v jejich importované řešení v **Průzkumníku řešení.** I když funkce existovalo v řešení služby SharePoint Designer, byly skryta zobrazení. Funkce jsou teď zobrazené v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
 Funkce jsou kontejnery pro SharePoint – položky. Jednotlivé funkce udržuje odkaz na jednotlivé položky, jako jsou typy obsahu a seznam definic, které obsahuje. Při importu řešení, [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] nastaví funkcí pro všechny importované elementy a pokusí se udržovat vztahy element funkce pro soubory. Všechny soubory, jejichž odkazy nebylo možné přeložit nacházejí ve **ostatní soubory importovat** složky.  
  
 Další informace o funkcích najdete v tématu [řešení služby SharePoint vyvíjet](../sharepoint/developing-sharepoint-solutions.md) a [práci s funkcemi](http://go.microsoft.com/fwlink/?LinkID=147704).  
  
### <a name="handle-special-cases"></a>Zpracování zvláštních případech
 V některých případech Visual Studio, nejdou sjednotit položky s jeho závislých souborů. Všechny soubory, které [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] nebylo možné přeložit zobrazí ve složce **ostatní soubory importovat**. Kromě toho jejich **DeploymentType** vlastnosti jsou nastaveny na **NoDeployment** tak, aby se nenasadí do řešení.  
  
 Například při importu definice seznamu ExpenseForms, definice seznamu s tímto názvem se zobrazí pod **seznam definic** složky v **Průzkumníku řešení** spolu s jeho  *Elements.xml* a *Schema.xml* soubory. Však možné umístit přidruženy formuláře ASPX a HTML ve složce s názvem **ExpenseForms** pod **ostatní soubory importovat** složky. K dokončení importu, přesunutí těchto souborů v rámci definice seznamu ExpenseForms v **Průzkumníku řešení** a změňte **DeploymentType** vlastnost pro každý soubor z **NoDeployment** k **ElementFile**.  
  
 Při importu přijímače událostí *Elements.xml* soubor zkopírován do správného umístění, ale je nutné ručně zahrnout sestavení balíčku řešení tak, aby se nasadí do řešení. [!INCLUDE[crabout](../sharepoint/includes/crabout-md.md)] jak to udělat, najdete v části [postupy: Přidání a odebrání dalších sestavení](../sharepoint/how-to-add-and-remove-additional-assemblies.md).  
  
 Při importu pracovní postupy, formuláře aplikace InfoPath se zkopírují do **ostatní soubory importovat** složky. Pokud *WSP* soubor obsahuje šablony, je nastavený jako spouštěcí stránku v **Průzkumníku řešení**.  
  
## <a name="import-fields-and-property-bags"></a>Pole pro import a kontejnery objektů a dat
 Při importu řešení, které obsahuje několik polí, všechny definice samostatné pole jsou sloučeny do jednoho *Elements.xml* souboru pod uzlem v **Průzkumníku řešení** názvem **pole** . Podobně se sloučí všech položek *Elements.xml* souboru pod uzel s názvem **PropertyBags**.  
  
 Pole ve službě SharePoint se sloupci zadaného datového typu, například textu, logická hodnota nebo vyhledávání. Další informace najdete v tématu [stavebním blokem: sloupce a typy polí](http://go.microsoft.com/fwlink/?LinkId=182304). Kontejnery objektů a dat umožňují přidávat vlastnosti pro objekty ve službě SharePoint, všechno z farmy do seznamu na webu služby SharePoint. Kontejnery objektů a dat jsou implementované jako zatřiďovací tabulku z názvů a hodnot vlastností. Další informace najdete v tématu [Správa konfigurace služby SharePoint](http://go.microsoft.com/fwlink/?LinkId=182296) nebo [nastavení kontejner objektů a dat služby SharePoint vlastností](http://go.microsoft.com/fwlink/?LinkId=182297).  
  
## <a name="delete-items-in-the-project"></a>Odstranění položek v projektu
 Většina položek v řešení služby SharePoint mít jeden nebo více závislé položky. Například seznam instancí závisí na obsahu typy a typy obsahu závisí na pole. Po importu řešení služby SharePoint, [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] neupozorní žádné problémy odkaz Pokud odstraníte položku v řešení, ale ne jeho závislé položky, dokud pokusem o nasazení řešení. Například pokud má importované řešení seznamu instanci, která závisí na typu obsahu a odstranit tento typ obsahu, může dojít k chybě při nasazení. Této chybě dojde, pokud není k dispozici na serveru SharePoint závislé položky. Podobně pokud odstraněné položky má také kontejner souvisejících objektů, pak odstraňte těchto položek z **PropertyBags** *Elements.xml* souboru. Proto pokud odstranit všechny položky z importovaných řešení a získat chyby nasazení, zkontrolujte Pokud třeba také odstranit všechny závislé položky.  
  
## <a name="restore-missing-feature-attributes"></a>Obnovit chybějící atributy funkce
 Při importu řešení, jsou vynechány některých atributů volitelná funkce z manifestu importované funkce. Pokud chcete obnovit tyto atributy v souboru nové funkce, identifikovat chybějící atributy tak, že porovnáte původní soubor funkce k manifestu nové funkce a postupujte podle pokynů v tématu [postupy: přizpůsobení funkce služby SharePoint](../sharepoint/how-to-customize-a-sharepoint-feature.md).  
  
## <a name="deployment-conflict-detection-is-not-performed-on-built-in-list-instances"></a>Neprovádí se u instancí seznam předdefinovaných zjišťování konfliktů nasazení
 [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] neprovádí zjišťování konfliktů nasazení na seznam předdefinovaných instance (to znamená, výchozí seznam instancí, které jsou součástí služby SharePoint). Aby nedošlo k přepsání seznam předdefinovaných instance na webu služby SharePoint se provádí není provádění zjišťování konfliktů. Seznam předdefinovaných, instancí jsou stále nasadit nebo aktualizovat, ale jsou nikdy odstranit nebo přepsat. [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)] [Řešení potíží s balení a nasazení SharePoint](../sharepoint/troubleshooting-sharepoint-packaging-and-deployment.md).  
  
## <a name="import-sharepoint-server-2010-workflows"></a>Importovat pracovní postupy SharePoint Server 2010
 Pokud importujete pracovní postup vytvořený v [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)], nebude po jeho nasazení správně fungovat. Pracovní postup se nefunguje správně, protože chybí některé sestavení a [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)] pracovní postupy obsahují InfoPath formulářů, které nejsou aktuálně podporované ve [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] řešení pracovního postupu. Však importovat [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)] pracovní postupy můžete provést po opravě některé položky, jako je například přidávání odkazů na fungovala správně [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)] sestavení a opětovné připojení InfoPath formuláře. [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)] [Import pracovních postupů služby SharePoint Server 2010](http://go.microsoft.com/fwlink/?LinkId=182226).  
  
## <a name="item-name-character-limit"></a>Položka Název limit pro počet znaků
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] limit 260 celkový počet znaků pro projekt a názvy položek projektu, včetně cesty je. Při importu řešení, pokud název položky překračuje tento limit, dojde k chybě:  
  
 **Zadaná cesta a název souboru jsou příliš dlouhé. Plně kvalifikovaný název souboru musí být méně než 260 znaků a název adresáře musí být méně než 248 znaků.**  
  
 Když se tato chyba se nevytvoří položky. Tento problém se nejčastěji vyskytuje v importovaných modulů. K tomuto problému nedošlo, postupujte takto:  
  
-   Použít krátké názvy pro svůj projekt, když zadáte, je v **přidat nový projekt** dialogové okno.  
  
-   Vytvoření projektu v umístění jako blízko kořenové složce co nejrychleji, aby zkrácení cesty.  
  
## <a name="the-sharepointproductversion-attribute"></a>Atribut SharePointProductVersion
 Pokud importujete řešení vytvořena ve starší verzi služby SharePoint, jako [!INCLUDE[winshare3](../sharepoint/includes/winshare3-md.md)] nebo [!INCLUDE[offshare7](../sharepoint/includes/offshare7-md.md)], změňte hodnotu atributu SharePointProductVersion v manifest balíčku k 12.0 nebo vložení ovládacího prvku manager skriptu do všech importovaných Web stránky a nechte SharePointProductVersion nastavit na 14.0. Importované webových formulářů, jinak hodnota nezobrazí ve službě SharePoint.  
  
### <a name="background"></a>Pozadí  
 Řešení v [!INCLUDE[wss_14_short](../sharepoint/includes/wss-14-short-md.md)] a [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)] zahrnují atribut nazvaný SharePointProductVersion. SharePoint používá k určení verze služby SharePoint, které řešení je navrženo pro tento atribut v jeho manifesty balíčku. Dvě platné hodnoty jsou 12.0 a 14.0. Hodnota 12.0 znamená, že položka je určen pro [!INCLUDE[winshare3](../sharepoint/includes/winshare3-md.md)] nebo [!INCLUDE[offshare7](../sharepoint/includes/offshare7-md.md)]; hodnota 14.0 znamená, že položka je určen pro [!INCLUDE[wss_14_short](../sharepoint/includes/wss-14-short-md.md)] nebo [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)].  
  
 Pro lepší zabezpečení při vykreslování stránky ASPX [!INCLUDE[wss_14_short](../sharepoint/includes/wss-14-short-md.md)] a [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)] vynutit, aby všechny stránky předlohy nebo ASPX obsahovalo ovládacího prvku skript správce. Další informace o skriptu manager najdete v tématu [– Přehled ovládacího prvku ScriptManager](http://go.microsoft.com/fwlink/?LinkID=169399). Proto není k dispozici v prvku manager skriptu [!INCLUDE[winshare3](../sharepoint/includes/winshare3-md.md)] a [!INCLUDE[offshare7](../sharepoint/includes/offshare7-md.md)], jeden musí být přidaný do žádné [!INCLUDE[winshare3](../sharepoint/includes/winshare3-md.md)] nebo [!INCLUDE[offshare7](../sharepoint/includes/offshare7-md.md)] stránky, která se upgraduje na [!INCLUDE[wss_14_short](../sharepoint/includes/wss-14-short-md.md)] nebo [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)]. Stránky ASPX, které používají standardní stránky předlohy nevyžadují ovládacího prvku skript správce, protože jedna již byla přidána do standardní stránky předlohy. Však musí stránky ASPX, nepoužívejte stránky předlohy nebo které využívají vlastní stránky předlohy přidání ovládacího prvku skriptu fungování [!INCLUDE[wss_14_short](../sharepoint/includes/wss-14-short-md.md)] nebo [!INCLUDE[moss_14_short](../sharepoint/includes/moss-14-short-md.md)].  
  
 Absence ovládacího prvku skript správce může být problém, při importu [!INCLUDE[winshare3](../sharepoint/includes/winshare3-md.md)] nebo [!INCLUDE[offshare7](../sharepoint/includes/offshare7-md.md)] projektu do [!INCLUDE[vs_dev10_long](../sharepoint/includes/vs-dev10-long-md.md)], protože atribut SharePointProductVersion všechny nové projekty je nastavena na 14.0. Pokud nasadíte upgradovaném projektu, který má webového formuláře bez správce skriptu, formuláře nezobrazí ve službě SharePoint.  
  
## <a name="see-also"></a>Viz také:
 [Návod: Import položek z existující stránky SharePoint](../sharepoint/walkthrough-import-items-from-an-existing-sharepoint-site.md)   
 [Pokyny pro import znovu použitelné pracovní postupy](../sharepoint/guidelines-for-importing-reusable-workflows.md)   
 [Návod: Importujte opakovaně použitelného pracovního postupu návrháře služby SharePoint do sady Visual Studio](../sharepoint/walkthrough-import-a-sharepoint-designer-reusable-workflow-into-visual-studio.md)   
 [Postupy: Přidání stávajícího souboru modelu služby BDC do projektu služby SharePoint](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)  
