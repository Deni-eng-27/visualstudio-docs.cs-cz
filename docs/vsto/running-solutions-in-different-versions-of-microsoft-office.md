---
title: "Spouštění řešení v různých verzích systému Microsoft Office | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- solutions [Office development in Visual Studio], multiple Office versions
- Office applications [Office development in Visual Studio], multiple Office versions
- Office development in Visual Studio, multiple Office versions
- Office solutions [Office development in Visual Studio]
- multiple Office versions
ms.assetid: 414e7741-c07d-4900-9d10-68b821413b3f
caps.latest.revision: "61"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 93e365d335f835196576ad9ed10216e904e81f93
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="running-solutions-in-different-versions-of-microsoft-office"></a>Spouštění řešení v různých verzích systému Microsoft Office
    
## <a name="running-office-solutions-created-by-using-visual-studio-2010-and-above"></a>Spouštění řešení Office vytvořili pomocí sady Visual Studio 2010 a vyšší  
  
|Verze systému Office cílem šablona projektu|Cílové rozhraní .NET Framework projektu<sup>1</sup>|Verze systému Office, která se může spustit řešení|Vyžaduje modul runtime na počítači koncového uživatele|  
|--------------------------------------------------------|------------------------------------------------------|--------------------------------------------------|-------------------------------------------|  
|Office 2016 a[!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)]|[!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]nebo novější|Office 2016<br /><br /> [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)]<br /><br /> [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]<br /><br /> Systém Microsoft Office 2007<sup>2</sup>|Visual Studio 2010 Tools for Office Runtime|  
|[!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]|[!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]nebo novější|Office 2016<br /><br /> [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)]<br /><br /> [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]<br /><br /> Systém Microsoft Office 2007<sup>2</sup>|Visual Studio 2010 Tools for Office Runtime|  
|[!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]|.NET Framework 3.5|Office 2016<br /><br /> [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)]<br /><br /> [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]|Visual Studio 2010 Tools for Office Runtime|  
|2007 – systém Microsoft Office|[!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]nebo novější,<br /><br /> or<br /><br /> .NET Framework 3.5|Office 2016<br /><br /> [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)]<br /><br /> [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]<br /><br /> 2007 – systém Microsoft Office|Visual Studio 2010 Tools for Office Runtime|  
  
 1. Verze rozhraní .NET Framework vyžadované vaše cíle projektu do počítačů koncových uživatelů pro vaše řešení ke spuštění. Například pokud cílem vašeho projektu je .NET Framework 3.5, je požadováno rozhraní .NET Framework 3.5 v počítačích koncových uživatelů. V tomto příkladu řešení nespustí, pokud je to pouze [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] je nainstalován v počítačích koncových uživatelů.  
  
 2. V tomto scénáři řešení se spustí bez chyb v systému Microsoft Office 2007 pouze v případě, že jej nebude používat funkce, které nově jsou v [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)].  
  
## <a name="running-office-solutions-created-by-using-versions-of-visual-studio-prior-to-visual-studio-2010"></a>Spuštění Office řešení vytvořili pomocí pomocí verze nástroje sady Visual Studio před Visual Studio 2010  
 Aplikace Microsoft Office se dají spustit řešení vytvořená pomocí verze sady Visual Studio před Visual Studio 2010. V některých případech tato řešení vyžadují různé verze [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Různé verze [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] může být nainstalovaná--vedle sebe na stejném počítači.  
  
 Následující tabulka uvádí, jaké verze systému Microsoft Office můžete spustit řešení vytvořená pomocí předchozí verze sady Visual Studio a které verze [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] a rozhraní .NET Framework, které jsou požadovány pro každé řešení.  
  
|Edice Visual Studia použít k vytvoření řešení|Verze systému Office cílem šablona projektu|Verze systému Office, která se může spustit řešení|Vyžaduje modul runtime na počítači koncového uživatele|Požadovaná verze rozhraní .NET Framework na počítači koncového uživatele|  
|----------------------------------------------------------|--------------------------------------------------------|--------------------------------------------------|-------------------------------------------|----------------------------------------------------------|  
|Visual Studio 2008 Professional<br /><br /> or<br /><br /> Visual Studio Team System 2008|2007 – systém Microsoft Office|[!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)]a [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)] <sup>1</sup><br /><br /> 2007 – systém Microsoft Office|Visual Studio 2010 Tools for Office Runtime<sup>1</sup><br /><br /> or<br /><br /> Visual Studio Tools pro systém Microsoft Office (verze 3.0 Runtime)|.NET Framework 3.5|  
|Jeden z následujících edic Visual Studio 2005 s VSTO 2005 SE<sup>2</sup> nainstalován:<br /><br /> – Visual Studio 2005 Tools for Office<br />– Visual Studio Team System 2005<br />– Visual Studio 2005 Professional|2007 – systém Microsoft Office|[!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)]a [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)] (32bitová verze pouze<sup>3</sup>)<br /><br /> 2007 – systém Microsoft Office|Druhé sadě Visual Studio 2005 Tools for Office Edition Runtime|Rozhraní .NET framework 2.0, .NET Framework 3.0 nebo rozhraní .NET Framework 3.5|  
|Některé z následujících edic sady Visual Studio:<br /><br /> – Visual Studio 2008 Professional<br />– Visual Studio Team System 2008<br />– Visual Studio 2005 Tools for Office (s nebo bez VSTO 2005 SE<sup>2</sup> nainstalované)<br />– Visual Studio Team System 2005 (s nebo bez VSTO 2005 SE<sup>2</sup> nainstalované)<br />– Visual Studio 2005 Professional with VSTO 2005 SE<sup>2</sup> nainstalován|Aplikace Microsoft Office 2003|[!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)]a [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)] (32bitová verze pouze<sup>3</sup>)<br /><br /> 2007 – systém Microsoft Office<br /><br /> Aplikace Microsoft Office 2003|Druhé sadě Visual Studio 2005 Tools for Office Edition Runtime|Rozhraní .NET framework 2.0, .NET Framework 3.0 nebo rozhraní .NET Framework 3.5|  
  
 1. [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)]a [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)] aplikace obsahovat sadu Visual Studio 2010 Tools for Office Runtime. Proto tyto aplikace vždycky používat sadu Visual Studio 2010 Tools pro systém Office Runtime, nikoli sady Visual Studio Tools pro systém Microsoft Office (verze 3.0 Runtime) v tomto scénáři. Aplikace v systému Microsoft Office 2007, můžete použít sadu Visual Studio 2010 Tools pro systém Office Runtime nebo sady Visual Studio Tools pro systém Microsoft Office (verze 3.0 Runtime).  
  
 2. VSTO 2005 SE představuje bezplatné rozšíření sady Visual Studio, který poskytuje šablony projektu doplňku VSTO pro Microsoft Office 2003 a systém Microsoft Office 2007. Dají se instalovat s Visual Studio 2005 Professional, Visual Studio 2005 Tools for Office nebo edice sady Visual Studio Team System 2005. Další informace najdete v tématu [Visual Studio 2005 Tools for Office Druhé vydání](http://go.microsoft.com/fwlink/?LinkId=148446).  
  
 3. Řešení pro systém Office vyžadující sady Visual Studio 2005 Tools for Office Runtime druhý Edition nejsou kompatibilní s verzí 64-bit [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] a [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]. Ke spuštění těchto řešení v 64bitové edici [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] nebo [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)], musíte provést upgrade projektu pro [!INCLUDE[vs_dev10_long](../sharepoint/includes/vs-dev10-long-md.md)] nebo Visual Studio 2008 projektu, jehož cílem systém Microsoft Office 2007.  
  
## <a name="see-also"></a>Viz také  
 [Návrh a vytváření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)   
 [Visual Studio Tools for Office Runtime – přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [Postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Visual Studio Tools for Office Runtime instalace scénáře](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md)   
 [Konfigurace počítače pro vývoj řešení pro systém Office](../vsto/running-solutions-in-different-versions-of-microsoft-office.md)  
  
  