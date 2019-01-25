---
title: Kód komentářů ve službě starší verze jazyka | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- comments, supporting in language services [managed package framework]
- language services [managed package framework], commenting code
ms.assetid: 9600d6f0-e2b6-4fe0-b935-fb32affb97a4
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: cd1405456ca9a6ba00926c82bcc7959ea36d26c2
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54765232"
---
# <a name="commenting-code-in-a-legacy-language-service"></a>Kód komentářů ve službě starší verze jazyka
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Programovací jazyky obvykle poskytují způsob poznámky nebo komentáře kódu. Komentář je část textu, který poskytuje další informace o kódu, ale je ignorována během kompilace a interpretace.  
  
 Třídy spravované balíčku rozhraní framework (MPF) poskytují podporu pro přidávání poznámek a odstraňuje se komentování vybraného textu.  
  
## <a name="comment-styles"></a>Styly komentář  
 Existují dvě obecné styly komentář:  
  
1. Řádek komentáře, kde komentář je na jednom řádku.  
  
2. Komentáře bloku, ve kterém komentář může obsahovat více řádků.  
  
   Komentářů řádku mají obvykle počáteční znak (nebo znaky), při komentáře bloku mají počátečních a koncových znaků. Například v jazyce C#, řádkový komentář začíná / /, a začíná blok komentáře / * a končí \*/.  
  
   Když uživatel vybere příkaz **Zakomentovat výběr** z **upravit** -> **Upřesnit** nabídky, příkaz se směruje na <xref:Microsoft.VisualStudio.Package.Source.CommentSpan%2A> metodu <xref:Microsoft.VisualStudio.Package.Source> třídy. Když uživatel vybere příkaz **Odkomentovat výběr**, příkaz se směruje na <xref:Microsoft.VisualStudio.Package.Source.UncommentSpan%2A> metody.  
  
## <a name="supporting-code-comments"></a>Podpora komentářích ke kódu  
 Komentáře jazyka služby podpory kód prostřednictvím může mít `EnableCommenting` s názvem parametru <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> . Tím se nastaví <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableCommenting%2A> vlastnost <xref:Microsoft.VisualStudio.Package.LanguagePreferences> třídy. Další informace o nastavení jazyka servicce funkcí najdete v tématu [registrace služby starší verze jazyka](../../extensibility/internals/registering-a-legacy-language-service1.md)).  
  
 Musí také přepsat <xref:Microsoft.VisualStudio.Package.Source.GetCommentFormat%2A> metodu pro návrat <xref:Microsoft.VisualStudio.Package.CommentInfo> strukturu s znaky komentáře pro váš jazyk. C# – znaky komentáře styl čáry jsou výchozí.  
  
### <a name="example"></a>Příklad  
 Tady je příklad implementace <xref:Microsoft.VisualStudio.Package.Source.GetCommentFormat%2A> metody.  
  
```csharp  
using Microsoft.VisualStudio.Package;  
  
namespace MyLanguagePackage  
{  
    class MySource : Source  
    {  
        public override CommentInfo GetCommentFormat() {  
            CommentInfo info = new CommentInfo();  
            info.LineStart       = "//";  
            info.BlockStart      = "/*";  
            info.BlockEnd        = "*/";  
            info.UseLineComments = true;  
            return info;  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Funkce služby starší verze jazyka](../../extensibility/internals/legacy-language-service-features1.md)   
 [Registrace služby starší verze jazyka](../../extensibility/internals/registering-a-legacy-language-service1.md)
