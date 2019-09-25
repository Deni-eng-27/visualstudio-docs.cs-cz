---
title: 'CA2100: Zkontrolujte chyby zabezpečení u dotazů SQL'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- Review SQL queries for security vulnerabilities
- ReviewSqlQueriesForSecurityVulnerabilities
- CA2100
helpviewer_keywords:
- CA2100
- ReviewSqlQueriesForSecurityVulnerabilities
ms.assetid: 79670604-c02a-448d-9c0e-7ea0120bc5fe
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 837abb051467135b6332b53b2c59e5016d3adff6
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/24/2019
ms.locfileid: "71233055"
---
# <a name="ca2100-review-sql-queries-for-security-vulnerabilities"></a>CA2100: Zkontrolujte chyby zabezpečení u dotazů SQL

|||
|-|-|
|TypeName|ReviewSqlQueriesForSecurityVulnerabilities|
|CheckId|CA2100|
|Kategorie|Microsoft.Security|
|Zásadní změna|Nenarušující|

## <a name="cause"></a>příčina

Metoda nastavuje <xref:System.Data.IDbCommand.CommandText%2A?displayProperty=fullName> vlastnost pomocí řetězce, který je sestaven z řetězcového argumentu metody.

## <a name="rule-description"></a>Popis pravidla

Toto pravidlo předpokládá, že řetězcový argument obsahuje vstup uživatele. Řetězec příkazu SQL sestavený ze vstupu uživatele je ohrožen útoky prostřednictvím injektáže SQL. V případě útoku prostřednictvím injektáže SQL uživatel se zlými úmysly dodává vstup, který mění návrh dotazu při pokusu o poškození nebo získání neoprávněného přístupu k podkladové databázi. Mezi obvyklé techniky patří vložení jednoduché uvozovky nebo apostrofu, což je oddělovač řetězcového literálu SQL. dvě pomlčky, což znamená komentář SQL; a středníkem, který indikuje, že následuje nový příkaz. Pokud musí být vstup uživatele součástí dotazu, použijte jednu z následujících možností, která je uvedena v řádu účinnosti, aby se snížilo riziko útoku.

- Použijte uloženou proceduru.

- Použijte parametrizovaný řetězec příkazu.

- Před sestavením řetězce příkazu ověřte vstup uživatele pro typ i obsah.

Následující typy rozhraní .NET implementují <xref:System.Data.IDbCommand.CommandText%2A> vlastnost nebo poskytují konstruktory, které nastavily vlastnost pomocí řetězcového argumentu.

- <xref:System.Data.Odbc.OdbcCommand?displayProperty=fullName> a <xref:System.Data.Odbc.OdbcDataAdapter?displayProperty=fullName>

- <xref:System.Data.OleDb.OleDbCommand?displayProperty=fullName> a <xref:System.Data.OleDb.OleDbDataAdapter?displayProperty=fullName>

- <xref:System.Data.OracleClient.OracleCommand?displayProperty=fullName> a <xref:System.Data.OracleClient.OracleDataAdapter?displayProperty=fullName>

- <xref:System.Data.SqlClient.SqlCommand?displayProperty=fullName> a <xref:System.Data.SqlClient.SqlDataAdapter?displayProperty=fullName>

Všimněte si, že toto pravidlo je porušené, když se metoda ToString typu používá explicitně nebo implicitně k sestavení řetězce dotazu. Následuje příklad.

```csharp
int x = 10;
string query = "SELECT TOP " + x.ToString() + " FROM Table";
```

Toto pravidlo je porušeno, protože uživatel se zlými úmysly může přepsat metodu ToString ().

Toto pravidlo je porušeno také v případě implicitního použití ToString.

```csharp
int x = 10;
string query = String.Format("SELECT TOP {0} FROM Table", x);
```

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení tohoto pravidla, použijte parametrizovaný dotaz.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Pokud text příkazu neobsahuje žádný vstup uživatele, je bezpečné potlačit upozornění od tohoto pravidla.

## <a name="example"></a>Příklad

Následující příklad ukazuje metodu, `UnsafeQuery`, která porušuje pravidlo a metodu, `SaferQuery`,, který splňuje pravidlo pomocí parametrizovaného řetězce příkazu.

[!code-vb[FxCop.Security.ReviewSqlQueries#1](../code-quality/codesnippet/VisualBasic/ca2100-review-sql-queries-for-security-vulnerabilities_1.vb)]
[!code-csharp[FxCop.Security.ReviewSqlQueries#1](../code-quality/codesnippet/CSharp/ca2100-review-sql-queries-for-security-vulnerabilities_1.cs)]
[!code-cpp[FxCop.Security.ReviewSqlQueries#1](../code-quality/codesnippet/CPP/ca2100-review-sql-queries-for-security-vulnerabilities_1.cpp)]

## <a name="see-also"></a>Viz také:

- [Přehled zabezpečení](/dotnet/framework/data/adonet/security-overview)