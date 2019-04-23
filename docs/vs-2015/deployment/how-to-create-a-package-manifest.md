---
title: 'Postupy: Vytvoření manifestu balíčku | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- package files [Windows Installer]
- package files [ClickOnce]
- prerequisites, custom bootstrapper package
- dependencies, custom bootstrapper packages
ms.assetid: 5aecc507-2764-42f2-ae6f-c227971cf0af
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c711c50ab484cc88b1d6aff5c8e3018cead69953
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60046012"
---
# <a name="how-to-create-a-package-manifest"></a>Postupy: Vytvoření manifestu balíčku
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nasazení nezbytných součástí pro vaši aplikaci, můžete balíček zaváděcího nástroje. Balíček zaváděcího nástroje obsahuje jeden produkt soubor manifestu ale manifest balíčku pro každé národní prostředí. Sdílené funkce přes různé lokalizované verze by měly patřit do manifestu produktu.  
  
 Další informace o manifestech balíčku najdete v tématu [jak: Vytvoření manifestu produktu](../deployment/how-to-create-a-product-manifest.md).  
  
## <a name="creating-the-package-manifest"></a>Vytvoření manifestu balíčku  
  
#### <a name="to-create-the-package-manifest"></a>K vytvoření manifestu balíčku  
  
1. Vytvořte adresář pro balíček zaváděcího nástroje. Tento příklad používá C:\package.  
  
2. Vytvořte podadresář s názvem národního prostředí, například cs pro angličtinu.  
  
3. V sadě Visual Studio, vytvořit soubor XML, který je pojmenován `package.xml`a uložte ho do složky C:\package\en.  
  
4. Přidejte XML pro název balíčku zaváděcího nástroje, jazykovou verzi pro tento manifest balíčku lokalizované a volitelné licenční smlouvu. Následující kód XML používá proměnné `DisplayName` a `Culture`, které jsou definovány v prvku novější.  
  
    ```  
    <Package  
        xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"  
        Name="DisplayName"  
        Culture="Culture"  
        LicenseAgreement="eula.txt">  
    ```  
  
5. Přidejte XML pro všechny soubory, které jsou v adresáři specifických pro národní prostředí. Následující kód XML používá soubor, který je pojmenován eula.txt, který je možné použít **en** národní prostředí.  
  
    ```  
    <PackageFiles>  
      <PackageFile Name="eula.txt"/>  
    </PackageFiles>  
    ```  
  
6. Přidejte kód jazyka XML pro definování lokalizovatelných řetězců pro balíček zaváděcího nástroje. Následující kód XML přidá chybové řetězce pro národní prostředí cs.  
  
    ```  
      <Strings>  
        <String Name="DisplayName">Custom Bootstrapper Package</String>  
        <String Name="CultureName">en</String>  
        <String Name="NotAnAdmin">You must be an administrator to install   
    this package.</String>  
        <String Name="GeneralFailure">A general error has occurred while   
    installing this package.</String>  
    </Strings>  
    ```  
  
7. Zkopírujte složku C:\package do adresáře zaváděcího nástroje sady Visual Studio. Pro sadu Visual Studio 2010 je to adresář SDKs\Windows\v7.0A\Bootstrapper\Packages \Program Files\Microsoft.  
  
## <a name="example"></a>Příklad  
 Manifest balíčku obsahuje informace o specifických pro národní prostředí, jako jsou chybové zprávy, licenční podmínky pro software a jazykových sad.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<Package  
  xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"  
  Name="DisplayName"  
  Culture="Culture"  
  LicenseAgreement="eula.txt">  
  
  <PackageFiles>  
    <PackageFile Name="eula.txt"/>  
  </PackageFiles>  
  
  <Strings>  
    <String Name="DisplayName">Custom Bootstrapper Package</String>  
    <String Name="Culture">en</String>  
    <String Name="NotAnAdmin">You must be an administrator to install this package.</String>  
    <String Name="GeneralFailure">A general error has occurred while   
installing this package.</String>  
  </Strings>  
</Package>  
```  
  
## <a name="see-also"></a>Viz také  
 [Referenční schéma balíčku a produktu](../deployment/product-and-package-schema-reference.md)
