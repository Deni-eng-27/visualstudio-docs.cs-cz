---
title: Jaké možnosti publikování je pro mě nejlepší? | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.reviewer: riande
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
helpviewer_keywords:
- ASP.NET, web applications, deployment, publishing
ms.assetid: 3A13F685-531C-457D-A98E-631888011E4B
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5927986b8c89a2e86fcecf874eae35ac016805f3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# Jaké možnosti publikování je pro mě nejlepší?

Z Visual Studia, webové aplikace lze publikovat přímo na následující cíle:

- [Aplikační služba Azure](#azure-app-service)
- [Virtuální počítače Azure](#azure-virtual-machines)
- [Systém souborů](#file-system)
- [Vlastní cíle (služby IIS, FTP, atd.) ](#custom-targets), který zahrnuje všechny libovolné webové servery.

Na **publikovat** kartě můžete vybrat existující profil publikování, importovat existující nebo vytvořit novou pomocí možnosti popsané v tomto poli. Prohlídka možnosti publikování v integrovaném vývojovém prostředí pro různých typů aplikací, najdete v části [první pohled na nasazení](../../deployment/deploying-applications-services-and-components.md).

## Azure App Service Web Apps

[Azure App Service Web Apps](/azure/app-service/app-service-web-overview) (nebo jenom webové aplikace) pomáhá vývojářům rychle vytvořit různé škálovatelných webových aplikací a služeb bez údržbu infrastruktury.

Můžete určit, kolik computing spotřeby webové aplikace má výběrem [cenová úroveň nebo se chystáte](/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview) pro službu obsahující aplikaci. Můžete mít více webových aplikací (a jinými typy aplikací) sdílet stejnou službu aplikace beze změny cenové úrovně. Například můžete hostovat vývoj, pracovní a provozní společně na stejném App Service Web Apps.

App Service běží na hostovaných v cloudu virtuálních počítačů v Azure, ale jsou spravovaná tyto virtuální počítače. Každou webovou aplikaci v App Service bude přiřazen jedinečný \*. azurewebsites.net URL; všechny cenové úrovně než volné povolit přiřazení vlastních názvů domén do lokality.

### Když chcete-li zvolit Azure App Service Web Apps

- Chcete nasadit webovou aplikaci, která je přístupná prostřednictvím Internetu.
- Chcete automaticky škálovat podle požadavků webové aplikace bez nutnosti znovu nasadit.
- Nechcete udržovat infrastrukturu serveru (včetně aktualizací softwaru).
- Nepotřebujete žádné úpravy na úrovni počítače na serverech, které jsou hostiteli webové aplikace.

> Pokud chcete používat Azure App Service ve svém vlastním datovém centru nebo jiným počítačům v místě, můžete to udělat tak pomocí [zásobník Azure](https://azure.microsoft.com/overview/azure-stack/).

Další informace o publikování aplikací ASP.NET Core najdete v tématu [publikování webové aplikace ASP.NET Core Azure App Service pomocí sady Visual Studio](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs).

## Virtuální počítače Azure

[Virtuální počítače Azure (VM)](https://azure.microsoft.com/documentation/services/virtual-machines/) umožňují vytvářet a spravovat libovolný počet výpočetních prostředků v cloudu. Za předpokladu, odpovědnost za všechny softwaru a aktualizací na virtuálních počítačích, můžete je upravit tolik, kolik požadovaného podle požadavků vaší webové aplikaci. Virtuální počítače můžete přistupovat přímo prostřednictvím vzdálené plochy, a také požadovaných každé z nich budou udržovat přiřazená IP adresa.

Škálování webové aplikace, která je hostovaná na virtuálních počítačích zahrnuje otáčí až další virtuální počítače podle požadavků a pak nasazení potřebný software. Tato další úroveň umožňuje ovládací prvek, je škálovat jinak v různých oblastech globální. Například pokud vaše aplikace je obsluhuje zaměstnanci v různých místní pobočky, je možné škálovat podle počtu zaměstnanců v těchto oblastech potenciálně snižuje tak náklady na virtuální počítače.

Další informace najdete v části [podrobné porovnání](https://azure.microsoft.com/documentation/articles/choose-web-site-cloud-service-vm/) mezi Azure App Service, Azure Virtual Machines a jinými službami Azure, které můžete použít jako cíl nasazení pomocí možnosti vlastní v sadě Visual Studio.

### Když vyberte virtuální počítače Azure aplikace

- Chcete nasadit webovou aplikaci, která je přístupná prostřednictvím Internetu, s plnou kontrolu nad životnost přiřazené IP adresy.
- Je nutné přizpůsobení na úrovni počítače na serverech, což zahrnuje další software, například systém specializované databáze, konkrétní síťové konfigurace, diskových oddílů a tak dále.
- Chcete, aby dobře úroveň kontroly nad škálování webové aplikace.
- Musíte přímý přístup k serverům hostování vaší aplikace z jiného důvodu.

> Pokud chcete používat virtuální počítače Azure ve svém vlastním datovém centru nebo jiným počítačům v místě, můžete provést tak pomocí [zásobník Azure](https://azure.microsoft.com/overview/azure-stack/).


## Systém souborů

Nasazení do systému souborů znamená jednoduše zkopírovat soubory webové aplikace do konkrétní složky ve vašem počítači. Tato možnost se nejčastěji používá pro účely testování nebo pro nasazení aplikací pro použití v omezený počet lidí, pokud počítač běží webovém serveru. Pokud cílová složka je sdílena v síti, pak nasazení do systému souborů můžete zpřístupnit webové aplikace soubory ostatním uživatelům, kteří mohou poté ji nasadit do konkrétních serverů.

Všechny místní počítače se systémem webového serveru můžete zpřístupnit aplikaci prostřednictvím Internetu nebo intranetu v závislosti na tom, jak je nakonfigurovaná a sítě, ke kterým je připojen. (Pokud se počítač připojit přímo k Internetu, buďte opatrní hlavně k ochraně před externí ohrožení zabezpečení.) Vzhledem k tomu, že budete spravovat tyto počítače, můžete začít úplnou kontrolu nad softwarových a hardwarových konfiguracích.

Všimněte si, že pokud z nějakého důvodu (například přístup k počítači) nejste moci používat cloudové služby, jako je Azure App Service nebo virtuálních počítačích Azure, můžete použít [zásobník Azure](https://azure.microsoft.com/overview/azure-stack/) ve svém vlastním datovém centru. Zásobník Azure umožňuje spravujete a používáte výpočetních prostředků pomocí Azure App Service a Azure Virtual Machines zachováním ještě všechno místně.

### Kdy použít nasazení systému souborů

- Potřebovat pouze nasazení aplikace do sdílené složky, ze kterého ostatní nasadí ho na různé servery.
- Je nutné pouze místní testovací nasazení.
- Chcete prozkoumat a upravit soubory aplikace potenciálně nezávisle před jejich odesláním na jiný cíl nasazení.

Další informace o nasazení aplikací .NET Core najdete v tématu [.NET Core nasazení aplikace pomocí sady Visual Studio](/dotnet/core/deploying/deploy-with-vs).

## Vlastní cíle

Vlastní cíl umožňuje nasadit webovou aplikaci na cíl, než Azure App Service, virtuální počítače Azure nebo místního systému souborů. Můžete nasadit systém souborů nebo jiný server (Internetu nebo intranetu) ke kterému máte přístup, včetně těch, na jiných cloudových služeb. Můžete pracovat s web nasazení (soubory nebo. ZIP) a FTP.

Při výběru vlastní cíl, Visual Studio vás vyzve k zadání názvu profilu a pak shromažďovat další **připojení** informace, včetně na cílový server nebo umístění, název lokality a přihlašovací údaje. Můžete řídit následujících chování na **nastavení** karty:

- Konfigurace, které chcete nasadit.
- Jestli chcete odebrat existující soubory z cílového umístění.
- Určuje, zda předkompilovat během publikování.
- Určuje, zda chcete vyloučit soubory ve složce App_Data z nasazení.

Můžete vytvořit libovolný počet vlastní profily nasazení v sadě Visual Studio, které umožňují spravovat profily s jiným nastavením.

### Kdy použít vlastní nasazení

- Cloudové služby používáte na zadejte než Azure, která je přístupná prostřednictvím adresy URL.
- Chcete nasadit, pomocí přihlašovacích údajů než ty, které používáte v sadě Visual Studio, nebo těch, které přímo navázána na vaše účty Azure.
- Chcete odstranit soubory z cíle pokaždé, když nasazujete.

Další informace o publikování do služby IIS najdete v tématu [IIS 8.0 pomocí technologie ASP.NET 3.5 a technologii ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45) a [vzdáleného ladění ASP.NET ve vzdáleném počítači IIS](../../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md).