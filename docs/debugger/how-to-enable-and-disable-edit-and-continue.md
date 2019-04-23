---
title: 'Postupy: Povolení a zákaz operace upravit a pokračovat | Dokumentace Microsoftu'
ms.custom: seodec18
ms.date: 10/04/2018
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- /INCREMENTAL linker option
- Apply Code Changes command
- Edit and Continue, disabling
- code changes, applying in break mode
- INCREMENTAL linker option
- Edit and Continue, enabling
- break mode, applying code changes
- Edit and Continue, applying code changes
- Step command
- Go command
ms.assetid: fd961a1c-76fa-420d-ad8f-c1a6c003b0db
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
- cplusplus
ms.openlocfilehash: b0a10d720e911f80aa5ef7b4a42f521bfd9c31bd
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60070405"
---
# <a name="how-to-enable-and-disable-edit-and-continue-c-vb-c"></a>Postupy: Povolení a zákaz operace upravit a pokračovat (C#, VB, C++)

Můžete zakázat nebo povolit **upravit a pokračovat** v sadě Visual Studio **možnosti** dialogové okno v době návrhu. **Upravit a pokračovat** sestavení lze použít pouze v ladění. Další informace najdete v tématu [upravit a pokračovat](../debugger/edit-and-continue.md).

Pro nativní kód C++ **upravit a pokračovat** vyžaduje použití `/INCREMENTAL` možnost. Další informace o požadavcích na funkci v jazyce C++, naleznete v tomto [blogový příspěvek](https://devblogs.microsoft.com/cppblog/c-edit-and-continue-in-visual-studio-2015-update-3/) a [upravit a pokračovat (Visual C++)](../debugger/edit-and-continue-visual-cpp.md).

**K povolení nebo zakázání funkce upravit a pokračovat:**

1. Pokud jste v relaci ladění, zastavte ladění (**ladění** > **Zastavit ladění** nebo **Shift**+**F5**) .

1. V **nástroje** > **možnosti** > (nebo **ladění** > **možnosti**) > **ladění**  >  **Obecné**vyberte **upravit a pokračovat** v pravém podokně.

    > [!NOTE]
    >  Pokud je povolená technologie IntelliTrace a shromažďovat události IntelliTrace a informace o volání, upravit a pokračovat je zakázané. Další informace najdete v tématu [IntelliTrace](../debugger/intellitrace.md).

1. Pro kód jazyka C++, ujistěte se, že **Povolit nativní editovat a pokračovat** je vybraná a nastavit další možnosti:
    - **Použít změny při pokračování (jenom nativní)**

      Pokud vybraná, Visual Studio automaticky zkompiluje a platí změn kódu, pokud budete pokračovat v ladění ze stavu pozastavení. V opačném případě můžete také použít změny pomocí **ladění** > **použít změny kódu**.

    - **Upozornit na starý kód (pouze nativní)**

      Pokud je vybrána, poskytuje upozornění na starý kód.

1. Klikněte na tlačítko **OK**.
