---
title: Přiřazení licencí pro předplatná sady Visual Studio | Dokumentace Microsoftu
author: TerryGLee
ms.author: tglee
manager: douge
ms.date: 07/16/2018
ms.topic: conceptual
description: Zjistěte, jak správci mohou přiřadit licence pro předplatitele
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: e0baa4ee731b8d69e18ab59c958801d94fb99869
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/25/2018
ms.locfileid: "39251702"
---
# <a name="assign-licenses-in-the-visual-studio-subscriptions-administrator-portal"></a>Přiřazení licencí na portálu správce předplatných sady Visual Studio

Jako správce předplatných sady Visual Studio můžete použít portál správce předplatných přiřadit jednotlivým uživatelům a skupinám uživatelů.

Pro skupiny uživatelů, můžete přiřadit předplatných k nim jednu v čase, nebo použijte **hromadné přidání** funkce rychle a snadno nahrát seznam předplatitelů a jejich informace o předplatném.

## <a name="individual-assignments"></a>Jednotlivé přiřazení

Tady je postup, chcete-li přiřadit licenci předplatného sady Visual Studio s novým uživatelem, takže bude mít přístup k výhodám předplatného.

1. Přihlaste se k [portálu správce](https://manage.visualstudio.com).

2. Chcete-li přiřadit licenci na jednoho předplatitele sady Visual Studio, v horní části v tabulce vyberte **přidat**.

   ![Přidat jednoho předplatitele](media\add-single-subscriber.png)

3. Zadejte informace do polí formuláře pro nové předplatitele. Pokud vaše organizace používá Azure Active Directory, toto pole funguje jako vyhledávací funkce, která se najít v aktuálním adresáři, můžete vybrat správný uživatel ve výsledcích hledání. Jakmile vyberete osoby, se automaticky vyplní své jméno, přihlašovací e-mailu a e-mailové oznámení.

   ![Přidáte novou e-mailovou adresu oznámení](media\add-new-subscriber-notification-email.png)

   Pokud chcete mít přístup ke stahování softwaru při přihlašování do tohoto předplatného [portál předplatného sady Visual Studio](https://my.visualstudio.com?wt.mc_id=o~msft~docs), ujistěte se, že nechat tento přepínač soubory ke stažení v povolená **nastavení stahování** oddíl. Pokud budete chtít zakázat soubory ke stažení, uživatel nebude mít přístup k souborům ke stažení softwaru, ale budou mít dál přístup ke všem výhodám zahrnutý v předplatném.

   ![Přístup k souborům ke stažení](media\access-to-downloads.png)

   Pokud chcete změnit jazyk, ve kterém přijímá odběratele informace, můžete k tomu, **předvolby komunikace** oddílu.

   ![Změnit jazyk, který chcete použít při odesílání oznámení e-mailů](media\change-subscriber-communication-preference.png)

   Pokud chcete přidat odkaz poznámek k předplatnému, můžete k tomu, **přidat odkaz na** oddílu.

   ![Přidat poznámky odkaz na předplatné](media\add-subscriber-reference-notes.png) 

    Když budete mít vyberou možnosti a zadávání dat pro odběratele, zvolte **přidat** v dolní části **přidat předplatitele** nabídka.

   ![Klikněte na tlačítko Přidat](media\add-button.png)

4. Po přidání odběratele, E-mail s přiřazením automaticky se pošle na nový odběratel se další pokyny. Můžete kdykoli znovu odeslat E-mail s přiřazením tak odběratele vyberete a kliknete na **znovu odeslal** tlačítko v horní nabídce.

   ![Znovu poslat aktivační e-mail pro všechny uživatele nebo více uživatelů, pokaždé, když chcete](media\resend-subscriber-activation-emails.png) 

## <a name="bulk-assignments"></a>Hromadné přiřazení

1. Chcete-li přidat několik předplatitelů najednou, přejděte na **spravovat předplatitele** kartu. Na pásu karet v horní části klikněte na tlačítko **hromadné přidání**.

  ![Přidat několik předplatitelů](media\add-multiple-subscribers.png)

1. Hromadné přiřazení používá šablonu aplikace Microsoft Excel k odeslání odběratele. V dialogovém okně nahrát několik předplatitelů klikněte na tlačítko **Stáhnout** stáhnout šablonu.

  ![Stáhněte si šablonu v Excelu na načíst několik předplatitelů](media\download-template-upload-subscribers.png)

   > ! [POZNÁMKA] Kdykoli stáhněte nejnovější verzi této šablony. Pokud používáte starší verzi, hromadné načtení může selhat.

1. V Excelovém listu vyplňte pole s informacemi pro jednotlivce, které chcete přiřadit odběrů. (*Odkaz* je volitelné pole.) Uložte soubor místně, až budete hotovi.

  Zajistit hladký průběh nahrávání, dodržujte následující osvědčené postupy:

    - Ujistěte se, že žádná z polí formuláře obsahovat čárky.
    - Odeberte mezery před a za pole formuláře.
    - Ujistěte se, že uživatele názvy neobsahují mezery mezi dvěma částmi první nebo poslední názvy (například pokud uživatel má dvě části jméno jako je například "Maggie může", to by měla být zadána jako "MaggieMay" protože systém nebude trim místo navíc.)

1. Vraťte se do portálu pro správu předplatných sady Visual Studio. V **nahrát několik předplatitelů** dialogové okno, klikněte na tlačítko **Procházet**.

  ![Procházet šablony uložené na načíst několik předplatitelů](media\bulk-add-browse-saved-template.png)

1. Přejděte na Excelový soubor, který jste uložili a potom klikněte na **OK**.

  ![Nahrát šablonu v Excelu na načíst několik předplatitelů](media\bulk-upload-subscribers.png)

  Zobrazí se dialogové okno průběhu nahrání.

  Pokud šablona obsahuje chyby, nahrávání se nezdaří a zobrazí chyby, mohli opravte šablonu a pokuste se znovu hromadné načtení.

  ![Chybová zpráva, pokud se nezdaří nahrát několik předplatitelů](media\bulk-add-template-failed.png)

  Při nahrání je úspěšné, zobrazí se vám seznam předplatitelů a potvrzovací zpráva.

  ![Potvrzení, pokud je úspěšná nahrát několik předplatitelů](media\bulk-add-template-success.png)
