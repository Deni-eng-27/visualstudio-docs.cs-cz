---
title: Úloha SignFile – | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#SignFile
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, SignFile task
- SignFile task [MSBuild]
ms.assetid: edef1819-ddeb-4e09-95de-fc7063ba9388
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 08db6a5d22cacc348a9ef36fd9e9857d5b55642a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "65703727"
---
# <a name="signfile-task"></a>SignFile – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Podepíše zadaný soubor pomocí zadaného certifikátu.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `SignFile` úkolu.  
  
 Certifikáty SHA-256 jsou povoleny pouze v počítačích s rozhraním .NET 4,5 a vyšším.  
  
> [!WARNING]
> Počínaje Visual Studio 2013 Update 3 má tento úkol nový podpis, který umožňuje zadat cílovou verzi rozhraní .NET Framework pro daný soubor. Pokud je to možné, doporučujeme používat nový podpis, protože proces MSBuild používá hodnoty hash SHA-256 pouze v případě, že je cílovým rozhraním .NET 4,5 nebo vyšší. Pokud je cílová architektura rozhraní .NET 4,0 nebo nižší, nebude použita hodnota hash SHA-256.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`CertificateThumbprint`|Požadovaný parametr `String`.<br /><br /> Určuje certifikát, který se má použít pro podepisování. Tento certifikát se musí nacházet v osobním úložišti aktuálního uživatele.|  
|`SigningTarget`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>.<br /><br /> Určuje soubory, které se mají podepsat pomocí certifikátu.|  
|`TimestampUrl`|Volitelný `String` parametr.<br /><br /> Určuje adresu URL serveru časového razítka.|  
|`TargetFrameworkVersion`|Verze .NET Framework, která se používá pro cíl.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů Tato úloha dědí parametry z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisů naleznete v tématu [základní třída Task](../msbuild/task-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `SignFile` úlohu k podepsání souborů zadaných v `FilesToSign` kolekci Item s certifikátem zadaným `Certificate` vlastností.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <FileToSign Include="File.exe" />  
    </ItemGroup>  
    <PropertyGroup>  
        <Certificate>Cert.cer</Certificate>  
    </PropertyGroup>  
    <Target Name="Sign">  
        <SignFile  
            CertificateThumbprint="$(CertificateThumbprint)"  
            SigningTarget="@(FileToSign)"   
            TargetFrameworkVersion="v4.5" />  
    </Target>  
</Project>  
```  
  
> [!NOTE]
> Kryptografický otisk certifikátu je hodnota hash SHA-1 certifikátu. Další informace najdete v tématu [získání hodnoty hash SHA-1 certifikátu důvěryhodné kořenové certifikační autority](https://msdn.microsoft.com/dd641990-9a88-4228-a245-017797131a87).  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `Exec` úlohu k podepsání souborů zadaných v `FilesToSign` kolekci Item s certifikátem zadaným `Certificate` vlastností. To můžete použít k podepsání Instalační služba systému Windows souborů během procesu sestavení.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <FileToSign Include="File.msi" />  
    </ItemGroup>  
    <PropertyGroup>  
        <Certificate>Cert.cer</Certificate>  
    </PropertyGroup>  
    <Target Name="Sign">  
        <Exec Command="signtool.exe sign /f CertFile /p Password "@(FileToSign)" "/>  
        <SignFile  
            CertificateThumbprint="$(CertificateThumbprint)"  
            SigningTarget="@(FileToSign)"   
            TargetFrameworkVersion="v4.0" />  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Odkaz na úkol](../msbuild/msbuild-task-reference.md)   
 [Úlohy](../msbuild/msbuild-tasks.md)
