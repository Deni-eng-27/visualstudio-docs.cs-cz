---
title: "Rozhraní průvodce (IDTWizard) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDTWizard interface
- wizards, interface
ms.assetid: 09618d9d-d115-45b6-bccc-de328994b39c
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 57e3ceda07abadbf00e67e740bd276430157eabe
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="wizard-interface-idtwizard"></a>Rozhraní průvodce (IDTWizard)
Integrované vývojové prostředí (IDE) používá <xref:EnvDTE.IDTWizard> rozhraní ke komunikaci s použitím průvodců. Průvodci musí toto rozhraní implementují kvůli nainstalují v prostředí IDE.  
  
 <xref:EnvDTE.IDTWizard.Execute%2A> Metoda je jedinou metodou přidružené <xref:EnvDTE.IDTWizard> rozhraní. Tuto metodu implementovat průvodců a rozhraní IDE volá metodu na rozhraní. Následující příklad ukazuje podpis metody.  
  
```  
/* IDTWizard Method */  
STDMETHOD(Execute)(THIS_  
   /* [in] */ IDispatch *Application,  
   /* [in] */ long hwndOwner,  
   /* [in] */ SAFEARRAY * *ContextParams,  
   /* [in] */ SAFEARRAY * *CustomParams,  
   /* [out] [in] */ wizardResult *RetVal  
   );  
```  
  
 Mechanismus spuštění je podobné pro oba **nový projekt** a **přidat novou položku**průvodců. Chcete-li spustit buď, zavolejte <xref:EnvDTE.IDTWizard> rozhraní definované v Dteinternal.h. Jediným rozdílem je sada kontextu a vlastních parametrů, které se budou předávat rozhraní při volání rozhraní.  
  
 Následující informace popisují <xref:EnvDTE.IDTWizard> rozhraní, které se musí implementovat průvodců pro práci v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE. Volání IDE <xref:EnvDTE.IDTWizard.Execute%2A> metoda v Průvodci předání následující:  
  
-   Objekt DTE  
  
     Objekt DTE je kořen automatizace modelu.  
  
-   Popisovač pro dialogové okno jak je znázorněno v segmentu kódu `hwndOwner ([in] long)`.  
  
     Tento průvodce využívá `hwndOwner` jako nadřízenou pro dialogové okno průvodce.  
  
-   Kontextové parametry předaný rozhraní jako typ variant pro SAFEARRAY jak je uvedené v segmentu kódu `[in] SAFEARRAY (VARIANT)* ContextParams`.  
  
     Kontextové parametry obsahovat pole hodnot, které jsou specifické pro druh průvodce spuštění a aktuálním stavu projektu. Prostředí IDE předá kontextových parametrů v průvodci. Další informace najdete v tématu [kontextové parametry](../../extensibility/internals/context-parameters.md).  
  
-   Vlastní parametry předaný rozhraní jako hodnotu typu variant pro SAFEARRAY jak je uvedené v segmentu kódu `[in] SAFEARRAY (VARIANT)* CustomParams`.  
  
     Vlastní parametry obsahovat pole vlastní parametry. Soubor .vsz předá vlastní parametry prostředí IDE. Hodnoty jsou určeny `Param=` příkazy. Další informace najdete v tématu [vlastní parametry](../../extensibility/internals/custom-parameters.md).  
  
-   Návratové hodnoty pro rozhraní  
  
    ```  
    wizardResultSuccess = -1,  
    wizardResultFailure = 0  
    wizardResultCancel = 1  
    wizardResultBackout = 2  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Kontextové parametry](../../extensibility/internals/context-parameters.md)   
 [Vlastní parametry](../../extensibility/internals/custom-parameters.md)   
 [Průvodci](../../extensibility/internals/wizards.md)   
 [Soubor průvodce (.Vsz)](../../extensibility/internals/wizard-dot-vsz-file.md)