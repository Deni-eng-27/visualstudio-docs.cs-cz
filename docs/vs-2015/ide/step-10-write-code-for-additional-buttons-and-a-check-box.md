---
title: 'Krok 10: napište kód pro další tlačítka a zaškrtávací políčko | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 185cf370-ab39-4ac0-b6bc-601d5b95a4a2
caps.latest.revision: 23
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 75081ae9c1183b470cd3197589cbf4134fe4a97b
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72667336"
---
# <a name="step-10-write-code-for-additional-buttons-and-a-check-box"></a>Krok 10: Zapište kód pro přídavná tlačítka a zaškrtávací pole
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nyní jste připraveni provést další čtyři metody. Tento kód můžete zkopírovat a vložit, ale pokud se chcete dozvědět nejvíc od tohoto kurzu, zadejte kód a použijte technologii IntelliSense.

 Tento kód přidá funkce do tlačítek, které jste přidali dříve. Bez tohoto kódu nejsou tlačítka dělat nic. Tlačítka používají kód v jejich `Click`ch událostech (a zaškrtávací políčko používá událost `CheckChanged`) k provedení různých akcí při aktivaci ovládacích prvků. Například událost `clearButton_Click`, která se aktivuje po kliknutí na tlačítko **Vymazat obrázek** , vymaže aktuální obrázek nastavením vlastnosti `Image` na `null` (nebo `nothing`). Každá událost v kódu obsahuje komentáře, které vysvětlují, co kód dělá.

 ![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo") Verzi videa tohoto tématu najdete v tématu [kurz 1: vytvoření prohlížeče obrázků v Visual Basic-video 5](http://go.microsoft.com/fwlink/?LinkId=205216) nebo [kurz 1: vytvoření prohlížeče obrázků ve C# videu 5](http://go.microsoft.com/fwlink/?LinkId=205206). Tato videa používají starší verzi sady Visual Studio, takže existují mírné rozdíly v některých příkazech nabídky a dalších prvcích uživatelského rozhraní. Koncepty a postupy však fungují podobně v aktuální verzi sady Visual Studio.

> [!NOTE]
> Osvědčený postup: vždy komentovat kód. Komentáře jsou informace, které uživatel přečte, a je to čas, kdy se váš kód může pochopit. Vše na řádku komentáře program ignoruje. V jazyce C#Visual se zadáním dvou dvojitých lomítek na začátku (//) zobrazí komentář k řádku a v Visual Basic zadáte komentář řádku, který začíná jednoduchou uvozovkou (').

### <a name="to-write-code-for-additional-buttons-and-a-check-box"></a>Psaní kódu pro další tlačítka a zaškrtávací políčko

- Přidejte následující kód do souboru kódu Form1 (Form1.cs nebo Form1. vb). Vyberte kartu **VB** pro zobrazení kódu Visual Basic.

     [!code-csharp[VbExpressTutorial1Step9_10#2](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial1step9_10/cs/form1.cs#2)]
     [!code-vb[VbExpressTutorial1Step9_10#2](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial1step9_10/vb/form1.vb#2)]

### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Pokud chcete přejít na další krok kurzu, přečtěte si [Krok 11: spuštění programu a vyzkoušejte jiné funkce](../ide/step-11-run-your-program-and-try-other-features.md).

- Pokud se chcete vrátit k předchozímu kroku kurzu, přečtěte si [Krok 9: kontrola, komentář a testování kódu](../ide/step-9-review-comment-and-test-your-code.md).
