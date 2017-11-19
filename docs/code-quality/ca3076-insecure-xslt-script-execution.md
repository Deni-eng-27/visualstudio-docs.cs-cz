---
title: "CA3076: Spuštění skriptu nezabezpečené XSLT | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53cb7a46-c564-488f-bc51-0e210a7853c9
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5bf7da81e41a00bd0d673e3522f944dc17a549c9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca3076-insecure-xslt-script-execution"></a>CA3076: Spuštění skriptu nezabezpečené XSLT
|||  
|-|-|  
|TypeName|InsecureXSLTScriptExecution|  
|CheckId|CA3076|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Pokud spustíte [předlohy se styly transformace XSLT (Extensible Language)](https://support.microsoft.com/en-us/kb/313997) v aplikacích .NET nezabezpečeným, procesor může [vyřešit nedůvěryhodné odkazy na URI](http://msdn.microsoft.com/en-us/ba3e4d4f-1ee7-4226-a51a-78a1f1b5bd8a) , může odhalit citlivá informace o útočníci, což Denial of Service a webů útoky.  
  
## <a name="rule-description"></a>Popis pravidla  
 [XSLT](http://msdn.microsoft.com/en-us/6377ce5f-3c45-42a6-b7a9-ec8da588b60c) je standard World Wide Web Consortium (W3C) transformace dat XML. XSLT se obvykle používá k zápisu šablony stylů transformace dat XML do jiných formátů, jako je například HTML, pevná délka textu, text oddělený čárkami nebo do jiného formátu XML. I když zakázané ve výchozím nastavení, můžete ji povolit pro váš projekt.  
  
 Aby se zajistilo, nejsou vystavení prostor pro útoky, toto pravidlo aktivuje vždy, když XslCompiledTransform. <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> obdrží nezabezpečené kombinace instancí <xref:System.Xml.Xsl.XsltSettings> a <xref:System.Xml.XmlResolver>, což umožňuje zpracování škodlivým skriptem.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
  
-   Nahraďte nezabezpečené argument XsltSettings XsltSettings. <xref:System.Xml.Xsl.XsltSettings.Default%2A> nebo instanci, která se vypne provádění dokumentu funkce a skript.  
  
-   Nahraďte <xref:System.Xml.XmlResolver> argument s hodnotou null nebo <xref:System.Xml.XmlSecureResolver> instance.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Pokud si nejste jisti, že vstup se označuje jako z důvěryhodného zdroje, není potlačit pravidlo z toto upozornění.  
  
## <a name="pseudo-code-examples"></a>Příklady pseudo kódu  
  
### <a name="violation"></a>Porušení  
  
```csharp  
using System.Xml;  
using System.Xml.Xsl;  
  
namespace TestNamespace   
{   
    class TestClass   
    {  
         void TestMethod()   
        {    
             XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();   
             var settings = XsltSettings.TrustedXslt;   
             var resolver = new XmlUrlResolver();   
             xslCompiledTransform.Load("testStylesheet", settings, resolver); // warn   
        }  
    }   
}   
```  
  
### <a name="solution"></a>Řešení  
  
```csharp  
using System.Xml;   
using System.Xml.Xsl;   
  
namespace TestNamespace   
{   
    class TestClass   
    {   
        void TestMethod()   
        {   
            XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();   
            var settings = XsltSettings.Default;   
            var resolver = new XmlUrlResolver();   
            xslCompiledTransform.Load("testStylesheet", settings, resolver);   
        }   
    }   
}  
```  
  
### <a name="violation"></a>Porušení  
  
```csharp  
using System.Xml;   
using System.Xml.Xsl;   
  
namespace TestNamespace   
{   
    class TestClass   
    {   
        private static void TestMethod(XsltSettings settings)   
        {   
            try   
            {   
                XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();   
                var resolver = new XmlUrlResolver();   
                xslCompiledTransform.Load("testStylesheet", settings, resolver); // warn   
            }   
            catch { throw; }   
            finally { }   
        }   
    }   
}  
```  
  
### <a name="solution"></a>Řešení  
  
```csharp  
using System.Xml;   
using System.Xml.Xsl;   
  
namespace TestNamespace   
{   
    class TestClass   
    {   
        private static void TestMethod(XsltSettings settings)   
        {   
            try   
            {   
                XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();   
                settings.EnableDocumentFunction = false;   
                settings.EnableScript = false;   
                var resolver = new XmlUrlResolver();   
                xslCompiledTransform.Load("testStylesheet", settings, resolver);   
            }   
            catch { throw; }   
            finally { }   
        }   
    }   
}  
```