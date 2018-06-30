---
title: 'Návod: Nasazení definice seznamu úkolů projektu | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, deploying
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 2af59e2d5d26a6db1ecde24ca93c3f0d737eb31d
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120176"
---
# <a name="walkthrough-deploy-a-project-task-list-definition"></a>Návod: Nasazení definice seznamu úkolů projektu

Tento postup vám ukáže, jak používat [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)] Pokud chcete vytvořit, upravit, ladění a nasazení seznam serveru SharePoint ke sledování úloh projektu.

[!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

## <a name="prerequisites"></a>Požadavky

- Podporované edice systému Microsoft Windows a služby SharePoint. Další informace najdete v tématu [požadavky na vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).

- Visual Studio 2017 nebo edici nástroje Visual Studio Application Lifecycle Management (ALM).

## <a name="create-a-sharepoint-list"></a>Vytvoření seznamu služby SharePoint

Vytvořte seznam projektu služby SharePoint a přidružte definice seznamu úloh.

1. Otevřete **nový projekt** dialogové okno, rozbalte seznam **SharePoint** uzel a potom zvolte **2010** uzlu.

2. V **šablony** podokně, vyberte **projektu služby SharePoint 2010** šablony, název projektu **ProjectTaskList**a potom vyberte **OK**tlačítko.

     **Průvodce vlastním nastavením SharePoint** se zobrazí.

3. Zadejte místní web služby SharePoint, který používáte pro ladění, vyberte **nasadit jako řešení farmy** možnost tlačítko a potom vyberte **Dokončit** tlačítko.

4. Otevřete místní nabídky projektu a zvolte **přidat** > **novou položku**.

5. V **šablony** podokně, vyberte **seznamu** šablony a potom zvolte **přidat** tlačítko.

     **Průvodce vlastním nastavením SharePoint** se zobrazí.

6. V **zadejte název chcete k zobrazení seznamu?** zadejte **seznamu úkolů projektu**.

7. Vyberte **vytvořit seznam nepřizpůsobitelné na základě existující typu seznamu** možnost tlačítko a zvolte ve svém seznamu **úlohy**a potom zvolte **Dokončit** tlačítko.

     Seznam, funkce a balíku objeví v **Průzkumníku řešení**.

## <a name="add-an-event-receiver"></a>Přidat příjemce událostí

V seznamu úkolů, můžete přidat příjemce událostí, který automaticky nastaví splatnosti datum a popis úlohy. Následující postup obslužnou rutinu jednoduchá událost přidá do seznamu instance jako přijímače událostí.

1. Otevřete místní nabídce uzlu projektu, zvolte **přidat**a potom zvolte **novou položku**.

2. V seznamu šablon služby SharePoint, vyberte **příjemce událostí** šablony a pojmenujte ji **ProjectTaskListEventReceiver**.

     **Průvodce vlastním nastavením SharePoint** se zobrazí.

3. Na **zvolte nastavení příjemce událostí** vyberte **události položky seznamu** jako typ příjemce událostí v **jaký typ příjemce událostí chcete** seznamu.

4. V **co položka by měl být zdroj události** vyberte **úlohy**.

5. V seznamu událostí pro zpracování, zaškrtněte políčko vedle **přidání položky**a potom zvolte **Dokončit** tlačítko.

     Nový uzel příjemce událostí se přidá do projektu s souboru kódu, který je pojmenován **ProjectTaskListEventReceiver**.

6. Přidejte kód, který `ItemAdded` metoda v **ProjectTaskListEventReceiver** souboru kódu. Úlohy pokaždé, když se přidá novou úlohu, se přidá výchozí datum splatnosti a popis. Výchozí hodnota z důvodu datum je 1. července 2009.

     [!code-vb[SPProjectTaskList#1](../sharepoint/codesnippet/VisualBasic/projecttasklist1/projecttasklisteventreceiver/projecttasklisteventreceiver.vb#1)]
     [!code-csharp[SPProjectTaskList#1](../sharepoint/codesnippet/CSharp/projecttasklist/projecttasklisteventreceiver/projecttasklisteventreceiver.cs#1)]

## <a name="customize-the-project-task-list-feature"></a>Přizpůsobení funkce seznamu úkolů projektu

Když vytvoříte řešení služby SharePoint, Visual Studio automaticky vytvoří funkce pro výchozí položky projektu. Nastavení seznamu úkolů projektu pro web služby SharePoint můžete přizpůsobit pomocí návrháře funkce.

1. V **Průzkumníku řešení**, rozbalte položku **funkce**.

2. Otevřete místní nabídku pro **Feature1**a potom zvolte **Návrhář zobrazení**.

3. V **název** zadejte **funkce seznamu úkolů projektu**.

4. V **oboru** vyberte **webové**.

5. V **vlastnosti** okno, zadejte **1.0.0.0** hodnotu **verze** vlastnost.

## <a name="customize-the-project-task-list-package"></a>Přizpůsobení balíčku seznamu úkolů projektu

Při vytváření projektu služby SharePoint, Visual Studio automaticky přidá funkce, které obsahují položky projektu výchozí do balíčku. Nastavení seznamu úkolů projektu pro web služby SharePoint můžete přizpůsobit pomocí návrháře balíčků.

1. V **SolutionExplorer**, otevřete místní nabídku pro **balíček**a potom zvolte **Návrhář zobrazení**.

2. V **název** zadejte **ProjectTaskListPackage**.

3. Vyberte **resetovat Webový Server** zaškrtávací políčko.

## <a name="build-and-test-the-project-task-list"></a>Vytvoření a testování seznamu úkolů projektu

Když spouštíte projekt, otevře se web služby SharePoint. Ručně však přejděte do umístění seznamu úkolů.

1. Vyberte **F5** klíč k vytváření a nasazování seznamu úkolů projektu.

     Otevře se stránka serveru SharePoint.

2. Vyberte **Domů** kartě.

3. V levém bočním panelu, vyberte **seznamu úkolů projektu** odkaz.

     Zobrazí se stránka seznamu úkolů projektu.

4. V **nástroje seznamu** , zvolte **položky** kartě.

5. V **položky** skupiny, vyberte **nová položka** tlačítko.

6. V **název** textové pole, zadejte **Task1**.

7. Vyberte **Uložit** tlačítko.

     Po aktualizaci lokality **Task1** úkol se zobrazí termínu splnění 7/1/2009.

8. Zvolte **Task1**.

     Zobrazí se v podrobném zobrazení úlohy a popis zobrazuje "Toto je kritické úlohy."

## <a name="deploy-the-project-task-list"></a>Nasazení seznamu úkolů projektu

Po vytvoření a testování seznamu úkolů projektu, abyste ji mohli nasadit na *místní systém* nebo *vzdáleného systému*. Místní systém je do stejného počítače, na kterém vyvinutá řešení, zatímco vzdáleného systému je do jiného počítače.

### <a name="to-deploy-the-project-task-list-to-the-local-system"></a>K nasazení seznamu úkolů projektu do místního systému

Na panelu nabídek Visual Studio zvolte **sestavení** > **nasadit řešení**.

Visual Studio recykluje fond aplikací služby IIS, odvolá všechny existující verze řešení, zkopíruje balíčku řešení (*WSP*) souboru do služby SharePoint a potom aktivuje její funkce. Teď můžete použít řešení ve službě SharePoint. Další informace o postupu konfigurace nasazení najdete v tématu [postupy: Úprava konfigurace nasazení služby SharePoint](../sharepoint/how-to-edit-a-sharepoint-deployment-configuration.md).

### <a name="to-deploy-the-project-task-list-to-a-remote-system"></a>K nasazení seznamu úkolů projektu do vzdáleného systému

1. Na panelu nabídek Visual Studio zvolte **sestavení** > **publikovat**.

2. V **publikovat** dialogovém okně vyberte **publikovat do systému souborů** tlačítko.

     Můžete změnit v cílovém umístění **publikovat** dialogové okno tak, že zvolíte tlačítko se třemi tečkami ![ikonu třemi tečkami](../sharepoint/media/ellipsisicon.gif "ikonu třemi tečkami") a potom přejdete do jiného umístění.

3. Vyberte **publikovat** tlačítko.

     A *WSP* soubor se vytvoří pro řešení.

4. Kopírování *WSP* souboru do vzdáleného systému SharePoint.

5. Pomocí prostředí PowerShell `Add-SPUserSolution` příkaz k instalaci balíčku na vzdálenou instalaci služby SharePoint. (Pro řešení ve farmách, použijte `Add-SPSolution` příkaz.)

     Například `Add-SPUserSolution C:\MyProjects\ProjectTaskList\ProjectTaskList\bin\Debug\ProjectTaskList.wsp`.

6. Pomocí prostředí PowerShell `Install-SPUserSolution` příkaz k nasazení řešení. (Pro řešení ve farmách, použijte `Install-SPSolution` příkaz.)

     Například `Install-SPUserSolution -Identity ProjectTaskList.wsp -Site http://NewSiteName`.

     Další informace o vzdálené nasazení najdete v tématu [pomocí řešení](http://go.microsoft.com/fwlink/?LinkId=217680) a [přidání a nasazení řešení pomocí prostředí PowerShell v produktu SharePoint 2010](http://go.microsoft.com/fwlink/?LinkId=217682).

## <a name="next-steps"></a>Další kroky

Další informace o tom, jak přizpůsobit a nasadit řešení služby SharePoint z v následujících tématech:

- [Návod: Vytvoření sloupce webu, typu obsahu a seznamu pro službu SharePoint](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md)

- [Postupy: vytvoření přijímače událostí](../sharepoint/how-to-create-an-event-receiver.md)

- [Prostředí Windows PowerShell pro SharePoint Server 2010](http://go.microsoft.com/fwlink/?LinkId=217684)

## <a name="see-also"></a>Viz také:
[Zabalení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)
