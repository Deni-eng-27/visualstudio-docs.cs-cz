---
title: "Rychlé spuštění, prostředí, dialogové okno Možnosti | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Environment.QuickLaunch
- vs.quicklaunch
helpviewer_keywords:
- searching IDE
- IDE, searching
ms.assetid: 4200f297-d065-4723-9a30-d91ff2e26c9d
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 0f71cca51a27c8ed9d6467d99425d4d3b721d195
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="quick-launch-environment-options-dialog-box"></a>Dialogové okno Snadné spuštění, Prostředí, Možnosti
Můžete použít **Snadné spuštění** k rychlému vyhledání a provádět akce u prostředků IDE jako možnosti, šablony, nabídky. Nemůžete použít **Snadné spuštění** vyhledávání kódu a symboly. **Snadné spuštění** vyhledávacího pole je umístěna v pravém horním rohu panelu nabídek a je přístupný výběrem kombinace kláves Ctrl + Q klíče. Do pole zadejte hledaný řetězec. K vyhledání řetězce, které obsahují @, použijte ' @@'.  
  
 **Snadné spuštění** je ve výchozím nastavení povolené při instalaci sady Visual Studio. V řádku nabídek, můžete zobrazit nebo skrýt **Snadné spuštění** výběrem **nástroje**, **možnosti**. Rozbalte **prostředí** uzel a potom zvolte **Snadné spuštění**. Vyberte nebo zrušte **povolit rychlé spuštění** zaškrtávací políčko. Můžete také povolit nebo zakázat kategorie vyhledávání na této stránce.  
  
## <a name="category-list"></a>Seznam kategorií  
 Výsledky hledání rychlé spuštění se zobrazí v čtyř kategorií: **nedávno použité**, **nabídky**, **možnosti**, a **otevřené dokumenty**, spolu s počet položek v kategorii. Chcete-li procházejí prostřednictvím výsledky hledání podle kategorií, zvolte kombinace kláves Ctrl + Q klíče a zobrazit všechny výsledky z další kategorie. Za poslední kategorie se zobrazí, kombinace kláves Ctrl + Q ukazuje několik výsledky z každé kategorie. Ctrl + Shift + Q můžete procházet kategorie v obráceném pořadí. Chcete-li zobrazit všechny výsledky hledání v části kategorie, zvolte název kategorie.  
  
 Následující zkratky můžete použít k omezení hledání tak, aby určité kategorie.  
  
|Kategorie|Zástupce|Popis zástupce|  
|--------------|--------------|--------------------------|  
|Naposledy použité|@mru<br /><br /> Třeba `@mru font`.|Zobrazí až pěti položek, které **nedávno použité**.|  
|Nabídky|@menu<br /><br /> Třeba `@menu font`.|Omezí výsledky vyhledávání na položky nabídky.|  
|Možnosti|@opt<br /><br /> Třeba `@opt font`.|Omezení vyhledávání nastavení v **možnosti** dialogové okno.|  
|Dokumenty|@doc<br /><br /> Třeba `@doc font`.|Omezí výsledky vyhledávání na názvy souborů a cesty k nim otevřené dokumenty pro kritéria hledání, ale nebude hledat text v rámci soubory sami.|  
  
> [!NOTE]
>  Klávesové zkratky můžete změnit na **Obecné**, **klávesnice** stránky v **možnosti** dialogové okno.  
  
## <a name="show-previous-results"></a>Zobrazit předchozí výsledky  
 Ve výchozím nastavení není mezi relacemi vyhledávání trvalé hledaný termín, který zadáte. Hledaný řetězec není zaškrtnuto, je-li vyhledat termín, přesuňte se ukazatelem mimo **Snadné spuštění** oblasti a pak se vraťte zpět. Chcete-li zachovat výsledky hledání, přejděte na **možnosti** dialogové okno Vyberte **Snadné spuštění**a potom vyberte **výsledky hledání zobrazit z předchozí hledání Snadné spuštění při aktivaci.** zaškrtávací políčko. Při příštím hledání nechte oblast Snadné spuštění a vraťte, snadné spuštění bude zachování naposledy použila hledaný termín a také zobrazit výsledky hledání.  
  
 Nejnovější tipy a triky pro používání **Snadné spuštění**, najdete v části [Visual Studio Blog](http://go.microsoft.com/fwlink/?LinkId=236054).  
  
## <a name="see-also"></a>Viz také  
 [Obecné elementy uživatelského rozhraní (Visual Studio)](../../ide/reference/general-user-interface-elements-visual-studio.md)   
 [Prostředí, dialogové okno Možnosti](../../ide/reference/environment-options-dialog-box.md)