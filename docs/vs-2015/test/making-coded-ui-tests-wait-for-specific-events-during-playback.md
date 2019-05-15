---
title: Provádění kódované UI testy vyčkat, než konkrétní události při přehrávání | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: conceptual
ms.assetid: 41981ad6-673e-492e-b739-9863b14157b1
caps.latest.revision: 26
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 8c0158370ceb101e8c6934f92e2dd3e8689254c5
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65686313"
---
# <a name="making-coded-ui-tests-wait-for-specific-events-during-playback"></a>Zajištění čekání programových testů UI na konkrétní události při přehrávání
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Programové přehrávání testů uživatelského rozhraní webu můžete dát pokyn testů čekala určitých událostí pravděpodobnější, jako je okno se zobrazí indikátor průběhu signalizující zmizí a tak dále. K tomuto účelu použijte vhodnou metodu UITestControl.WaitForControlXXX() jak je popsáno v následující tabulce. Příklad programový test UI, který čeká na povolit pomocí ovládacího prvku <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForControlEnabled%2A> metody, naleznete v tématu [názorný postup: Vytváření, úpravy a údržba programového testu UI](../test/walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md).  
  
 **Požadavky**  
  
 Visual Studio Enterprise  
  
> [!TIP]
> Můžete také přidat zpoždění před akcí pomocí editoru programového testu UI. Další informace najdete v tématu [jak: Vložení prodlevy před akci uživatelského rozhraní pomocí editoru testů kódované UI](https://msdn.microsoft.com/library/509f8ef7-e105-4049-b11b-d64549e055b0).  
  
 **UITestControl.WaitForControlXXX() Methods**  
  
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForControlReady%2A>  
  
 Čeká se na ovládací prvek bude připravené tak, aby přijímal myši a klávesnice. Modul implicitně volá tato rozhraní API pro všechny akce čekat pro ovládací prvek bude připravené před provedením jakékoli operace. Nicméně v některých esoterických scénáři, budete muset provést explicitní volání konstruktoru.  
  
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForControlEnabled%2A>  
  
 Čeká na ovládací prvek povolena, když Průvodce provádí nějaké asynchronní ověření vstupu tím, že volání na server. Například může metoda čekat **Další** tlačítko průvodce bude (povoleno). Příklad této metody, naleznete v tématu [názorný postup: Vytváření, úpravy a údržba programového testu UI](../test/walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md).  
  
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForControlExist%2A>  
  
 Čeká se na ovládací prvek se zobrazí v Uživatelském rozhraní. Například očekáváte dialogovým oknem chyby po dokončení ověření parametry aplikace. Čas potřebný pro ověření je proměnná. Tuto metodu můžete použít čekat dialog s chybou.  
  
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForControlNotExist%2A>  
  
 Čeká se na ovládací prvek zmizí z uživatelského rozhraní. Například může čekat indikátor průběhu zmizí.  
  
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForControlPropertyEqual%2A>  
  
 Počká zadanou vlastnost ovládacího prvku má zadanou hodnotu. Je třeba počkat stavový text změnit na **provádí**.  
  
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForControlPropertyNotEqual%2A>  
  
 Počká zadanou vlastnost ovládacího prvku má opakem zadanou hodnotu. Například můžete čekat textové pole pro nesmí být jen pro čtení, to znamená, upravovat.  
  
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForControlCondition%2A>  
  
 Čeká zadanou predikát vrátí bude `true`. To lze použít pro operace komplexní čekání (například nebo podmínky) na daný ovládací prvek. Například můžete počkat, dokud je stavový text **Succeeded** nebo **neúspěšné** jak je znázorněno v následujícím kódu:  
  
```csharp  
  
// Define the method to evaluate the condition   
private static bool IsStatusDone(UITestControl control)   
{   
    WinText statusText = control as WinText;   
    return statusText.DisplayText == "Succeeded" || statusText.DisplayText == "Failed";   
}   
  
// In test method, wait till the method evaluates to true   
statusText.WaitForControlCondition(IsStatusDone);  
  
```  
  
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.WaitForCondition%2A>  
  
 Všechny předchozí metody jsou metody instance UITestControl. Tato metoda je statická metoda. Tato metoda také čeká zadanou predikát bude `true` ale můžou se používat pro operace komplexní čekání (například nebo podmínky) na více ovládacích prvků. Například můžete počkat, dokud je stavový text **Succeeded** nebo dokud se zobrazí chybová zpráva, jak je znázorněno v následujícím kódu:  
  
```csharp  
  
// Define the method to evaluate the condition   
private static bool IsStatusDoneOrError(UITestControl[] controls)   
{   
    WinText statusText = controls[0] as WinText;   
    WinWindow errorDialog = controls[1] as WinWindow;   
    return statusText.DisplayText == "Succeeded" || errorDialog.Exists;   
}   
  
// In test method, wait till the method evaluates to true   
UITestControl.WaitForCondition<UITestControl[]>(new UITestControl[] { statusText, errorDialog }, IsStatusDoneOrError);  
  
```  
  
 Všechny tyto metody mají následující chování:  
  
 Metody vrací hodnotu true, pokud čekání úspěšné a hodnotu false, pokud čekání se nezdařilo.  
  
 Je určeno implicitním časový limit operace čekání <xref:Microsoft.VisualStudio.TestTools.UITesting.PlaybackSettings.WaitForReadyTimeout%2A> vlastnost. Výchozí hodnota této vlastnosti je 60000 milisekund (jednu minutu).  
  
 Metody mají přetížení provést explicitní vypršení časového limitu v milisekundách. Ale při vyhledávání protokolem implicitní pro ovládací prvek nebo když aplikace je zaneprázdněna výsledkem operace čekání, skutečné čekací doba může být větší než zadaný časový limit.  
  
 Předchozí funkce jsou výkonnější a flexibilnější a by měl splňovat téměř všechny podmínky. Ale v případě tyto metody nevyhovují vašim potřebám a budete muset buď kód <xref:Microsoft.VisualStudio.TestTools.UITesting.Playback.Wait%2A>, nebo <xref:System.Threading.Thread.Sleep%2A> ve vašem kódu, se doporučuje použít Playback.Wait() místo Thread.Sleep() API. Důvody jsou:  
  
 Můžete použít <xref:Microsoft.VisualStudio.TestTools.UITesting.PlaybackSettings.ThinkTimeMultiplier%2A>vlastnost upravit dobu trvání režimu spánku. Ve výchozím nastavení tato proměnná je 1 ale můžete zvýšit nebo snížit dobu čekání po kód změnit. Například pokud testujete konkrétně přes pomalé sítě nebo ostatní případy nízký výkon, můžete změnit tuto proměnnou na jednom místě (nebo dokonce i v konfiguračním souboru) 1.5 můžete přidat další 50 % čekat na všech místech.  
  
 Playback.Wait() interně volá Thread.Sleep() (po výše výpočtu) do menších bloků v smyčky for vycházející z při kontrole operace cancel\break uživatele. Jinými slovy Playback.Wait() umožňuje, že zrušíte před koncem čekání přehrávání nejsou režimy spánku může nebo vyvolat výjimku.  
  
> [!TIP]
> Editor programového testu uživatelského rozhraní umožňuje snadno upravovat programové testy uživatelského rozhraní. Použití editoru programového testu UI, můžete vyhledat, zobrazit a upravit testovací metody. Můžete také upravit akce uživatelského rozhraní a jim přidružené ovládací prvky v mapování ovládacího prvku uživatelského rozhraní. Další informace najdete v tématu [testů uživatelského rozhraní programového úpravy pomocí editoru programového testu UI](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md).  
  
 **Pokyny**  
  
 Další informace najdete v tématu [testování pro nepřetržité dodávky s Visual Studio 2012 – kapitola 5: Automatizace systémových testů](http://go.microsoft.com/fwlink/?LinkID=255196)  
  
## <a name="see-also"></a>Viz také  
 [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)   
 [Vytváření programových testů UI](../test/use-ui-automation-to-test-your-code.md#VerifyingCodeUsingCUITCreate)   
 [Návod: Vytváření, úpravy a údržba programového testu UI](../test/walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md)   
 [Anatomie programového testu UI](../test/anatomy-of-a-coded-ui-test.md)   
 [Podporované konfigurace a platformy pro programové testy uživatelského rozhraní a zaznamenávání akcí](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)   
 [Postupy: Vložení prodlevy před akci uživatelského rozhraní pomocí editoru testů programového uživatelského rozhraní](https://msdn.microsoft.com/library/509f8ef7-e105-4049-b11b-d64549e055b0)
