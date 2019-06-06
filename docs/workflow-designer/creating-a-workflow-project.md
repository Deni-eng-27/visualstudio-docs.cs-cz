---
title: Vytvořit projekt Workflow Foundation
ms.date: 06/25/2018
ms.topic: conceptual
helpviewer_keywords:
- Workflow Designer, creating a workflow project
- creating a workflow project
ms.assetid: 235a125e-ebe7-4a98-bf77-86c8558728fb
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e19ec88a4dec7a13ecc3d77e5d4fc1f04bb114bd
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2019
ms.locfileid: "66747800"
---
# <a name="workflow-project-templates"></a>Šablony projektu pracovního postupu

Pracovní postupy, služby pracovních postupů Windows Communication Foundation (WCF), vlastních aktivit a Návrháři vlastních aktivit můžete vytvořit pomocí šablony projektů Visual Studio. Tento článek popisuje, jak vytvořit knihovny a aplikace pomocí šablony projektu, který je k dispozici v sadě Visual Studio.

## <a name="create-a-workflow-project"></a>Vytvoření projektu pracovního postupu

Visual Studio poskytuje čtyři různé šablony projektu pracovního postupu:

- Konzolová aplikace pracovního postupu

- Aplikace služby pracovního postupu WCF

- Knihovna aktivit

- Knihovna návrháře aktivit

Pro přístup k tyto šablony, nejdřív nainstalovat **Windows Workflow Foundation** komponentu sady Visual Studio. Podrobné pokyny najdete v tématu [nainstalovat Windows Workflow Foundation](developing-applications-with-the-workflow-designer.md#install-windows-workflow-foundation).

1. Po instalaci **Windows Workflow Foundation** komponenty, vyberte **souboru** > **nový** > **projektu**.

1. Vyhledejte a vyberte šablonu projektu pracovního postupu, například, **Konzolová aplikace pracovního postupu** šablony.

1. Pokračujte k vytvoření projektu.

   > [!NOTE]
   > Pokud chcete přidat nový projekt do existujícího řešení, otevřete řešení v sadě Visual Studio, klikněte pravým tlačítkem na řešení v **Průzkumníka řešení**a vyberte **přidat** > **nový Projekt**.

## <a name="workflow-console-app"></a>Konzolová aplikace pracovního postupu

Pokud se rozhodnete **Konzolová aplikace pracovního postupu** šablony, sady Visual Studio vytvoří definici pracovního postupu v XAML. Návrháře postupu provádění se otevře a zobrazí na plátně pro pracovní postup, který jste vytvořili. K vytvoření pracovního postupu, přetáhněte aktivity nebo jiné položky pracovního postupu z **nástrojů** na návrhovou plochu.

## <a name="wcf-workflow-service-app"></a>Aplikace služby pracovního postupu WCF

Pokud se rozhodnete **aplikace služeb pracovního postupu WCF** šablony, sady Visual Studio vytvoří definici služby jako XAML. Otevře se Návrhář pracovního postupu do návrhového zobrazení s <xref:System.Activities.Statements.Sequence> aktivitu, která obsahuje sadu <xref:System.ServiceModel.Activities.Receive> a <xref:System.ServiceModel.Activities.SendReply> aktivity.

## <a name="activity-library"></a>Knihovna aktivit

Pokud se rozhodnete **knihovny aktivit** šablony, sady Visual Studio vytvoří definici aktivity v XAML. Návrhář postupu provádění se otevře a zobrazí na plátně pro vaše vlastní aktivity. Přetáhněte aktivitu z **nástrojů** na návrhovou plochu se zahrnuje do vaší vlastní aktivitě.

> [!NOTE]
> V těle vaší vlastní aktivitě povolená jenom jedna podřízená aktivita. Avšak podřízené aktivity mohou být složené aktivity, například <xref:System.Activities.Statements.Sequence> aktivity nebo <xref:System.Activities.Statements.Flowchart> aktivity.

## <a name="activity-designer-library"></a>Knihovna návrháře aktivit

Pokud se rozhodnete **knihovny návrháře aktivit** šablony, sady Visual Studio vytvoří definici návrháře aktivit v XAML a použití modelu code-behind implementační soubor. Návrháře postupu provádění se otevře a zobrazí na plátně návrháře aktivit. Přetáhněte Windows Presentation Foundation (WPF) ovládacích prvků z **nástrojů** na návrhovou plochu pro použití v Návrháři vaše vlastní aktivity.

Příklad implementace vlastního návrháře aktivit najdete v tématu [jak: Vytvoření vlastního návrháře aktivit](/dotnet/framework/windows-workflow-foundation/how-to-create-a-custom-activity-designer).

> [!NOTE]
> Vlastní návrháři aktivit lze pro vlastní aktivity a výchozí aktivity .NET.

## <a name="see-also"></a>Viz také:

- [Návrhář postupu provádění](developing-applications-with-the-workflow-designer.md)
- [Návrh pracovních postupů (.NET Framework)](/dotnet/framework/windows-workflow-foundation/designing-workflows)