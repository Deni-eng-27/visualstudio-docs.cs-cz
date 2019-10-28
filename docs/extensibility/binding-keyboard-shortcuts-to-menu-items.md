---
title: Vázání klávesových zkratek k položkám nabídky | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- keyboard command
- keyboards
- command key
- keyboard shortcuts
- menu items
ms.assetid: 19f483b6-4d3e-424e-9d68-dc129c788e47
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 98c0b6f5b26e7f423f2a89f680395ceaba7286bc
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/28/2019
ms.locfileid: "72982275"
---
# <a name="bind-keyboard-shortcuts-to-menu-items"></a>Vázání klávesových zkratek k položkám nabídky
Chcete-li vytvořit novou klávesovou zkratku pro vlastní příkaz nabídky, stačí přidat položku do souboru *. vsct* pro balíček. Toto téma vysvětluje, jak namapovat klávesovou zkratku na vlastní tlačítko, položku nabídky nebo příkaz panelu nástrojů a jak použít mapování klávesnice ve výchozím editoru nebo omezit na vlastní editor.

 Chcete-li přiřadit klávesové zkratky existujícím položkám nabídky sady Visual Studio, přečtěte si téma [identifikace a přizpůsobení klávesových zkratek](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md).

## <a name="choose-a-key-combination"></a>Zvolit kombinaci kláves
 V aplikaci Visual Studio se již používá mnoho klávesových zkratek. Neměli byste přiřadit stejný zástupce více než jednomu příkazu, protože duplicitní vazby je obtížné detekovat a mohou také způsobovat nepředvídatelné výsledky. Proto je vhodné před přiřazením ověřit dostupnost zástupce.

### <a name="to-verify-the-availability-of-a-keyboard-shortcut"></a>Ověření dostupnosti klávesové zkratky

1. V okně **nástroje** > **Možnosti** > **prostředí** vyberte možnost **klávesnice**.

2. Ujistěte se, že je **Nový zástupce v** sadě nastavený na **globální**.

3. V poli **klávesových zkratek klávesových zkratek** zadejte klávesovou zkratku, kterou chcete použít.

    Pokud je zástupce již použit v aplikaci Visual Studio, **zástupce aktuálně používaný** v poli zobrazí příkaz, který zástupce aktuálně volá.

4. Vyzkoušejte různé kombinace klíčů, dokud nezjistíte, která z nich není namapovaná.

   > [!NOTE]
   > Klávesové zkratky, které používají **ALT** , můžou otevřít nabídku a ne přímo spustit příkaz. Proto může být **zástupce aktuálně používaný v** boxu při psaní zástupce, který obsahuje **ALT**, prázdný. Můžete ověřit, že zástupce neotevře nabídku zavřením dialogového okna **Možnosti** a následným stisknutím kláves.

   Následující postup předpokládá, že máte existující VSPackage s příkazem nabídky. Pokud k tomu potřebujete pomoc, podívejte se na [Vytvoření rozšíření pomocí příkazu nabídky](../extensibility/creating-an-extension-with-a-menu-command.md).

### <a name="to-assign-a-keyboard-shortcut-to-a-command"></a>Přiřazení klávesové zkratky k příkazu

1. Otevřete soubor *. vsct* pro váš balíček.

2. Po `<Commands>`, pokud ještě neexistuje, vytvořte prázdný oddíl `<KeyBindings>`.

   > [!WARNING]
   > Další informace o vazbách klíčů naleznete v tématu [Binding](../extensibility/keybinding-element.md).

    V části `<KeyBindings>` vytvořte položku `<KeyBinding>`.

    Nastavte atributy `guid` a `id` na hodnoty příkazu, který chcete vyvolat.

    Nastavte atribut `mod1` pro **řízení**, **ALT**nebo **SHIFT**.

    Oddíl vazeb klíčů by měl vypadat přibližně takto:

   ```xml
   <KeyBindings>
       <KeyBinding guid="<name of command set>" id="<name of command id>"
           editor="guidVSStd97" key1="1" mod1="CONTROL"/>
   </KeyBindings>

   ```

   Pokud vaše klávesová zkratka vyžaduje více než dva klíče, nastavte atributy `mod2` a `key2`.

   Ve většině případů by se **SHIFT** neměl používat bez druhého modifikátoru, protože jeho stisknutí má za následek, že většina alfanumerických klíčů zapíše velké písmeno nebo symbol.

   Kódy virtuálních klíčů umožňují přístup ke speciálním klíčům, ke kterým není přiřazen znak, například klávesy funkcí a klávesa **BACKSPACE** . Další informace najdete v tématu [kódy virtuálních klíčů](/windows/desktop/inputdev/virtual-key-codes).

   Chcete-li příkaz zpřístupnit v editoru sady Visual Studio, nastavte atribut `editor` na hodnotu `guidVSStd97`.

   Chcete-li, aby byl příkaz dostupný pouze ve vlastním editoru, nastavte atribut `editor` na název vlastního editoru vygenerovaného šablonou [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] při vytváření balíčku VSPackage, který obsahuje vlastní editor. Chcete-li zjistit hodnotu názvu, vyhledejte v sekci `<Symbols>` `<GuidSymbol>` uzel, jehož atribut `name` končí na "`editorfactory`". Toto je název vlastního editoru.

## <a name="example"></a>Příklad
 Tento příklad váže klávesovou zkratku **Ctrl**+**ALT**+**C** k příkazu s názvem `cmdidMyCommand` v balíčku s názvem `MyPackage`.

```
<CommandTable>
. . .
<Commands>
. . .
</Commands>
<KeyBindings>
  <KeyBinding guid="guidMyPackageCmdSet" id="cmdidMyCommand"
      key1="C" mod1="CONTROL" mod2="ALT" editor="guidVSStd97" />
</KeyBindings>
. . .
</CommandTable>
```

## <a name="example"></a>Příklad
 Tento příklad váže klávesovou zkratku **Ctrl**+**B** k příkazu s názvem `cmdidBold` v projektu s názvem `TestEditor`. Příkaz je k dispozici pouze ve vlastním editoru, nikoli v jiných editorech.

```xml
<KeyBinding guid="guidVSStd97" id="cmdidBold" editor="guidTestEditorEditorFactory" key1="B" mod1="Control" />
```

## <a name="see-also"></a>Viz také:
- [Rozšiřování nabídek a příkazů](../extensibility/extending-menus-and-commands.md)