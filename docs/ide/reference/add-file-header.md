---
title: Přidání hlavičky souboru
ms.date: 07/10/2020
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 2c69f73989e898c44bdef6cf008d48f6c918652a
ms.sourcegitcommit: a801ca3269274ce1de4f6b2c3f40b58bbaa3f460
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/25/2020
ms.locfileid: "88801318"
---
# <a name="add-file-header"></a>Přidání hlavičky souboru

Tato generace kódu platí pro:

- C#

- Visual Basic

**Co:** Do existujících souborů, projektů a řešení můžete přidat záhlaví souborů pomocí [EditorConfig](https://docs.microsoft.com/visualstudio/ide/create-portable-custom-editor-options#add-an-editorconfig-file-to-a-project).

**Když:** Chcete snadno přidat záhlaví souboru do souborů, projektů a řešení.

**Proč:** Váš tým vyžaduje, abyste zahrnuli hlavičku souboru pro účely autorského práva. 

## <a name="how-to"></a>Postupy

1. Přidejte [EditorConfig](https://docs.microsoft.com/visualstudio/ide/create-portable-custom-editor-options#add-an-editorconfig-file-to-a-project) do projektu nebo řešení, pokud ho ještě nemáte.

2. Do souboru EditorConfig přidejte následující pravidlo: *file_header_template*.

3. Nastavte hodnotu pravidla tak, aby se rovnala textu záhlaví, který chcete použít. Můžete použít `{fileName}` jako zástupný symbol pro název souboru.

    ![Pravidlo záhlaví souboru EditorConfig](media/add-file-header-rule.png)

    > [!NOTE]
    > V EditorConfig nemůžete mít explicitní víceřádkové řádky a k vložení nových řádků bude potřeba použít znak nového řádku UNIX.

4. Umístěte blikající kurzor na první řádek jakéhokoli souboru C# nebo Visual Basic.

5. Stiskněte klávesu **CTRL** + **.** pro aktivaci nabídky **rychlé akce a refaktoringy** .

6. Vyberte možnost **Přidat hlavičku souboru**. 

    ![Pravidlo záhlaví souboru EditorConfig](media/add-file-header.png)

7. Chcete-li použít hlavičku souboru na celý projekt nebo řešení, vyberte možnost **projekt** nebo **řešení** pod možností **opravit všechny výskyty v:** .

8. Otevře se dialogové okno **opravit všechny výskyty** , kde můžete zobrazit náhled změn.

    ![Dialog opravit všechny výskyty](media/file-header-preview-changes.png)

8. Chcete-li změny použít, vyberte **použít** .

## <a name="see-also"></a>Viz také

- [Generování kódu](../code-generation-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)
