---
title: '&lt;Podpis&gt; – Element (nasazení ClickOnce) | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <Signature> element [ClickOnce deployment manifest]
ms.assetid: c99b07ad-e8ba-43f2-b0d6-3745e7a7c8b3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1c636a4178cf278c2bb0ad75f4e78b94758dda30
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62927485"
---
# <a name="ltsignaturegt-element-clickonce-deployment"></a>&lt;Podpis&gt; – element (nasazení ClickOnce)
Obsahuje informace potřebné k digitálnímu podpisu manifestu nasazení.

## <a name="syntax"></a>Syntaxe

```xml

      <Signature> 
   XML signature information 
</Signature>
```

## <a name="remarks"></a>Poznámky
 Podpis manifestu nasazení použitím signatury obálky je volitelná, avšak doporučená. Další informace o podepisování souborů XML, naleznete v tématu World Wide Web Consortium doporučení, "Syntaxe a zpracování XML – podpis" je popsáno v [ http://www.w3.org/TR/xmldsig-core/ ](http://www.w3.org/TR/xmldsig-core/).

 Pokud chcete pro podepsání manifestu, třeba zadat hodnoty hash pro všechny soubory. Manifest se soubory, které se mají hodnotu hash nelze podepsat, protože uživatelé nemohou ověřit obsah nezašifrované souborů.

## <a name="example"></a>Příklad
 Následující příklad kódu ukazuje `Signature` elementu v manifestu nasazení používané [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení.

```xml
<Signature xmlns="http://www.w3.org/2000/09/xmldsig#">
  <SignedInfo>
    <CanonicalizationMethod Algorithm=
           "http://www.w3.org/TR/2001/REC-xml-c14n-20010315" />
    <SignatureMethod Algorithm=
           "http://www.w3.org/2000/09/xmldsig#rsa-sha1" />
    <Reference URI="">
      <Transforms>
        <Transform Algorithm=
           "http://www.w3.org/2000/09/xmldsig#enveloped-signature" />
      </Transforms>
      <DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />
      <DigestValue>d2z5AE...</DigestValue>
    </Reference>
  </SignedInfo>
  <SignatureValue>
4PHj6SaopoLp...
  </SignatureValue>
  <KeyInfo>
    <X509Data>
      <X509Certificate>
MIIHnTCCBoWgAwIBAgIKJY9+nwAHAAB...
      </X509Certificate>
    </X509Data>
  </KeyInfo>
</Signature>
```

## <a name="see-also"></a>Viz také:
- [ClickOnce – manifest nasazení](../deployment/clickonce-deployment-manifest.md)