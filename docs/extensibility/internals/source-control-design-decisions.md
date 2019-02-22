---
title: Zdroj rozhodnutí o návrhu správy | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], design decisions
ms.assetid: 5f60ec1a-5a74-4362-8293-817a4dd73872
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8378bf0a95ca9a844de4985f7403f04978607dcd
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56615270"
---
# <a name="source-control-design-decisions"></a>Rozhodnutí o návrhu správy zdrojového kódu
Následující rozhodnutí o návrhu pro projekty třeba zvážit při implementaci správy zdrojového kódu.

## <a name="will-information-be-shared-or-private"></a>Bude informace sdílené nebo soukromé?
 Nejdůležitější rozhodnutí o návrhu, můžete je informací je sdílet a co je privátní. Například seznam souborů projektu, které se sdílí, ale v tomto seznamu souborů, někteří uživatelé měli mít soukromé soubory. Nastavení kompilátoru sdílejí, ale je obecně privátní počáteční projekt. Nastavení jsou čistě sdílené, sdílené s přepsání nebo čistě privátní. Návrh soukromé položky, jako je možnosti uživatele řešení (.suo) soubory nejsou zapsány do [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)]. Nezapomeňte si uložit žádné soukromé informace v soukromé soubory, jako je například soubor .suo, nebo konkrétní soukromých soubor vytvoříte, například. csproj.user souboru pro jazyk Visual C# nebo. vbproj.user soubor v jazyce Visual Basic.

 Toto rozhodnutí není kompletní a provádět na základě jednotlivých položkách.

## <a name="will-the-project-include-special-files"></a>Projekt bude obsahovat speciální soubory?
 Další rozhodnutí o návrhu důležité je, zda strukturu projektu používá speciální soubory. Speciální soubory jsou skryté soubory, které tvoří základ soubory, které jsou viditelné v Průzkumníku řešení a vrácení se změnami a rezervace dialogová okna. Pokud používáte speciální souborů, postupujte podle následujících pokynů:

1.  Nepřidružujte speciální soubory k kořenový uzel projektu – to znamená s projektem samotném souboru. Váš soubor projektu musí být jeden soubor.

2.  Když jsou speciální soubory přidat, odebrat nebo přejmenovat v projektu odpovídající <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2> události musí být aktivována s příznakem, který označuje soubory jsou speciální soubory. Tyto události jsou nazývány prostředím v reakci na projektu volání odpovídající <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> metody.

3.  Když projekt nebo editor volá <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> pro soubor, speciální soubory přidružené k tento soubor nejsou rezervovány automaticky. Speciální soubory v předejte ho spolu s nadřazený soubor. Zjistí vztah mezi všechny soubory, které jsou předány v prostředí a odpovídajícím způsobem Skrýt speciální soubory v Uživatelském rozhraní vrácení se změnami.

## <a name="see-also"></a>Viz také
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>
- [Podpora správy zdrojového kódu](../../extensibility/internals/supporting-source-control.md)