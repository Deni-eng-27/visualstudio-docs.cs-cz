---
title: Resolvekeysource – úloha | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ResolveKeySource
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ResolveKeySource task [MSBuild]
- MSBuild, ResolveKeySource task
ms.assetid: 449f06c2-e9aa-4236-ab1e-c45c25452b2e
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: bd5cbe2f4998ab78ce39cde4b26a38b13c70b2f8
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59649288"
---
# <a name="resolvekeysource-task"></a>ResolveKeySource – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Určuje zdroj klíče silného názvu.  
  
## <a name="task-parameters"></a>Parametry úlohy  
 Následující tabulka popisuje parametry `ResolveKeySource` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`AutoClosePasswordPromptShow`|Volitelné `Int32` parametru.<br /><br /> Získá nebo nastaví dobu, během několika sekund, chcete-li zobrazit počet si zprávu.|  
|`AutoClosePasswordPromptTimeout`|Volitelné `Int32` parametru.<br /><br /> Získá nebo nastaví dobu, během několika sekund se má čekat před zavřením dialogové okno Příkazový řádek heslo.|  
|`CertificateFile`|Volitelné `String` parametru.<br /><br /> Získá nebo nastaví cestu k souboru certifikátu.|  
|`CertificateThumbprint`|Volitelné `String` parametru.<br /><br /> Získá nebo nastaví kryptografický otisk certifikátu.|  
|`KeyFile`|Volitelné `String` parametru.<br /><br /> Získá nebo nastaví cestu k souboru klíče.|  
|`ResolvedKeyContainer`|Volitelné `String` výstupní parametr.<br /><br /> Získá nebo nastaví přeložit kontejneru klíčů.|  
|`ResolvedKeyFile`|Volitelné `String` výstupní parametr.<br /><br /> Získá nebo nastaví přeložit soubor klíče.|  
|`ResolvedThumbprint`|Volitelné `String` výstupní parametr.<br /><br /> Získá nebo nastaví kryptografický otisk certifikátu přeložit.|  
|`ShowImportDialogDespitePreviousFailures`|Volitelné `Boolean` parametru.<br /><br /> Pokud `true`, zobrazit dialogové okno importu bez ohledu na předchozí chyby.|  
|`SuppressAutoClosePasswordPrompt`|Volitelné `Boolean` parametru.<br /><br /> Získá nebo nastaví logickou hodnotu, která určuje, zda dialogové okno Příkazový řádek heslo by neměl automatickým ukončením.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
