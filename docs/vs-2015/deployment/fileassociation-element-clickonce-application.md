---
title: '&lt;fileAssociation&gt; – Element (aplikace ClickOnce) | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <fileAssociation> element [ClickOnce application manifest]
- manifests [ClickOnce], fileAssociation element
ms.assetid: 8f951b4f-54f9-412e-a9e5-af4e379fcf08
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 3a3589387b00eb1ade9c9b60b0845bc2421b3486
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633549"
---
# <a name="ltfileassociationgt-element-clickonce-application"></a>&lt;fileAssociation&gt; – Element (aplikace ClickOnce)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [ &lt;fileAssociation&gt; – Element (aplikace ClickOnce)](https://docs.microsoft.com/visualstudio/deployment/fileassociation-element-clickonce-application).  
  
Určuje příponu souboru, který se má přidružit aplikaci.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<fileAssociation  
    xmlns="urn:schemas-microsoft-com:clickonce.v1"  
    extension  
    description  
    progid  
    defaultIcon  
/>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `fileAssociation` Element je volitelné. Element má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`extension`|Požadováno. Přípona souboru, který má být přidružena k aplikaci.|  
|`description`|Požadováno. Popis typu souboru pro použití v prostředí.|  
|`progid`|Požadováno. Název jednoznačně identifikující tento typ souboru.|  
|`defaultIcon`|Požadováno. Určuje ikonu pro soubory s touto příponou. Soubor ikony musí být zadaný pomocí [ \<soubor > – Element](../deployment/file-element-clickonce-application.md) v rámci [ \<sestavení > Element](../deployment/assembly-element-clickonce-application.md) , který obsahuje tento element.|  
  
## <a name="remarks"></a>Poznámky  
 Tento element musí obsahovat odkaz na obor názvů XML "urn: schémata-microsoft-com:clickonce.v1". Pokud `<fileAssociation>` element se používá, musí být pozdější než `<application>` v nadřazeném prvku [ \<sestavení > Element](../deployment/assembly-element-clickonce-application.md).  
  
 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] nepřepíše existující přidružení souborů. Aplikace ClickOnce však můžete přepsat příponu souboru pro aktuálního uživatele. Po odinstalaci aplikace ClickOnce ClickOnce odstraní přidružení souborů pro uživatele a znovu je aktivní přidružení vázaná na počítač.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje `fileAssociation` prvky v aplikaci manifestu pro textový editor aplikace nasazené pomocí [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]. Tento příklad kódu také zahrnuje [ \<soubor > – Element](../deployment/file-element-clickonce-application.md) požadavku `defaultIcon` atribut.  
  
```  
<file name="text.ico" size="4286">  
  <hash>  
    <dsig:Transforms>  
      <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
    </dsig:Transforms>  
    <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
    <dsig:DigestValue>0joAqhmfeBb93ZneZv/oTMP2brY=</dsig:DigestValue>  
  </hash>  
</file>  
<file name="writing.ico" size="9662">  
  <hash>  
    <dsig:Transforms>  
      <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
    </dsig:Transforms>  
    <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
    <dsig:DigestValue>2cL2U7cm13nG40v9MQdxYKazIwI=</dsig:DigestValue>  
  </hash>  
</file>  
<fileAssociation xmlns="urn:schemas-microsoft-com:clickonce.v1" extension=".text" description="Text  Document (ClickOnce)" progid="Text.Document" defaultIcon="text.ico" />  
<fileAssociation xmlns="urn:schemas-microsoft-com:clickonce.v1" extension=".writing" description="Writings (ClickOnce)" progid="Writing.Document" defaultIcon="writing.ico" />  
```  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – manifest aplikace ](../deployment/clickonce-application-manifest.md)



