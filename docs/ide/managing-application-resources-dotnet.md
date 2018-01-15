---
title: "Správa prostředků aplikace (.NET) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- msvse_resedit.dlg.SetCustomTool
- msvse_settingsdesigner.err.formatvalue
- msvse_resedit.err.nameblank
- msvse_resedit.err.duplicatename
helpviewer_keywords:
- Resource Designer
- resources [Visual Studio]
- Resources page in Project Designer
- application resources [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 2006f565edbca8a859cd2c155645e47e083b5528
ms.sourcegitcommit: 11740fed01cc602252ef698aaa11c07987b00570
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/12/2018
---
# <a name="managing-application-resources-net"></a>Správa prostředků aplikace (.NET)

Soubory prostředků jsou soubory, které jsou součástí aplikace, ale nejsou kompilovány, pro soubory ikon příklad nebo zvukových souborů. Vzhledem k tomu, že tyto soubory nejsou součástí procesu kompilace, můžete je změnit bez nutnosti její kompilace vaší binární soubory. Pokud máte v úmyslu lokalizaci vaší aplikace, používejte zdrojové soubory pro všechny řetězce a další prostředky, které se musí změnit při lokalizaci berte vaší aplikace.

Další informace o prostředcích v aplikacích klasické pracovní plochy rozhraní .NET najdete v tématu [prostředků v aplikacích plochy](/dotnet/framework/resources/index).

## <a name="working-with-resources"></a>Práci s prostředky

V projektu spravovaného kódu otevřete okno Vlastnosti projektu. Buď můžete otevřít okno Vlastnosti:

- pravým tlačítkem myši na uzel projektu v **Průzkumníku řešení** a výběrem **vlastnosti**
- zadáním "projektu vlastnosti" v **Snadné spuštění** okna
- Výběr **Alt**+**Enter** v **Průzkumníku řešení** okna

Vyberte **prostředky** kartě. Pokud projekt není obsahovat jeden již, přidat a odstranit různé druhy prostředků a upravit stávající prostředky, můžete přidat souboru RESX.

## <a name="resources-in-other-project-types"></a>Prostředky v jiné typy projektu

Prostředky se spravují jinak v rozhraní .NET projektů než jiné typy projektů. Další informace o prostředcích v:

- Univerzální platformu Windows (UWP) aplikace, najdete v části [prostředky aplikace a systém správy prostředků](/windows/uwp/app-resources/)
- Projekty C++, najdete v části [práce se zdrojovými soubory](/cpp/windows/working-with-resource-files) a [postupy: vytvoření prostředku](/cpp/windows/how-to-create-a-resource)

## <a name="see-also"></a>Viz také

[Prostředky v aplikacích klasické pracovní plochy (rozhraní .NET Framework)](/dotnet/framework/resources/index)