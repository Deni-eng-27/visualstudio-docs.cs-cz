---
title: Pole najít / příkaz
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.findcommandbox
helpviewer_keywords:
- Find/Command box
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 221c5fbbd3f0f82ac97d0c2a0fcc82657e0296c4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62977748"
---
# <a name="findcommand-box"></a>pole Najít/příkaz

Můžete hledat text a spustit příkazy sady Visual Studio z **najít/příkaz** pole. **Najít/příkaz** pole je stále k dispozici jako ovládací prvek panelu nástrojů, ale už není ve výchozím nastavení viditelný. Můžete zobrazit **najít/příkaz** pole výběrem **přidat nebo odebrat tlačítka** na **standardní** nástrojů a následným výběrem možnosti **najít**.

Ke spuštění [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] příkazu, adresa větší než (**>**) přihlašování.

**Najít/příkaz** pole zachová poslední 20 položek zadaných a zobrazí je v rozevíracím seznamu. V seznamu můžete procházet kliknutím **klávesy se šipkami**.

![Najít&#47;příkaz pole](../ide/media/findcommandbox.png)

## <a name="searching-for-text"></a>Hledání textu

Ve výchozím nastavení při zadávání textu **najít/příkaz** pole a klikněte na tlačítko **Enter** klíče, Visual Studio vyhledá aktuální okno dokumentu nebo nástroj pomocí možnosti, které jsou určené v **Najít v souborech** dialogové okno. Další informace najdete v tématu [hledání a nahrazení textu](../ide/finding-and-replacing-text.md).

## <a name="entering-commands"></a>Zadávání příkazů

Použít **najít/příkaz** pole vydat jediného [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] příkaz % $n nebo alias místo Hledat text před příkaz umístit větší než (**>**) symbol. Příklad:

```
>File.NewFile c:\temp\MyFile /t:"General\Text File"
```

Alternativně můžete použít také **příkaz** okno k zadání a spustit jeden nebo více příkazů. Některé příkazy nebo aliasy lze zadat a spustit samostatně; ostatní vyžadovala trojnásobnou investici argumenty v syntaxi. Seznam příkazů, které mají argumenty najdete v tématu [příkazy sady Visual Studio](../ide/reference/visual-studio-commands.md).

## <a name="escape-characters"></a>Řídicí znaky

Stříšky (**^**) znak v příkazu znamená, že znak, který bezprostředně následují je interpretován doslovně a ne jako řídicí znak. To lze použít k vložení uvozovek (**"**), mezery, nejlepší lomítka, střížek nebo jakýmikoli literálními znaky v parametr nebo přepínač hodnota s výjimkou názvů switchů. Příklad:

```
>Edit.Find ^^t /regex
```

Stříška funguje stejně, ať už se jedná o vnitřní nebo vnější uvozovky. Pokud poslední znak na řádku stříška, je ignorován.

## <a name="see-also"></a>Viz také:

- [Okno příkazového řádku](../ide/reference/command-window.md)
- [Hledání a nahrazení textu](../ide/finding-and-replacing-text.md)