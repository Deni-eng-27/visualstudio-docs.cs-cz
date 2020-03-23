---
title: Zalamování řádků
ms.date: 11/07/2018
ms.topic: conceptual
helpviewer_keywords:
- word wrap
- editors, text viewing
- Code Editor, word wrap
ms.assetid: 442f33ef-9f52-4515-b55f-fb816d664645
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f456a35f4a65438df5229492beb1f3e142e38f05
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2020
ms.locfileid: "79508937"
---
# <a name="how-to-manage-word-wrap-in-the-editor"></a>Postup: Správa zalamování slov v editoru

Můžete nastavit a vymazat možnost **zalamování aplikace Word.** Pokud je tato možnost nastavena, část dlouhého řádku, která přesahuje aktuální šířku okna Editor kódu, se zobrazí na dalším řádku. Pokud je tato možnost například vymazána, abyste usnadnili použití číslování řádků, můžete posunout doprava a zobrazit tak konce dlouhých čar.

> [!NOTE]
> Toto téma platí pouze pro Visual Studio v systému Windows. Visual Studio pro Mac momentálně nepodporuje zalamování řádků.

## <a name="to-set-word-wrap-preferences"></a>Nastavení předvoleb zalamování slov

1. V nabídce **Tools** (Nástroje) vyberte **Options** (Možnosti).

2. Ve složce **Textový editor** zvolte **obecné** možnosti v podsložce **Všechny jazyky,** chcete-li tuto možnost nastavit globálně.

     — nebo —

     Zvolte **obecné** možnosti v podsložce pro jazyk, ve kterém programujete.

3. V části **Nastavení**vyberte nebo zrušte zaškrtnutí možnosti **zalamování aplikace Word.**

     Když je vybraná volba **zalamování aplikace Word,** je povolena volba **Zobrazit vizuální glyfy pro zalamování řádků.**

4. Vyberte volbu **Zobrazit vizuální glyfy pro zalamování řádků,** pokud dáváte přednost zobrazení indikátoru návratové šipky, kde se dlouhá čára zalomí na druhý řádek. Zrušte zaškrtnutí této možnosti, pokud nechcete zobrazovat šipky indikátorů.

    > [!NOTE]
    > Tyto šipky připomenutí nejsou přidány do kódu; jsou pouze pro účely zobrazení.

## <a name="known-issues"></a>Známé problémy

Pokud jste obeznámeni s zalamování slov v Poznámkový blok ++, Sublime Text nebo Visual Studio Kód, být vědomi následujících problémů, kde Visual Studio chová odlišně od ostatních editorů:

* [Trojité kliknutí nevybere celý řádek](https://developercommunity.visualstudio.com/content/problem/268989/triple-click-doesnt-select-whole-line-when-word-wr.html)
* [Dvakrát stisknutí klávesy End nepřesune kurzor na konec řádku.](https://developercommunity.visualstudio.com/content/problem/138274/pressing-end-key-twice-should-move-cursor-to-end-o.html)

## <a name="see-also"></a>Viz také

- [Funkce editoru kódu](../../ide/writing-code-in-the-code-and-text-editor.md)
