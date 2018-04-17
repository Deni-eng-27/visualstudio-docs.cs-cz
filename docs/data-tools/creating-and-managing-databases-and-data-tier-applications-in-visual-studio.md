---
title: Databáze projekty – projekty serveru a DAC projekty v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- managing change, databases
- database features of Visual Studio, managing change
- databases, managing change
- managing change, database servers
ms.assetid: 40b51f5a-d52c-44ac-8f84-037a0917af33
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: baca17712d6cf39753dab51c60fee901c0ea08ca
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="database-projects-and-data-tier-applications-in-visual-studio"></a>Databázové projekty a aplikace na datové vrstvě v sadě Visual Studio  
Databázové projekty můžete použít k vytvoření nové databáze nové aplikace na datové vrstvě (DAC) a k aktualizaci existující databáze a aplikace na datové vrstvě. Databázové projekty i DAC projekty umožňují použít techniky verze řízení a projekt správy pro váš vývojový program databáze na mnohem stejným způsobem, že použijete tyto techniky spravovaným nebo nativním kódem. Vám může pomoci váš vývojový tým vytvoříte spravovat změny databáze a databázové servery *DAC projektu*, *projekt databáze*, nebo *serverový projekt* a umístit ho v části Správa verzí. Členy týmu prohlížet soubory a ujistěte se, vytvářet a testovat změny v *izolované vývojového prostředí*, nebo izolovaného prostoru, než je sdílet s týmem. K zajištění kvality kódu, můžete váš tým dokončit a otestovat všechny změny pro konkrétní verzi databáze v testovacím prostředí, před nasazením změny do produkčního prostředí.  
  
Seznam funkcí databáze, které podporuje aplikace datové vrstvy, najdete v části [funkce podporované v aplikace datové vrstvy](http://go.microsoft.com/fwlink/?LinkId=164239) na webu společnosti Microsoft. Pokud ve vaší databázi funkce, které nepodporuje aplikace datové vrstvy, místo toho používejte databázového projektu spravovat změny k vaší databázi.  
  
## <a name="common-high-level-tasks"></a>Běžné úlohy vysoké úrovně  
  
|Podrobný úloh|Podpůrný obsah|  
|----------------------|------------------------|  
|**Spustit vývoj aplikace datové vrstvy:** A DAC je nový koncept zavedené [!INCLUDE[sskatmai_r2](../data-tools/includes/sskatmai_r2_md.md)] obsahující definice [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] databáze a v podporu instance objektů, které jsou používány klient server nebo vrstvě 3 aplikace. DAC zahrnuje databázové objekty, jako jsou tabulky a zobrazení, společně s instance entitami, jako je například přihlášení. Můžete použít [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] pro vytvoření projektu DAC sestavení soubor balíčku DAC a odeslat tento soubor balíčku DAC do správce databáze pro nasazení do instance [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] databázového stroje.|-   [Vytváření a Správa aplikace datové vrstvy](http://go.microsoft.com/fwlink/?LinkId=160741) (webu společnosti Microsoft)<br />-   [SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=227328)|  
|**Provádění vývoj iterativní databází:** Pokud jste vývojář nebo tester, podívejte se na částí projektu a potom je aktualizovat izolované vývojovém prostředí. Pomocí tohoto typu prostředí si můžete testovat změny bez ovlivnění dalších členové týmu. Po dokončení se změny, je třeba zkontrolovat soubory zpět do správy verzí, kde můžete získat změny a vytvořit a nasadit je na testovací server ostatní členové týmu.|-   [Dotaz a textové editory (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=227327) (webu společnosti Microsoft)<br />-   [Ladicí program Transact-SQL](http://go.microsoft.com/fwlink/?LinkId=227324) (webu společnosti Microsoft)|  
|**Při vytváření prototypu, ověření testů, výsledky a změny databázové skripty a objekty:** můžete použít [!INCLUDE[tsql](../data-tools/includes/tsql_md.md)] editor provést jednu z těchto běžné úlohy.|-   [Dotaz a textové editory (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=227327) (webu společnosti Microsoft)|  
  
## <a name="see-also"></a>Viz také
[Visual Studio Data Tools for .NET](../data-tools/visual-studio-data-tools-for-dotnet.md)
