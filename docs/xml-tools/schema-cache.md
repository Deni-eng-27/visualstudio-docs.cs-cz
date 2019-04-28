---
title: Editor XML schémat mezipaměti
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 35a7fcad-f3bf-4a96-9008-4306e7276223
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 28f5a7ffe202e7e02b06e676501ab508ee1a4ab2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62955550"
---
# <a name="schema-cache"></a>Mezipaměť schémat

XML editor poskytuje nachází v mezipaměti schématu *%VSInstallDir%\xml\Schemas* adresáře. Mezipaměti schématu je pro všechny uživatele ve vašem počítači globální a obsahuje standardní schémat XML, které slouží k ověření dokumentu technologie IntelliSense a XML.

Editor souborů XML můžete také vyhledat schémata, které jsou umístěny v řešení, schémata zadané v **schémata** pole dokumentu **vlastnosti** okno a schémata identifikován `xsi:schemaLocation` a `xsi:noNamespaceSchemaLocation`atributy.

Následující tabulka popisuje schémata, které jsou nainstalovány v editoru XML.

| Název souboru | Popis |
|-| - |
| *catalog.xsd* | Schéma pro soubory katalogu schémat XML editor. Informace o katalogů schémat najdete níže. |
| *DotNetConfig.xsd* | Schéma pro soubory Web.Config "<http://schemas.microsoft.com/.NETConfiguration/v2.0>". |
| *msbuild.xsd* | Schéma pro soubory MSBuild Ujistěte se, "<http://schemas.microsoft.com/developer/msbuild/2003>". |
| *msdata.xsd* | Schéma XSD poznámky přidal <xref:System.Data.DataSet> třídy, "urn: schémata-microsoft-schemas-msdata". |
| *msxsl.xsd* | Schéma pro rozšíření bloku skriptu Microsoft XSLT, urn: schémata-microsoft-com:xslt. |
| *SnippetFormat.xsd* | Schéma pro soubory XML fragmentu kódu. Příklady najdete v tématu *%VSInstallDir%\VC#\Expansions*. |
| *Soap1.1.xsd* | Schéma pro Simple Object Access Protocol (SOAP) 1.1, http://schemas.xmlsoap.org/soap/envelope/. |
| *Soap1.2.xsd* | Schéma pro Simple Object Access Protocol 1.2. |
| *SiteMapSchema.xsd* | Schéma pro soubor XML mapy webu technologie ASP.NET, "<http://schemas.microsoft.com/AspNet/SiteMap-File-1.0>". |
| *wsdl.xsd* | Schéma pro Web Service Description Language http://schemas.xmlsoap.org/wsdl/. |
| *xenc.xsd* | Schéma pro šifrování XML http://www.w3.org/2000/09/xmldsig#. |
| *xhtml.xsd* | Schéma pro XHTML http://www.w3.org/1999/xhtml. |
| *XLINK.xsd* | Schéma pro XLink1.0, http://www.w3.org/1999/xlink. |
| *xml.xsd* | Schéma popisující XML: Space a XML: lang – atributy, http://www.w3.org/XML/1998/namespace. |
| *xmlsig.xsd* | Schéma XML – digitální podpisy, http://www.w3.org/2000/09/xmldsig#. |
| *xsdschema.xsd* | Schéma XSD, popisující http://www.w3.org/2001/XMLSchema. |
| *xslt.xsd* | Transformuje se schéma pro formát XML, http://www.w3.org/1999/XSL/Transform. |

## <a name="update-schemas-in-the-cache"></a>Aktualizovat schémata v mezipaměti

Editor načte adresář mezipaměti schématu, když balíček editoru XML je načten a sleduje změny při spuštění. Pokud schéma se přidala, se automaticky načtou do indexu v paměti známých schémat. Pokud schéma byla odebrána, se automaticky odebere z indexu v paměti. Pokud schéma aktualizovalo, se automaticky zruší platnost mezipaměti v paměti tohoto schématu.

> [!NOTE]
> Adresář mezipaměti schématu je globální k počítači, byste měli přidávat jenom zde schémata, které jsou užitečné pro všechny projekty sady Visual Studio, které mohou být vytvořeny v počítači a standardní.

XML editor také podporuje libovolný počet soubory katalogu schématu v adresáři mezipaměti schématu. Katalogů schémat může odkazovat na jiné umístění pro schémat, které chcete, aby editoru vědět o. *Catalog.xsd* soubor definuje formát pro soubor katalogu a je součástí adresáře mezipaměti schématu. *Catalog.xml* výchozí katalog je soubor a obsahuje odkazy na jiná schémata v *VSInstallDir %*. Tady je odběr vzorků *catalog.xml* souboru:

```xml
<SchemaCatalog xmlns="http://schemas.microsoft.com/xsd/catalog">
  <Schema href="%VSInstallDir%/help/schemas/Favorites.xsd" targetNamespace="urn:Favorites-Schema"/>
  <Schema href="%VSInstallDir%/help/schemas/Links.xsd" targetNamespace="urn:Links-Schema"/>
  <Schema href="%VSInstallDir%/help/schemas/MyHelp.xsd" targetNamespace="urn:VSHelp-Schema"/>
</SchemaCatalog>
```

`href` Atribut může být libovolný soubor protokolu http adresa URL nebo cesta odkazující na dané schéma. Cesta k souboru může být relativní vzhledem k dokumentu katalogu. Následující proměnné, které jsou odděleny %%, společnost editoru a rozšířit v cestě:

- VSInstallDir

- Systém

- ProgramFiles

- Programy

- CommonProgramFiles

- ApplicationData

- CommonApplicationData

- LCID

Může zahrnovat dokumentu katalogu `Catalog` element, který odkazuje na jiné katalogů. Můžete použít `Catalog` element na střed katalogu sdílí váš tým nebo společnost nebo online katalogu sdílené s obchodními partnery. `href` Atribut je soubor http adresa URL nebo cesta pro ostatní katalogů. Následující je příkladem `Catalog` element:

```xml
<Catalog href="file://c:/xcbl/xcblCatalog.xml"/>
```

Katalog můžete také řídit, jak schémata jsou spojené s dokumenty XML pomocí speciálních `Association` elementu. Tento prvek přidruží schémat, které máte žádné cílový obor názvů s konkrétní příponou, které mohou být užitečné, protože editoru XML není nutné žádné automatické přidružení schémat, které nemají `targetNamespace` atribut. V následujícím příkladu `Association` elementu přidruží schématu dotNetConfig všechny soubory, které mají příponu "konfigurace":

```xml
<Association extension="config" schema="%VSInstallDir%/xml/schemas/dotNetConfig.xsd"/>
```

## <a name="localized-schemas"></a>Lokalizované schémata

V mnoha případech *catalog.xml* soubor neobsahuje položky pro lokalizované schémata. Můžete přidat další položky *catalog.xml* souboru odkazující na lokalizované schématu adresáře.

V následujícím příkladu nový `Schema` byl vytvořen element, který používá % proměnná % LCID tak, aby odkazoval na lokalizované schéma.

```xml
<Schema href="%InstallRoot%/Common7/IDE/Policy/Schemas/%LCID%/TDLSchema.xsd"
  targetNamespace="http://www.microsoft.com/schema/EnterpriseTemplates/TDLSchema"/>
```

## <a name="change-the-location-of-the-schema-cache"></a>Změnit umístění mezipaměti schémat

Můžete přizpůsobit umístění mezipaměti schémat pomocí **různé** stránka možností. Pokud máte adresář oblíbených schémat, místo toho použít tato schémata lze nastavit editoru.

> [!NOTE]
> Tato změna ovlivní pouze aktuální uživatel Visual Studio.

### <a name="to-change-the-schema-cache-location"></a>Chcete-li změnit umístění mezipaměti schémat

1. Z **nástroje** nabídce vyberte možnost **možnosti**.

2. Rozbalte **textový Editor**, rozbalte **XML**a potom klikněte na tlačítko **různé**.

3. Klikněte na tlačítko **Procházet** tlačítko **schémata** pole.

4. Vyberte složku pro ukládání do mezipaměti schématu a klikněte na tlačítko **OK**.

### <a name="to-add-another-directory-of-common-schemas"></a>Chcete-li přidat jiného adresáře běžných schémat

1. Upravit *catalog.xml* souboru v adresáři mezipaměti schématu XML editor.

2. Přidat nový `<Catalog href="..."/>` element, který odkazuje na adresář další schémata.

3. Uložte provedené změny.

   Katalog se automaticky znovu načte.

## <a name="see-also"></a>Viz také:

- [XML editor](../xml-tools/xml-editor.md)