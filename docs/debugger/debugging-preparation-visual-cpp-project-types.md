---
title: Příprava na ladění C++ projektů | Microsoft Docs
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- project templates, debugging
- C++ projects, debugging
- debug builds, project settings
- debugging [C++]
ms.assetid: 912b4ba2-7719-43d5-b087-db33e3f9329a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: 9c7d223b9ea542177176045c9abd103958e5ae33
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2019
ms.locfileid: "72738116"
---
# <a name="debugging-preparation-c-project-types"></a>Příprava ladění: C++ typy projektů
Tato část popisuje, jak ladit základní typy projektů vytvořené pomocí šablon projektů [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)].

 Všimněte si, že tyto typy projektů, které vytváří knihovny DLL jako výstup, byly seskupeny do [projektů ladění dll](../debugger/debugging-dll-projects.md) z důvodu společných funkcí, které sdílí.

## <a name="BKMK_In_this_topic"></a>V tomto tématu
 [Doporučené nastavení vlastností](#BKMK_Recommended_Property_Settings)

 [Projekty Win32](#BKMK_Win32_Projects)

- [Ladění aplikace C nebo C++ Win32](#BKMK_To_debug_a_C_or_C___Win32_application)

- [Ruční nastavení konfigurace ladění](#BKMK_To_manually_set_a_Debug_configuration)

  [Model Windows Forms aplikace (.NET)](#BKMK_Windows_Forms_Applications___NET_)

## <a name="BKMK_Recommended_Property_Settings"></a>Doporučené nastavení vlastností
 Některé vlastnosti by měly být nastavené stejným způsobem pro všechny nespravované scénáře ladění. V následujících tabulkách se zobrazí doporučená nastavení vlastností. Nastavení, které zde nejsou uvedeny, se může lišit mezi různými nespravovanými typy projektů. Další informace naleznete v tématu [nastavení projektu pro konfiguraci C++ ladění](../debugger/project-settings-for-a-cpp-debug-configuration.md).

### <a name="configuration-properties-124-cc-124-optimization-node"></a>Konfigurační uzel &#124; C/C++ &#124; optimalizace – vlastnosti

|Název vlastnosti|Nastavením|
|-------------------|-------------|
|**Vybrané**|Nastaveno na **disabled (/0d).** Optimalizovaný kód je těžší ladit, protože vygenerované pokyny neodpovídají přímo vašemu zdrojovému kódu. Pokud zjistíte, že váš program obsahuje chybu, která se zobrazí pouze v optimalizovaném kódu, můžete toto nastavení zapnout, ale mějte na paměti, že kód zobrazený v okně **zpětný překlad** je vygenerován z optimalizovaného zdroje, který se nemusí shodovat s tím, co vidíte ve vašich zdrojových oknech. Další funkce, například krokování, se nemusí chovat podle očekávání.|

### <a name="configuration-properties-124-linker-124-debugging-node"></a>Vlastnosti &#124; konfigurace uzel &#124; ladění linkeru

|Název vlastnosti|Nastavením|
|-------------------|-------------|
|**Generovat ladicí informace**|Tuto možnost byste měli vždycky nastavit na **Ano (/debug)** a vytvořit tak symboly ladění a soubory potřebné pro ladění. Když aplikace přejde do produkčního prostředí, můžete ji nastavit na vypnuto.|

 [V tomto tématu](../debugger/debugging-preparation-visual-cpp-project-types.md#BKMK_In_this_topic)

## <a name="BKMK_Win32_Projects"></a>Projekty Win32
 Aplikace Win32 jsou tradiční programy pro Windows napsané v C++jazyce C nebo. Ladění tohoto typu aplikace v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] je jednoduché.

 Aplikace Win32 zahrnují MFC aplikace a projekty ATL. Používají rozhraní API systému Windows a mohou používat knihovnu MFC nebo ATL, ale nepoužívají modul CLR (Common Language Runtime). Mohou však volat spravovaný kód, který používá CLR.

 Následující postup vysvětluje, jak ladit projekt Win32 z aplikace [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Dalším způsobem, jak ladit aplikaci Win32, je spustit aplikaci mimo [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a připojit k ní. Další informace najdete v tématu [připojení ke spuštěným procesům](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).

### <a name="BKMK_To_debug_a_C_or_C___Win32_application"></a>Ladění aplikace C nebo C++ Win32

1. Otevřete projekt v aplikaci Visual Studio.

2. V nabídce **ladit** klikněte na tlačítko **Spustit**.

3. Ladění pomocí technik popsaných v [části první pohled na ladicí program](../debugger/debugger-feature-tour.md).

### <a name="BKMK_To_manually_set_a_Debug_configuration"></a>Ruční nastavení konfigurace ladění

1. V nabídce **zobrazení** klikněte na položku **stránky vlastností**.

2. Kliknutím na uzel **Vlastnosti konfigurace** ho otevřete, pokud ještě není.

3. Vyberte **Obecné**a nastavte hodnotu **výstupního** řádku na **ladit**.

4. Otevřete uzel **C/C++**  a vyberte **Obecné**.

    V řádku **ladění** zadejte typ ladicích informací, které mají být generovány kompilátorem. Hodnoty, které můžete zvolit zahrnout **databázi programu (/Zi)** nebo **databáze programu pro upravit & pokračovat (/Zi)**

5. Vyberte možnost **optimalizace**a v řádku **optimalizace** v rozevíracím seznamu vyberte možnost **zakázáno (/0d)** .

    Optimalizovaný kód je těžší ladit, protože vygenerované pokyny neodpovídají přímo vašemu zdrojovému kódu. Pokud zjistíte, že váš program obsahuje chybu, která se zobrazí pouze v optimalizovaném kódu, můžete toto nastavení zapnout, ale mějte na paměti, že kód zobrazený v okně zpětný překlad je vygenerován z optimalizovaného zdroje, který se nemusí shodovat s tím, co vidíte ve vašich zdrojových oknech. Funkce, jako je například krokování, budou zřejmě zobrazovat zarážky a bod provádění nesprávně.

6. Otevřete uzel **linker** a vyberte **ladění**. V prvním **vygenerovaném** řádku vyberte v rozevíracím seznamu **Ano (/debug)** . Tuto hodnotu vždy nastavte při ladění.

   Další informace naleznete v tématu[nastavení projektu pro konfiguraci C++ ladění](../debugger/project-settings-for-a-cpp-debug-configuration.md).

   [V tomto tématu](../debugger/debugging-preparation-visual-cpp-project-types.md#BKMK_In_this_topic)

## <a name="BKMK_Windows_Forms_Applications___NET_"></a>Model Windows Forms aplikace (.NET)
 Šablona **aplikace model Windows Forms (.NET)** vytvoří [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] model Windows Forms aplikaci. Další informace najdete v tématu [Postupy: vytvoření projektu aplikace pro systém Windows](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/42wc9kk5(v=vs.100)).

 Ladění tohoto typu aplikace v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] je podobné jako u spravovaných aplikací model Windows Forms.

 Při vytváření projektu model Windows Forms se šablonou projektu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] automaticky vytvoří požadované nastavení pro ladění a vydání. V případě potřeby můžete tato nastavení změnit v dialogovém okně **\<project název > stránky vlastností** . Další informace najdete v tématu [Konfigurace ladění a vydání](../debugger/how-to-set-debug-and-release-configurations.md).

 Další informace naleznete v tématu [nastavení projektu pro konfiguraci C++ ladění](../debugger/project-settings-for-a-cpp-debug-configuration.md).

 Dalším způsobem, jak ladit aplikaci model Windows Forms, je spustit aplikaci mimo [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a připojit k ní. Další informace najdete v tématu [připojení ke spuštěnému programu nebo více programům](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).

 [V tomto tématu](../debugger/debugging-preparation-visual-cpp-project-types.md#BKMK_In_this_topic)

## <a name="see-also"></a>Viz také:
- [První seznámení s ladicím programem](../debugger/debugger-feature-tour.md)
- [Nastavení projektu pro konfiguraci ladění jazyka C++](../debugger/project-settings-for-a-cpp-debug-configuration.md)
- [Připojení ke spuštěnému programu nebo více programům](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)
- [Konfigurace ladění a vydaných verzí](../debugger/how-to-set-debug-and-release-configurations.md)
- [Postupy: vytvoření projektu aplikace pro systém Windows](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/42wc9kk5(v=vs.100))