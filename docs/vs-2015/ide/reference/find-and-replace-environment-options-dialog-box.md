---
title: Dialogové okno Najít a nahradit, prostředí, možnosti | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Environment.FindReplace
- VS.ToolsOptionsPages.Environment.FindandReplace
helpviewer_keywords:
- Find and Replace, Options dialog box
- Find and Replace, customizing
ms.assetid: f804d6d5-6309-46e4-8294-b83e880b5ec9
caps.latest.revision: 16
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: c17b25d8a837f751b8bd8ec108c0b821d58c6df0
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "72657695"
---
# <a name="find-and-replace-environment-options-dialog-box"></a>Najít a nahradit, prostředí, dialogové okno Možnosti
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Tato stránka dialogového okna **Možnosti** slouží k řízení oken zpráv a dalších aspektů operace Find a Replace. K tomuto dialogovému oknu se dostanete z nabídky **nástroje** kliknutím na **Možnosti**, rozbalením **prostředí**a kliknutím na **Najít a nahradit**. Pokud se tato stránka v seznamu nezobrazuje, vyberte v dialogovém okně **Možnosti** možnost **Zobrazit všechna nastavení** .

> [!NOTE]
> Možnosti dostupné v dialogových oknech a názvy a umístění příkazů nabídky, které vidíte, se mohou lišit od toho, co je popsáno v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, v nabídce **nástroje** klikněte na položku **Nastavení importu a exportu** . Další informace naleznete v tématu [přizpůsobení nastavení vývoje v aplikaci Visual Studio](https://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní
 **Zobrazit informační zprávy** Tuto možnost vyberte, pokud chcete zobrazit všechny informační zprávy najít a nahradit, které mají možnost **vždy zobrazit tuto zprávu** . Pokud se například rozhodnete, že se nezobrazuje zpráva "vyhledat dosažený počáteční bod hledání". při použití funkce Najít a nahradit by se tato informační zpráva pravděpodobně po výběru znovu zobrazila.

 Pokud nechcete zobrazit žádné informativní zprávy pro funkce Najít a nahradit, zrušte zaškrtnutí tohoto políčka.

 Pokud jste zrušili zaškrtnutí políčka **vždy zobrazit tuto zprávu** u některých, ale ne všechny, **vyhledejte a nahraďte** informační zprávy, zdá se, že se zobrazuje **informativní** zprávy, která se zobrazí, ale není vybraná. Pokud chcete obnovit všechny volitelné zprávy **Najít a nahradit** , zrušte tuto možnost a pak ji znovu vyberte.

> [!NOTE]
> Tato možnost nemá vliv na žádné informační zprávy **find a nahrazování** , které nezobrazují možnost **vždy zobrazit tuto zprávu** .

 **Zobrazit varovné zprávy** Tuto možnost vyberte, pokud chcete zobrazit všechny zprávy postupovat opatrněji najít a nahradit, které mají možnost **vždy zobrazit tuto zprávu** . Pokud jste například zvolili, že se má zobrazit zpráva o **nahrazení všech** upozornění, která se zobrazí, když se pokusíte změnit umístění v souborech, které nejsou aktuálně otevřeny pro úpravy, výběrem této možnosti by se tato zpráva upozornění zobrazila znovu, když se pokusíte Nahradit vše.

 Pokud nechcete zobrazit žádné zprávy postupovat opatrněji pro funkce Najít a nahradit, zrušte zaškrtnutí tohoto políčka.

 Pokud jste vymazali možnost **vždy zobrazit tuto zprávu** u některých, ale ne všechny, **Najít a nahradit** upozornění, zobrazí se zaškrtávací políčko **Zobrazit zprávy s upozorněním** , ale není vybráno. Pokud chcete obnovit všechny volitelné zprávy **Najít a nahradit** , zrušte tuto možnost a pak ji znovu vyberte.

> [!NOTE]
> Tato možnost nemá vliv na žádné zprávy upozorňující na **hledání a nahrazování** , které nezobrazují možnost **vždy zobrazit tuto zprávu** .

 **Automaticky vyplnit pole najít textem z editoru** Tuto možnost vyberte, pokud chcete po výběru libovolného zobrazení okna **Najít a nahradit** v nabídce **Upravit** vložit text na kteroukoli stranu vloženého bodu aktuálního editoru do pole **najít, které** se má zobrazit. Tuto možnost zrušte, pokud chcete použít poslední vzor hledání z předchozího hledání jako řetězec **find** .

## <a name="see-also"></a>Viz také
 [Hledání a nahrazení textu](../../ide/finding-and-replacing-text.md)
