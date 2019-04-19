---
title: 'CA2302: Ujistěte se, že BinaryFormatter.Binder nastavený před voláním BinaryFormatter.Deserialize'
ms.date: 04/05/2019
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: fb997d8184ea9459b46eee95bfe2863e8c1c6ed0
ms.sourcegitcommit: 0e22ead8234b2c4467bcd0dc047b4ac5fb39b977
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/09/2019
ms.locfileid: "59367360"
---
# <a name="ca2302-ensure-binaryformatterbinder-is-set-before-calling-binaryformatterdeserialize"></a>CA2302: Ujistěte se, že BinaryFormatter.Binder nastavený před voláním BinaryFormatter.Deserialize

|||
|-|-|
|TypeName|EnsureBinaryFormatterBinderIsSetBeforeCallingBinaryFormatterDeserialize|
|CheckId|CA2302|
|Kategorie|Microsoft.Security|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina

A <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType> metody deserializace byla volána nebo je odkazované a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder> vlastnost může mít hodnotu null.

## <a name="rule-description"></a>Popis pravidla

[!INCLUDE[insecure-deserializers-description](includes/insecure-deserializers-description-md.md)]

Toto pravidlo vyhledá <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType> deserializace volání metody nebo odkazy, když <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> při jeho <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder> může mít hodnotu null. Pokud chcete zakázat všechny deserializace pomocí <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> bez ohledu na to <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder> vlastnost zakázat toto pravidlo a [CA2301](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md)a povolit pravidlo [CA2300](ca2300-do-not-use-insecure-deserializer-binaryformatter.md).

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

- Pokud je to možné, použijte zabezpečené serializátor, a **Nepovolit útočníkovi zadat libovolný typ k deserializaci**. Některé bezpečnější serializátory patří:
  - <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>
  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>
  - <xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType> -Nikdy nepoužívejte <xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType>. Pokud je nutné použít typ překladače, musí omezit deserializovaný typy očekávané seznamu.
  - <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
  - NewtonSoft Json.NET - TypeNameHandling.None použití. Pokud musíte použít jinou hodnotu pro TypeNameHandling, je nutné na očekávaný seznam omezit deserializovaný typy.
  - Protocol Buffers
- Ujistěte se, serializovaná data manipulovat testování. Po serializaci podepište kryptograficky serializovaná data. Před deserializace, ověřte kryptografický podpis. Musí chránit kryptografické klíče je zveřejněn a byste navrhnout pro rotace klíčů.
- Zakázání deserializovaný typů. Implementovat vlastní <xref:System.Runtime.Serialization.SerializationBinder?displayProperty=nameWithType>. Před deserializace s <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, nastavte <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder> vlastnost instance vašeho vlastního <xref:System.Runtime.Serialization.SerializationBinder>. V přepsané <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> metodu, pokud neočekávaný typ poté vyvolají výjimku.
  - Ujistěte se, že všechny cesty kódu <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder> sadu vlastností.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

- Je bezpečné potlačit upozornění tohoto pravidla, pokud víte, že vstup je důvěryhodný. Vezměte v úvahu, že může v průběhu času měnit toky důvěryhodnosti hranice a data vaší aplikace.
- Je bezpečné pro potlačení tohoto upozornění, pokud jste provedli jednu z výše uvedených opatření.

## <a name="pseudo-code-examples"></a>Příklady pseudo kódu

### <a name="violation"></a>Porušení

```csharp
using System;
using System.IO;
using System.Runtime.Serialization.Formatters.Binary;

[Serializable]
public class BookRecord
{
    public string Title { get; set; }
    public string Author { get; set; }
    public int PageCount { get; set; }
    public AisleLocation Location { get; set; }
}

[Serializable]
public class AisleLocation
{
    public char Aisle { get; set; }
    public byte Shelf { get; set; }
}

public class ExampleClass
{
    public BinaryFormatter Formatter { get; set; }

    public BookRecord DeserializeBookRecord(byte[] bytes)
    {
        using (MemoryStream ms = new MemoryStream(bytes))
        {
            return (BookRecord) this.Formatter.Deserialize(ms);
        }
    }
}
```

```vb
Imports System
Imports System.IO
Imports System.Runtime.Serialization.Formatters.Binary

<Serializable()>
Public Class BookRecord
    Public Property Title As String
    Public Property Author As String
    Public Property Location As AisleLocation
End Class

<Serializable()>
Public Class AisleLocation
    Public Property Aisle As Char
    Public Property Shelf As Byte
End Class

Public Class ExampleClass
    Public Property Formatter As BinaryFormatter

    Public Function DeserializeBookRecord(bytes As Byte()) As BookRecord
        Using ms As MemoryStream = New MemoryStream(bytes)
            Return CType(Me.Formatter.Deserialize(ms), BookRecord)
        End Using
    End Function
End Class
```

### <a name="solution"></a>Řešení
```csharp
using System;
using System.IO;
using System.Runtime.Serialization;
using System.Runtime.Serialization.Formatters.Binary;

public class BookRecordSerializationBinder : SerializationBinder
{
    public override Type BindToType(string assemblyName, string typeName)
    {
        // One way to discover expected types is through testing deserialization
        // of **valid** data and logging the types used.

        ////Console.WriteLine($"BindToType('{assemblyName}', '{typeName}')");

        if (typeName == "BookRecord" || typeName == "AisleLocation")
        {
            return null;
        }
        else
        {
            throw new ArgumentException("Unexpected type", "typeName");
        }
    }
}

[Serializable]
public class BookRecord
{
    public string Title { get; set; }
    public string Author { get; set; }
    public int PageCount { get; set; }
    public AisleLocation Location { get; set; }
}

[Serializable]
public class AisleLocation
{
    public char Aisle { get; set; }
    public byte Shelf { get; set; }
}

public class ExampleClass
{
    public BookRecord DeserializeBookRecord(byte[] bytes)
    {
        BinaryFormatter formatter = new BinaryFormatter();
        formatter.Binder = new BookRecordSerializationBinder();
        using (MemoryStream ms = new MemoryStream(bytes))
        {
            return (BookRecord) formatter.Deserialize(ms);
        }
    }
}
```

```vb
Imports System
Imports System.IO
Imports System.Runtime.Serialization
Imports System.Runtime.Serialization.Formatters.Binary

Public Class BookRecordSerializationBinder
    Inherits SerializationBinder

    Public Overrides Function BindToType(assemblyName As String, typeName As String) As Type
        ' One way to discover expected types is through testing deserialization
        ' of **valid** data and logging the types used.

        'Console.WriteLine($"BindToType('{assemblyName}', '{typeName}')")

        If typeName = "BinaryFormatterVB.BookRecord" Or typeName = "BinaryFormatterVB.AisleLocation" Then
            Return Nothing
        Else
            Throw New ArgumentException("Unexpected type", "typeName")
        End If
    End Function
End Class

<Serializable()>
Public Class BookRecord
    Public Property Title As String
    Public Property Author As String
    Public Property Location As AisleLocation
End Class

<Serializable()>
Public Class AisleLocation
    Public Property Aisle As Char
    Public Property Shelf As Byte
End Class

Public Class ExampleClass
    Public Function DeserializeBookRecord(bytes As Byte()) As BookRecord
        Dim formatter As BinaryFormatter = New BinaryFormatter()
        formatter.Binder = New BookRecordSerializationBinder()
        Using ms As MemoryStream = New MemoryStream(bytes)
            Return CType(formatter.Deserialize(ms), BookRecord)
        End Using
    End Function
End Class
```

## <a name="related-rules"></a>Související pravidla

[CA2300: Nepoužívejte nezabezpečené deserializátor BinaryFormatter](ca2300-do-not-use-insecure-deserializer-binaryformatter.md)

[CA2301: Nevolejte BinaryFormatter.Deserialize bez první nastavení BinaryFormatter.Binder](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md)