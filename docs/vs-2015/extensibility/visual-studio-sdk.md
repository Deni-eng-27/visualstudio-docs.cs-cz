---
title: Sada Visual Studio SDK | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- VSSDK.v90.StartPage
helpviewer_keywords:
- Visual Studio SDK
- VS SDK (see Visual Studio SDK)
- Visual Studio, SDK
ms.assetid: 1f7c348a-114c-4243-b392-3531e9c9c6fd
caps.latest.revision: 57
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 59ef6ae6b042b1616997821febe156ef5cac3b7f
ms.sourcegitcommit: bad28e99214cf62cfbd1222e8cb5ded1997d7ff0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2019
ms.locfileid: "74299706"
---
# <a name="visual-studio-sdk"></a>Visual Studio SDK
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Sada Visual Studio SDK vám pomůže s rozšiřováním funkcí sady Visual Studio nebo integrací nových funkcí do sady Visual Studio. Rozšíření můžete distribuovat dalším uživatelům i galerii sady Visual Studio. Níže jsou uvedeny některé způsoby, jak můžete sadu Visual Studio rozšíří:  
  
- Přidání příkazů, tlačítek, nabídek a dalších prvků uživatelského rozhraní do integrovaného vývojového prostředí  
  
- Přidat okna nástrojů pro nové funkce  
  
- Rozšiřování technologie IntelliSense pro daný jazyk nebo poskytnutí IntelliSense pro nové programovací jazyky  
  
- Používejte žárovky k poskytování pomocných rad a návrhů, které vývojářům pomůžou psát lepší kód.  
  
- Povolit podporu pro nový jazyk  
  
- Přidat vlastní typ projektu  
  
- Oslovení milionů vývojářů prostřednictvím Visual Studio Marketplace  
  
  Pokud jste ještě nikdy nezapsali rozšíření sady Visual Studio, měli byste najít další informace o těchto funkcích a [začít vyvíjet rozšíření sady Visual Studio](../extensibility/starting-to-develop-visual-studio-extensions.md).  
  
## <a name="installing-the-visual-studio-sdk"></a>Instalace sady Visual Studio SDK  
 Spouští se v sadě Visual Studio 2015, nenainstalujete sadu Visual Studio SDK ze služby Stažení softwaru. Je zahrnut jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="whats-new-in-the-visual-studio-2015-sdk"></a>Co je nového v sadě Visual Studio 2015 SDK  
 Sada Visual Studio SDK obsahuje některé nové funkce, včetně žárovek a nových položek projektu, které umožňují vytvářet příkazy nabídky, okna nástrojů a rozšíření editoru pomocí balíčku VSIX. Další informace najdete v tématu [co je nového ve službě Visual Studio 2015 SDK](../extensibility/what-s-new-in-the-visual-studio-2015-sdk.md).  
  
## <a name="visual-studio-user-experience-guidelines"></a>Pravidla pro práci s uživatelským prostředím sady Visual Studio  
 Skvělé tipy k návrhu uživatelského rozhraní pro rozšíření v [Visual Studio zkušenosti uživatelů](../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md).  
  
 Můžete se také seznámit s tím, jak se má vaše rozšíření na zařízeních s vysokým rozlišením DPI zobrazovat skvěle v tématu řešení [problémů s řešením dpi](../extensibility/addressing-dpi-issues2.md) .  
  
 Využijte výhod [služby image a katalogu](../extensibility/image-service-and-catalog.md) pro skvělou správu imagí a podporu vysokého rozlišení DPI.  
  
## <a name="finding-and-installing-existing-visual-studio-extensions"></a>Hledání a instalace existujících rozšíření sady Visual Studio  
 Rozšíření sady Visual Studio najdete v dialogovém okně **rozšíření a aktualizace** v nabídce **nástroje** . Další informace najdete v tématu [hledání a používání rozšíření sady Visual Studio](../ide/finding-and-using-visual-studio-extensions.md). V [Visual Studio Marketplace](https://marketplace.visualstudio.com/) můžete také najít rozšíření.  
  
## <a name="visual-studio-sdk-reference"></a>Referenční dokumentace sady Visual Studio SDK  
 Referenční informace k rozhraní API sady Visual Studio SDK najdete v [referenčních informacích k sadě Visual Studio SDK](../extensibility/visual-studio-sdk-reference.md).  
  
## <a name="visual-studio-sdk-samples"></a>Ukázky sady Visual Studio SDK  
 Příklady open source rozšíření sady VS SDK najdete na webu GitHub v sadě [Visual Studio Samples](https://aka.ms/vs2015sdksamples). Toto úložiště GitHub obsahuje ukázky, které ilustrují různé rozšiřitelné funkce v aplikaci Visual Studio.  
  
## <a name="other-visual-studio-sdk-resources"></a>Další prostředky sady Visual Studio SDK  
 Pokud máte dotazy týkající se VSSDK nebo chcete sdílet své zkušenosti s vývojem rozšíření, můžete použít [Fórum rozšiřitelnosti sady Visual Studio](https://social.msdn.microsoft.com/Forums/vstudio/home?forum=vsx) nebo [Chat skupiny extendvs](https://gitter.im/Microsoft/extendvs).  
  
 Další informace najdete na [blogu VSX Arcana](https://blogs.msdn.microsoft.com/vsx/) a v několika blogůch zapsaných přes Microsoft MVP:  
  
- [Oblíbená rozšíření sady Visual Studio](https://scottdorman.blog/2014/10/05/favorite-visual-studio-extensions/)  
  
- [Rozšiřitelnost sady Visual Studio](http://www.visualstudioextensibility.com/overview/vs/)  
  
- [Rozšíření sady Visual Studio](https://blog.slaks.net/2013-10-18/extending-visual-studio-part-1-getting-started/)  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření rozšíření pomocí příkazu nabídky](../extensibility/creating-an-extension-with-a-menu-command.md)   
 [Postupy: migrace rozšiřujících projektů do sady Visual Studio 2015](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2015.md)   
 [Nejčastější dotazy: Převádění doplňků na rozšíření VSPackage](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md)   
 [Správa více vláken ve spravovaném kódu](../extensibility/managing-multiple-threads-in-managed-code.md)   
 [Rozšíření nabídek a příkazů](../extensibility/extending-menus-and-commands.md)   
 [Přidávání příkazů do panelů nástrojů](../extensibility/adding-commands-to-toolbars.md)   
 [Rozšíření a přizpůsobení  nástrojů Windows](../extensibility/extending-and-customizing-tool-windows.md)  
   [rozšíření pro Editor a jazykové služby](../extensibility/editor-and-language-service-extensions.md)  
 [Rozšíření projektů](../extensibility/extending-projects.md)   
 [Rozšíření uživatelských nastavení a možností](../extensibility/extending-user-settings-and-options.md)   
 [Vytváření vlastních šablon projektů a položek](../extensibility/creating-custom-project-and-item-templates.md)   
 [Rozšíření vlastností a okna vlastností](../extensibility/extending-properties-and-the-property-window.md)   
 [Rozšíření dalších částí sady Visual Studio](../extensibility/extending-other-parts-of-visual-studio.md)   
 [Používání a poskytování služeb](../extensibility/using-and-providing-services.md)   
 [Rozšíření připojených služeb](../extensibility/extending-connected-services.md)   
 [Správa vspackage](../extensibility/managing-vspackages.md)   
   [izolovaného prostředí sady Visual Studio](../extensibility/visual-studio-isolated-shell.md)  
 [Odeslání rozšíření sady Visual Studio](../extensibility/shipping-visual-studio-extensions.md)   
 [V sadě Visual Studio SDK](../extensibility/internals/inside-the-visual-studio-sdk.md)   
 [Podpora pro sadu Visual Studio SDK](../extensibility/support-for-the-visual-studio-sdk.md)   
 [Archivní](../extensibility/archive.md)   
 [Referenční dokumentace sady Visual Studio SDK](../extensibility/visual-studio-sdk-reference.md)
