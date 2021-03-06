---
title: Architektura typů projektů | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], architecture
ms.assetid: 9c1d940f-8a54-41f7-a8aa-c870e324371c
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e53929b1ec2ed9c73191bf16f1cedc84a53b58f2
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80706310"
---
# <a name="project-types-architecture"></a>Architektura typů projektů
Tato část obsahuje podrobné informace o architektuře typů projektů v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] .

## <a name="in-this-section"></a>V tomto oddílu
- [Prvky modelu projektu](../../extensibility/internals/elements-of-a-project-model.md)

 Uvádí služby, které typ projektu může spotřebovat, a rozhraní, které musí implementovat.

- [Základní komponenty modelu projektu](../../extensibility/internals/project-model-core-components.md)

 Popisuje rozhraní typy projektů musí implementovat a volitelně mohou implementovat k poskytnutí dalších funkcí.

- [Kdy vytvořit typy projektů](../../extensibility/internals/when-to-create-project-types.md)

 Pomůže vám určit, kdy je nutné vytvořit typ projektu, a když můžete použít jinou [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] funkci rozšíření, jako jsou VSPackage a editory, abyste dosáhli stejného cíle.

- [Hierarchie a výběr](../../extensibility/internals/hierarchies-and-selection.md)

 Popisuje, jak [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] používá hierarchie a kontext výběru k zajištění konzistentního a zjednodušeného uživatelského prostředí.

## <a name="related-sections"></a>Související oddíly
- [Podtypy projektů](../../extensibility/internals/project-subtypes.md)

 Vysvětluje způsob, jakým podtypy projektů umožňují přizpůsobit chování projektových systémů [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] a [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] .

- [Typy projektů](../../extensibility/internals/project-types.md)

 Poskytuje přehled o projektech jako základních stavebních bloků [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrovaného vývojového prostředí (IDE). Odkazy jsou k dispozici pro další témata, která vysvětlují, jak projekty řídí sestavení a kompilování kódu.
