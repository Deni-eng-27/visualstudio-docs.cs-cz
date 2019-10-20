---
title: Řešení potíží s poškozenými odkazy | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: troubleshooting
helpviewer_keywords:
- Visual C# projects, references
- Visual Basic projects, references
- troubleshooting references
- referencing files from projects
- referencing components, troubleshooting
ms.assetid: 00a9ade9-652e-40de-8ada-85f63cd183ee
caps.latest.revision: 18
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: a1dd1312fc5728fbb68994fb6e70e253fa19172e
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72654790"
---
# <a name="troubleshooting-broken-references"></a>Řešení potíží s poškozenými odkazy
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pokud se vaše aplikace pokusí použít poškozený odkaz, je vygenerována chyba výjimky. Neschopnost najít odkazovanou komponentu je primární Trigger pro chybu, ale existuje několik situací, ve kterých může být odkaz považován za poškozený. Tyto instance jsou uvedené v následujícím seznamu:

- Odkazovaná cesta k projektu je nesprávná nebo neúplná.

- Odkazovaný soubor byl odstraněn.

- Odkazovaný soubor byl přejmenován.

- Připojení k síti nebo ověřování se nezdařilo.

- Odkaz je na komponentu modelu COM, která není v počítači nainstalována.

  Níže jsou uvedená opatření pro tyto problémy.

> [!NOTE]
> Soubory v sestaveních jsou odkazovány pomocí absolutních cest v souboru projektu. Proto je možné, že uživatelé, kteří pracují ve více vývojářích prostředí, mají v místním prostředí chybějící odkazované sestavení. Aby nedocházelo k těmto chybám, je lepší v těchto případech přidat odkazy z projektu na projekt. Další informace naleznete v tématu [NIB postupy: Přidání nebo odebrání odkazů pomocí dialogového okna Přidat odkaz](https://msdn.microsoft.com/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) a [programování se sestaveními](https://msdn.microsoft.com/library/25918b15-701d-42c7-95fc-c290d08648d6).

## <a name="reference-path-is-incorrect"></a>Cesta odkazu není správná.
 Pokud jsou projekty sdíleny v různých počítačích, některé odkazy nemusí být nalezeny, pokud je komponenta umístěna v jiném adresáři v každém počítači. Odkazy jsou uloženy pod názvem souboru komponenty (například MyComponent). Když je do projektu přidán odkaz, umístění složky souboru komponenty (například C:\MyComponents \\) je připojeno k vlastnosti projektu **ReferencePath** .

 Po otevření projektu se pokusí vyhledat tyto soubory odkazované součásti hledáním v adresářích v cestě reference. Pokud je projekt otevřen v počítači, který ukládá komponentu do jiného adresáře, například D:\MyComponents \\, odkaz nelze najít a v Seznam úkolů se zobrazí chyba.

 Chcete-li tento problém vyřešit, můžete poškozený odkaz odstranit a pak ho nahradit pomocí dialogového okna Přidat odkaz. Dalším řešením je použít položku **referenční cesty** na stránkách vlastností projektu a upravit složky v seznamu tak, aby odkazovaly na správná umístění. Vlastnost **cesty odkazů** je u každého uživatele na každém počítači trvalá. Proto změna referenční cesty nemá vliv na ostatní uživatele projektu.

> [!TIP]
> Odkazy z projektu na projekt nemají tyto problémy. Z tohoto důvodu použijte místo odkazů na soubory, pokud je to možné.

#### <a name="to-fix-a-broken-project-reference-by-correcting-the-reference-path"></a>Oprava poškozeného odkazu na projekt opravou cesty reference

1. V **Průzkumník řešení**klikněte pravým tlačítkem myši na uzel projektu a klikněte na příkaz **vlastnosti**.

2. Zobrazí se **Návrhář projektu** .

3. Pokud používáte Visual Basic, vyberte stránku **odkazy** a klikněte na tlačítko odkazy na **cesty** . V dialogovém okně **cesty k odkazům** zadejte cestu ke složce, která obsahuje položku, na kterou chcete odkazovat, v poli **Složka** a pak klikněte na tlačítko **Přidat složku** .

     -nebo-

     Pokud používáte vizuál C#, vyberte stránku **cesty odkazů** . Do pole **Složka** zadejte cestu ke složce obsahující položku, na kterou chcete odkazovat, a poté klikněte na tlačítko **Přidat složku** .

## <a name="referenced-file-has-been-deleted"></a>Odkazovaný soubor byl odstraněn.
 Je možné, že se soubor, na který se odkazuje, odstranil a na jednotce už neexistuje.

#### <a name="to-fix-a-broken-project-reference-for-a-file-that-no-longer-exists-on-your-drive"></a>Oprava poškozeného odkazu na projekt pro soubor, který již na jednotce neexistuje

- Odstraňte odkaz.

- Pokud odkaz existuje v jiném umístění v počítači, přečtěte si ho z tohoto umístění.

- Další informace naleznete v tématu [NIB postupy: Přidání nebo odebrání odkazů pomocí dialogového okna Přidat odkaz](https://msdn.microsoft.com/3bd75d61-f00c-47c0-86a2-dd1f20e231c9).

## <a name="referenced-file-has-been-renamed"></a>Odkazovaný soubor byl přejmenován.
 Je možné, že odkazovaný soubor byl přejmenován.

#### <a name="to-fix-a-broken-reference-for-a-file-that-has-been-renamed"></a>Oprava poškozeného odkazu na soubor, který byl přejmenován

- Odstraňte odkaz a pak přidejte odkaz na přejmenovaný soubor.

- Pokud odkaz existuje v jiném umístění v počítači, budete ho muset číst z tohoto umístění. Další informace naleznete v tématu [NIB postupy: Přidání nebo odebrání odkazů pomocí dialogového okna Přidat odkaz](https://msdn.microsoft.com/3bd75d61-f00c-47c0-86a2-dd1f20e231c9).

## <a name="network-connection-or-authentication-has-failed"></a>Připojení k síti nebo ověřování se nezdařilo.
 Může existovat celá řada možných příčin nepřístupných souborů: chybné síťové připojení nebo neúspěšné ověření, například. Každá příčina může mít jedinečný způsob obnovení; Například může být nutné požádat o přístup k požadovaným prostředkům místního správce. Odstranění odkazu a oprava kódu, který ho použil, je vždycky možnost. Další informace naleznete v tématu [NIB postupy: Přidání nebo odebrání odkazů pomocí dialogového okna Přidat odkaz](https://msdn.microsoft.com/3bd75d61-f00c-47c0-86a2-dd1f20e231c9).

## <a name="com-component-is-not-installed-on-computer"></a>Součást COM není v počítači nainstalována.
 Pokud uživatel přidal odkaz na komponentu COM a druhý uživatel se pokusí spustit kód v počítači, na kterém není tato součást nainstalována, obdrží druhý uživatel chybu, že odkaz je přerušen. Při instalaci komponenty na druhý počítač se chyba opraví. Další informace o tom, jak používat odkazy na komponenty modelu COM v projektech, naleznete v tématu [interoperabilita modelu COM v .NET Frameworkch aplikacích](https://msdn.microsoft.com/library/f5a72143-c268-4dff-a019-974ad940e17d).

## <a name="see-also"></a>Viz také
 [Úvod do stránky odkazy Návrháře projektu](https://msdn.microsoft.com/898dd854-c98d-430c-ba1b-a913ce3c73d7) [, návrháře projektu (Visual Basic)](../ide/reference/references-page-project-designer-visual-basic.md) [NIB postupy: Přidání nebo odebrání odkazů pomocí dialogového okna Přidat odkaz](https://msdn.microsoft.com/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)
