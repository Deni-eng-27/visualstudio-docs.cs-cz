---
title: 'Postupy: vytvoření informačního kanálu Atom pro soukromou galerii | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: how-to
helpviewer_keywords:
- Atom feed, VSIX private galleries
- VSIX private galleries, Atom feed
ms.assetid: 5897f538-9c41-486f-97d9-a1976d20d9fd
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 269161e831fdb176dbfea844e951597efb467312
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85905857"
---
# <a name="how-to-create-an-atom-feed-for-a-private-gallery"></a>Postupy: vytvoření informačního kanálu Atom pro soukromou galerii
Informační kanál Atom (RSS) můžete vytvořit do umístění v intranetu, které obsahuje rozšíření a přidat informační kanál do **rozšíření a aktualizace** jako soukromou galerii. Další informace najdete v tématu [soukromé Galerie](../extensibility/private-galleries.md).

## <a name="create-an-atom-feed"></a>Vytvoření informačního kanálu Atom
 Chcete-li vytvořit informační kanál Atom jako soukromou galerii, nejprve Shromážděte rozšíření (soubory *. vsix* ) do složky. V případě potřeby je můžete uspořádat do podsložek. Budete také potřebovat následující prostředky:

- *atom.xml* soubor, který rozšíření zpřístupňují jako soukromou galerii. Informace o tom, jak připojit soubor *atom.xml* k **rozšíření a aktualizacím**, najdete v tématu [soukromé Galerie](../extensibility/private-galleries.md).

- Složka, která obsahuje všechny soubory obrázků, které byly extrahovány z rozšíření (například snímky obrazovky). *atom.xml* soubor obsahuje relativní odkazy na tyto image, aby byly dostupné v **rozšířeních a aktualizacích**.

  Předpokládejme například, že jste shromáždili následující dvě rozšíření do složky:

- *Template_Wizard_239. vsix*, což je prázdná šablona projektu VSIX.

- *SelectionHighlight. vsix*, což je nástroj, který zvýrazní všechny instance vybraného slova.

  Obsah souboru *atom.xml* by vypadal podobně jako v následujícím příkladu:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<feed xmlns="http://www.w3.org/2005/Atom">
  <title type="text" />
  <id>uuid:bcecded5-97c8-4d24-96f1-7d9e16652433;id=1</id>
  <updated>2011-04-14T21:25:48Z</updated>
  <entry>
    <id>SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa</id>
    <title type="text">Highlight all occurrences of selected word</title>
    <summary type="text">This extends the editor to highlight ....</summary>
    <published>2011-04-14T14:24:51-07:00</published>
    <updated>2011-04-14T14:24:22-07:00</updated>
    <author>
      <name>Microsoft</name>
    </author>
    <link rel="icon" href="VSIXImages/SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa_Icon_SelectionHighlightIcon.jpg" />
    <link rel="previewimage" href="VSIXImages/SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa_PreviewImage_SelectionHighlight.jpg" />
    <content type="application/octet-stream" src="SelectionHighlight.vsix" />
    <Vsix xmlns="http://schemas.microsoft.com/developer/vsx-syndication-schema/2010" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <Id>SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa</Id>
      <Version>1.31</Version>
      <References />
      <Rating xsi:nil="true" />
      <RatingCount xsi:nil="true" />
      <DownloadCount xsi:nil="true" />
    </Vsix>
  </entry>
  <entry>
    <id>Template_Wizard_239.Microsoft.3b38a7e3-5cbc-4389-a92a-d82tyc2ed592</id>
    ...
  </entry>
</feed>
```

 Všimněte si, že dvě značky odkazů odkazují na snímky obrazovky ve vygenerované složce imagí.

## <a name="see-also"></a>Viz také
- [Soukromé galerie](../extensibility/private-galleries.md)
