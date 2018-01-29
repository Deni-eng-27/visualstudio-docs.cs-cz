---
title: "Upravit předplatná v portálu správce | Microsoft Docs"
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 10/3/2017
Ms.topic: Get-Started-Article
Description: Learn how administrators can edit subscription assignments.
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: 120bf87ddbaf50efa1abe59bac1c2e4616db7737
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2018
---
# <a name="editing-visual-studio-subscription-assignments"></a>Úpravy přiřazení předplatné sady Visual Studio

## <a name="making-changes-to-subscriber-information"></a>Provádění změn informace o odběru
Můžete upravit informace odběratele opravte chyby nebo aktualizovat informace. 
**Upozorňujeme, že úpravy e-mailovou adresu odběratele způsobí, že všechny stávající výhody resetování.**

Chcete-li upravit odběratele, vyberte na výpustky (...), které se zobrazují vedle e-mailová adresa odběratele, při přesunutí ukazatele myši nad ním. Zobrazí se rozevírací seznam.  Vyberte **upravit** upravit podrobnosti odběratele. Můžete také dvakrát klikněte na řádek odběratele v mřížce a otevřete okno Upravit.

   ![Vyberte odběratele, které chcete upravit](_img\edit-license\select-subscriber.png)

Můžete aktualizovat odběrateli křestní jméno, příjmení, země, jazyk a soubory ke stažení. Upravit informace o odběratele a potom klikněte na **Uložit**.

   ![Upravit podrobnosti odběratele](_img\edit-license\edit-subscriber.png)

> [!NOTE]
> Pokud potřebujete změnit úroveň odběr pro odběratele, musíte odstranit uživatele z portálu a znovu přidejte. Předplatné úrovně se nedají upravovat.

## <a name="editing-multiple-subscribers-by-using-bulk-edit"></a>Úprava více odběrateli pomocí hromadné úpravy

Můžete upravit více odběrateli najednou procesem hromadné úpravy. Tato funkce slouží především pro organizace, které jsou průchodu přes firemní e-mailová adresa změny nebo pokud se organizace rozhodla pro omezení přístupu ke stahování. 

> [!IMPORTANT]
> Předplatné úrovně (tj. Enterprise, Professional atd.) a nelze je měnit předplatné identifikátory GUID.  Když zkusíte nahrávaný s následujícími položkami změnit, nahrávání se nezdaří.  

1.  Chcete-li upravit více odběrateli najednou, přejděte na kartu odběratele. Na pásu karet v horní části, klikněte na tlačítko **hromadně upravovat**. 

    ![Úpravy licenci - hromadné úpravy](_img\edit-license\edit-license-bulk-edit.png)

2.  Hromadné úpravy používá šablony aplikace Excel k provádět úpravy informace o odběru. V dialogovém okně Upravit hromadné klikněte na tlačítko **Export to v aplikaci excel** stáhnout aktuální seznam odběratele, včetně všech jejich informací. 

    ![Úpravy licenci - Export provede hromadné úpravy seznamu](_img\edit-license\edit-license-bulk-edit-export.png)

3.  V dalším kroku uložte soubor místně, abyste mohli snadno najít a proveďte potřebné změny před jejich odesláním ji. Chcete-li zaručit úspěšné odeslání, **nemusíte upravovat úrovni předplatného nebo GUID odběru** jako to může způsobit odeslání selhání. 

4.  Vrátit na portál pro správu předplatných Visual Studio a v dialogovém okně hromadně upravovat, klikněte na tlačítko **Procházet**. Vyberte soubor aplikace Excel, který jste uložili a klikněte na tlačítko **OK**. Průběh nahrávání se zobrazí na obrazovce.

    ![Úpravy licenci - hromadné upravuje nahrávání souborů](_img\edit-license\edit-license-bulk-file-upload1.png)

5.  Jakmile jste odeslali soubor, zobrazí se oznámení umožňují vědět, že byla úspěšná. 

    ![Úpravy licenci - dokončení nahrávání provede hromadné úpravy](_img\edit-license\edit-license-bulk-upload-complete.png)


