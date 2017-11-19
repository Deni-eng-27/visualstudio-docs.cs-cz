---
title: "Odpovědnosti správce | Visual Studio Marketplace"
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 10/3/2017
Ms.topic: Get-Started-Article
Description: "Další informace o odpovědnosti správců odběry."
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: 0ac48059a0491b9009b6ff87fd6e05075565c028
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="administrator-overview"></a>Přehled Správce
## <a name="roles--responsibilities"></a>Role a odpovědnosti
Po sníženou cenu na produkty společnosti Microsoft a službách vaše organizace souhlasí určité odpovědnosti a omezení týkající se předplatné Visual Studio. Visual Studio správce má čtyři klíče zodpovědnosti:
1.  **Pochopit výhody a omezení Visual Studio předplatných.** Správně pochopení vašeho výhody můžete povolit pomocí cloudové služby snížit náklady na hardware a snížit náklady na software s uživatelské licence pro předprodukční prostředí. 
2.  **Přiřadit Visual Studio odběry konkrétní, s názvem jednotlivce a podporovat používání.** Smlouva vyžaduje, aby se konkrétní, s názvem jednotlivcům přiřazenou odběry Visual Studio. Následnou akci s vaší přiřazené jednotlivce zajistit, že přístup a plně využít výhod součástí jejich Visual Studio předplatného.
3.  **Přesně inventáře předprovozní prostředí.** To je důležité pro zajištění, že všichni uživatelé, kteří budou pracovat s Visual Studio licencovaný software správně licenci s předplatným vlastní Visual Studio. 
4.  **Sledovat změny v přiřazení uživatele a získat další licence podle plánu.** Microsoft multilicenční smlouvy poskytují flexibilitu v tom, jak používat a přiřaďte odběry Visual Studio. Předpokládá se, že ke sledování změn využití softwaru a přiřazení uživatelských a objednávky proces pro další licence podle plánu, uvedených ve smlouvě.

## <a name="benefits-and-limitations"></a>Výhody a omezení
Visual Studio odběry umožňují vývoj členové týmu pro instalaci a používání softwaru k návrhu, vývoj, testování, vyhodnocení a ukazují na ostatní software. Visual Studio odběrů softwaru nemá licenci pro produkční prostředí. 

|                                          |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Na základě uživatele licencování                     | MSDN platformy a všechny úrovně Visual Studio odběry jsou licencovaná podle jednotlivých uživatelů. Každý člen týmu vývoj, který bude v interakci (instalovat, konfigurovat nebo přístup) softwarem, který je součástí těchto produktů a služeb vyžaduje vlastní Visual Studio předplatné.                                                                                                                                                                                                                                                                                                                                  |
| Neomezená instalace                  | Každý licencovaný uživatel může nainstalovat a pomocí softwaru na libovolný počet zařízení pro návrh, vývoj, testování, hodnocení a předvedení softwaru. Výjimkou je aplikace Microsoft Office, který má licenci pro jeden počítač. Visual Studio licencovaný software můžete nainstalovat a použít v práci, home, školy a na zařízeních v pobočce zákazníka nebo na vyhrazeném hardwaru hostované třetí strany.                                                                                                                                                                                                                                  |
| Není určena pro produkční prostředí | Visual Studio odběrů softwaru nemá licenci pro produkční prostředí, včetně jakékoli prostředí přístup koncovým uživatelům k více než testování přijetí nebo připomínky, připojení k databázi produkční prostředí podporuje zotavení po havárii nebo produkční zálohování, nebo použít pro produkční špičky aktivity. Výjimky patří výhody pro určité úrovně předplatné uvedených v [Visual Studio licencování dokumentu White Paper](http://aka.ms/vslicensing).                                                                                            |
| Opětovné přiřazení licencí                     | Když uživatel odejde, tým a již nevyžaduje licenci, může se po 90 dnech přiřadit licence. Když měníte přiřazení licence, nebude nahradit všechny kódy product key, které již byly použity. Toto je různé funkce než byl vytvořen v webu Volume Licensing Service Center (VLSC). Všechny výhody, které byly používány, například Pluralsight se resetuje.                                                                                                                                                                                                                                                 |
| Výjimka pro koncové uživatele                  | Na konci vývojového projektu softwaru koncoví uživatelé obvykle zkontrolujte aplikace a zjistit, zda splňuje potřeby kritéria pro verzi. Tento proces se nazývá testování přijetí uživateli. Členové týmu například firma, sponzor nebo správce produktu vystupovat jako proxy pro koncové uživatele. Koncoví uživatelé, kteří nemají odběru Visual Studio může přistupovat k softwaru pro UAT Pokud používání softwaru jinak splňuje všechny Visual Studio licenční smlouvy. Navíc není obvyklé, že někdo jejichž primární role je návrh, vývoj nebo testování softwaru by také kvalifikaci jako "koncový uživatel". |

## <a name="inventory-of-pre-production-environment"></a>Inventář předprovozní prostředí
Visual Studio odběry zjednodušit správu prostředků, protože počítání uživatelům, nikoli zařízení.

Visual Studio správci musí přiřadit Visual Studio odběrů **konkrétní, s názvem jednotlivce**. Konvence vytváření názvů, jako jsou Dev1, Dev2 nebo Dev3 se **není povoleno**.

Tady jsou některé způsoby zjednodušení pořízení inventář předprovozní prostředí:
- Zkontrolujte vaše uživatele přiřazení. Společnost Microsoft poskytuje web volat [portálu pro správu Visual Studio](https://manage.visualstudio.com/) můžete sledovat přiřazení předplatné sady Visual Studio.
- Pomocí vaší místní nebo cloudové služby Active Directory na seznam uživatelů. Pokud používáte ke správě přístupu uživatele služby Active Directory, bude pravděpodobně možné identifikovat vývoj a testování uživatelů podle jejich členství v adresáři.
- Pomocí nástrojů pro automatizované systémy inventáře. Můžete také spravovat vaše prostředky softwaru a rozlišit předprovozní prostředí z výroby ty, které jsou pomocí nástroje pro inventář softwaru. Mnoho zákazníků s nástrojem Microsoft System Center vytvořit zásady vytváření názvů automatizovat tuto součást procesu inventáře.
- Získáte pomoc s ruční odsouhlasení. Zařazení pracovníci pomohou sjednotit uživatelům vývoj a testování bez vaše vývojová a testovací prostředí. 

## <a name="large-teams-and-internal-contractors"></a>Velkými týmy a interní dodavatelů
Visual Studio odběry správci jsou zodpovědní za zajištění, že každý uživatel, který komunikuje s Visual Studio licencovaný software má správně licenci na své vlastní předplatné sady Visual Studio.
### <a name="internal-teams"></a>Interními týmy
Moderní softwaru organizace obvykle zahrnují účastníky z několika skupin. Identifikujte kontakty z každé skupiny, který vám může pomoci při sledování inventáře uživatele a změny. Každá organizace se liší, ale seznam zahrnutých v vývoj týmy typické mohou zahrnovat:
- Software inženýrství týmy. 
- Obchodní týmů, včetně produktu vlastníci a obchodní analytici.
- Projektové týmy správy. 
- Kvalita týmů, včetně zaměstnancům QA a ruční testerům, sada.
- IT oddělení, včetně infrastruktury správci předprodukční režim a testovacího prostředí.

### <a name="external-contractors-and-partners"></a>Externích dodavatelů a partnery
Externích dodavatelů, mohou způsobit licencí, které chcete používat s vaším prostředím licenci sady Visual Studio. Certifikovanými partnery společnosti Microsoft obdržet několik volné Visual Studio odběry pro jejich interní použití. Tyto odběry ale nepokrývají výnosy aktivity, například vývoj vlastních softwaru pro zákazníka. Požádejte partnerům vám pošleme certifikovaných písmeno, které popisuje licencí, které se poskytují a ty, které potřebují k zajištění.

## <a name="track-user-assignment-and-process-orders"></a>Sledovat proces a přiřazení objednávky uživatele
Visual Studio odběry správce se očekává sledovat využití sady Visual Studio a zpracování objednávky pro všechny nárůst využití podle plánu, uvedených v jejich multilicenční smlouvu nebo Products společnosti Microsoft a smlouvou o poskytování služeb. Nový portál pro správu předplatných Visual Studio udělal to jednoduché s užitečné sledování zobrazující licencí k dispozici a použít.
### <a name="high-water-mark-of-usage"></a>Horní mez využití
**Vaše společnost povinnost nákupu předplatných Visual Studio se projeví okamžitě, když:**
- Licence je přiřazen k uživateli.
- Uživatel pracuje s softwaru Visual Studio.

Vaši povinnost dokončení nákupu je dáno **horní mez využití**. Tento vodoznak je vysoce bod v denní přiřazení uživatelských nebo v uživatelům interakci s Visual Studio softwaru, podle toho, která je vyšší.
1.  Visual Studio odběry správci může zvýšit horní mez využití přiřazením Visual Studio odběry jednotlivce.
2.  Visual Studio odběry správci mohou přiřadit odběry z jednoho odběratele, pokud uplynulo 90 dnů od doby původní přiřazení. Abyste se vyhnuli uměle horní mez, vždy k tomu nejdřív odebráním stávajícího předplatného a následným přidáním nového.
3.  Visual Studio odběry správce může změnit úroveň přiřazené předplatné pro jednotlivce, který představuje pokles v jedné přiřazení a o zvýšení v jiném. Při snížení odběratele přiřazené úrovni předplatného jednotlivých hned přestat používat a odinstalovat všechno, co je pouze ve vyšší úrovně předplatného. 

### <a name="open-license-and-open-value"></a>Otevřete licence a počáteční hodnota
Může být přiřazení odběry prostřednictvím jiného programu Microsoft Volume Licensing jako Microsoft Open License nebo počáteční hodnota. Pokud ano, je nutné v měsíci, ve kterém uživatelé (zaměstnanců nebo externích dodavatelů) komunikovat s Visual Studio licencovaný software zpracovat vaši objednávku pro všechny další uživatele.
### <a name="enterprise-agreements"></a>Smlouvy Enterprise
Microsoft Enterprise smlouvy (EA), MPSA a vyberte Plus smlouvy poskytují flexibilitu v tom, jak použít a licencí softwaru v sadě Visual Studio v čase. Visual Studio správci musíte nastavit roční pořadí True-Up aby softwarové licence až horní mez využití navázat během období smlouvy.