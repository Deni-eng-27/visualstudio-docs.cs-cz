---
title: "Visual Studio Tools for Unity Azure návod datový Model | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6FCCA8D1-0D06-4B2A-A55F-FC3D1FEA0F56
author: dantogno
ms.author: v-davian
manager: crdun
ms.openlocfilehash: e3b6064a3947f57ffcbe6422162c6c72fca0ab21
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="create-data-model-classes"></a>Vytvořit datové třídy modelu

Projekt Unity musí obsahovat třídy modelu dat, které odpovídají s tabulkami vytvořené v back-end mobilní aplikace Azure.

## <a name="create-the-crashinfo-class"></a>Vytvořte třídu CrashInfo

1. V Unity, přidejte novou složku v kořenovém **prostředky** adresář s názvem **skripty**. Uvnitř do nové složky skriptů vytvořit jinou novou složku s názvem **datové modely**. Toto je pouze organizace.

2. Ve složce nové datové modely, vytvořte nový skript jazyka C# s názvem **CrashInfo**.

3. Otevřete nový `CrashInfo` skriptu, odstraňte všechny šablony kód, včetně deklaraci třídy a pomocí příkazů a přidejte následující:

  ```csharp
  public class CrashInfo
  {
      public string Id { get; set; }
      public float X { get; set; }
      public float Y { get; set; }
      public float Z { get; set; }
  }
  ```

  > [!WARNING]
  > Návod fungovala správně musí název třídy datového modelu odpovídal názvu tabulky snadno vytvořit na back-end mobilní aplikace Azure.

## <a name="create-the-highscoreinfo-class"></a>Vytvořte třídu HighScoreInfo

1. Ve složce datové modely, vytvořte nový skript jazyka C# s názvem **HighScoreInfo**.

2. Otevřete nový `HighScoreInfo` skriptu, odstraňte všechny šablony kód, včetně deklaraci třídy a pomocí příkazů a přidejte následující:

  ```csharp
  public class HighScoreInfo
  {
      public string Name { get; set; }
      public float Time { get; set; }
      public string Id { get; set; }
  }
  ```

  ## <a name="next-step"></a>Další krok

  * [Implementace Azure MobileServiceClient](visual-studio-tools-for-unity-azure-mobile-client.md)
