---
title: 'Postupy: Přidání závislosti k balíčku VSIX | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- package reference
- package assembly
- package dll
- vsix reference
ms.assetid: 8f20177b-dab9-43a3-b959-81a591b451d6
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 97118134106614e1e04cd2bc328ad31480618116
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54765446"
---
# <a name="how-to-add-a-dependency-to-a-vsix-package"></a>Postupy: Přidání závislosti k balíčku VSIX
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete nastavit nasazení balíčku VSIX, který instaluje všechny závislosti, které ještě nejsou k dispozici na cílovém počítači. K tomu patří VSIX závislostí pro soubor source.extension.vsixmanifest.  
  
#### <a name="to-add-a-dependency"></a>Chcete-li přidat závislost  
  
1.  Otevřete soubor source.extension.vsixmanifest v **návrhu** zobrazení. Přejděte **závislosti** kartě a klikněte na tlačítko **nový**.  
  
2.  Přidání nainstalovaných rozšíření: v **přidat novou závislost** dialogovém okně vyberte **nainstalované rozšíření** a potom v **název**, vyberte v seznamu rozšíření.  
  
3.  Chcete-li přidat další VSIX, který není nainstalován:: v **přidat novou závislost** dialogovém okně vyberte **souboru v systému souborů** a pak pomocí **Procházet** tlačítko a vyberte rozšíření VSIX.  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu 1.0 rozšíření VSIX](http://msdn.microsoft.com/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)   
 [Anatomie balíčku VSIX](../extensibility/anatomy-of-a-vsix-package.md)   
 [Příprava rozšíření pro nasazení Instalační služby systému Windows](../extensibility/preparing-extensions-for-windows-installer-deployment.md)
