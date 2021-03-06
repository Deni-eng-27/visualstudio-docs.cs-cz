---
title: Přidávání adresářů do dialogového okna Nový projekt | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- New Project dialog box, extending
ms.assetid: 53b328f5-20bb-49a3-bf9e-1818f4fbdf50
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 827e383bba13c9742deb654bf3d680adeb3c109b
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80710236"
---
# <a name="add-directories-to-the-new-project-dialog-box"></a>Přidání adresářů do dialogového okna Nový projekt
Při vytváření nových typů projektů můžete také zaregistrovat nový adresář v dialogovém okně **Nový projekt** a zobrazit je pro použití jako šablony. Následující příklad kódu vysvětluje, jak registrovat nový adresář, označovaný také jako uzel. V příkladu jsou zaregistrovány šablony vystavené VSPackage, *CLSID_Package*. V důsledku toho levá strana dialogového okna **Nový projekt** nabízí přidaný uzel s názvem určeným prostředkem *Folder_Label_ResID* . Tento prostředek je načtený z knihovny VSPackage Satellite DLL.

 Hodnota **složky** představuje identifikátor GUID složky, pod kterou se zobrazuje uzel *Folder_Label_ResID* . V tomto příkladu identifikátor GUID představuje složku **ostatní projekty** v podokně **typy projektů** v dialogovém okně **Nový projekt** . Pokud se hodnota **ostatní projekty** nevyskytuje, je popisek umístěn na nejvyšší úrovni.

 `TemplatesDir`Hodnota určuje úplnou cestu k adresáři, který obsahuje šablony projektu. Tyto soubory mohou být buď soubory *. vsz* , nebo typické soubory šablon, které mají být klonovány.

 Zadáte `TemplatesLocalizedSubDir` -li hodnotu, musí se jednat o ID prostředku řetězce, který má název podadresáře `TemplatesDir` obsahující lokalizované šablony. Vzhledem k tomu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] , že načte prostředek řetězce z satelitní knihovny DLL, pokud nějaký máte, každá satelitní knihovna DLL může obsahovat jiný název podadresáře. `SortPriority`Hodnota určuje prioritu řazení.

```
NoRemove NewProjectTemplates
{
    NoRemove TemplateDirs
  {
    ForceRemove %CLSID_Package%
    {
      ForceRemove /1 = s '#%Folder_Label_ResID%'
      {
        val Folder = s '{DCF2A94A-45B0-11D1-ADBF-00C04FB6BE4C}'
        val TemplatesDir = s '%Template_Path%'
        val TemplatesLocalizedSubDir = s '#100'
        val SortPriority = d 1000
      }
    }
  }
}
```

## <a name="see-also"></a>Viz také
- [Registrace šablon projektů a položek](../../extensibility/internals/registering-project-and-item-templates.md)
- [Přidání položek do dialogového okna Přidat novou položku](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)
- [Přidání adresářů do dialogového okna Přidat novou položku](../../extensibility/internals/adding-directories-to-the-add-new-item-dialog-box.md)
