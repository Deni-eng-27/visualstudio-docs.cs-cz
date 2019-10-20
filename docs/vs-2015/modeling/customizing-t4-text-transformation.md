---
title: Přizpůsobení transformace textu T4 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- text templates, API
- text templates, custom hosts
ms.assetid: 62cd9a3c-a6e1-4b29-93f5-f2a0cf47dc92
caps.latest.revision: 30
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 71cec79acfcc934f9ddd910006f32f5207b26c84
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72654970"
---
# <a name="customizing-t4-text-transformation"></a>Přizpůsobení transformace textu T4
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Textové šablony jsou funkcí [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], které umožňují generovat kód programu nebo jiné textové soubory pomocí transformačního procesu. Pomocí [!INCLUDE[vssdk_current_short](../includes/vssdk-current-short-md.md)] můžete roztáhnout výchozí proces transformace šablony přizpůsobením procesoru direktivy textové šablony nebo hostitele textové šablony.

## <a name="in-this-section"></a>V tomto oddílu
 [Proces transformace textové šablony](../modeling/the-text-template-transformation-process.md) Popisuje, jak transformace textu funguje a vysvětluje roli hostitele šablony a procesory direktiv.

 [Vytváření vlastních procesorů pro direktivy textových šablon T4](../modeling/creating-custom-t4-text-template-directive-processors.md) Procesor direktiv zpracovává direktivy ve vaší šabloně, například `<#@template#>.` spouští během kompilování šablony a může načítat sestavení a další prostředky. Může také vkládat kód, který načte prostředky za běhu. Definováním vlastního procesoru direktiv můžete snížit složitost svých šablon.

 [Vyvolání transformace textu v rozšíření vs](../modeling/invoking-text-transformation-in-a-vs-extension.md) Pokud píšete rozšíření [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], jako je například příkaz nabídky nebo obslužná rutina události, může vaše rozšíření použít službu šablonování textu k transformaci jakékoli textové šablony. Do šablony můžete předat data parametrů pomocí objektu Session a získat hodnoty ze šablony pomocí direktivy `<#@parameter#>`.

 [Zpracování textových šablon pomocí vlastního hostitele](../modeling/processing-text-templates-by-using-a-custom-host.md) Když se spustí kód textové šablony, hostitel poskytne přístup k externím souborům a stavu aplikace. Například hostitel, který spouští transformace textu v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] může poskytnout přístup k Průzkumníku řešení. Zobrazuje také chyby v okně chybové zprávy. Pokud chcete spouštět transformace textu v jiném kontextu, můžete definovat vlastního hostitele, který poskytuje přístup k dostupným službám v daném kontextu.

 Pokud píšete rozšíření [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], zvažte použití existující služby transformace textu namísto psaní vlastního hostitele. Další informace najdete v tématu [vyvolání transformace textu v rozšíření vs](../modeling/invoking-text-transformation-in-a-vs-extension.md).

## <a name="reference"></a>Odkaz
 [Zápis textové šablony T4](../modeling/writing-a-t4-text-template.md)

 Poskytuje syntaxi direktiv textových šablon a řídicích bloků.
