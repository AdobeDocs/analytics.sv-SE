---
description: Information om kraven för rapportsviten innan du använder datakällor.
subtopic: Data sources
title: Krav och överföringsgränser
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 97a7cc65-f99a-4227-94f2-6f428ebdfad3
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 1%

---

# Krav och överföringsgränser

Information om kraven för rapportsviten innan du använder datakällor.

I följande avsnitt visas begränsningar som gäller för datakällor och data som importeras till marketing reports and analytics.

* [Storleksgränser](/help/import/c-data-sources/datasrc-requirements.md#section_77B06D82CB374FFABD39F7D9A49D8E18)
* [Datum](/help/import/c-data-sources/datasrc-requirements.md#section_2B8E69BA1E0B4DEAB4E2034C2B9E16C2)
* [Allmänt](/help/import/c-data-sources/datasrc-requirements.md#section_1CD337F660484ABDB7D8CAE96FF46ACF)
* [Stöd för flera byte](/help/import/c-data-sources/datasrc-requirements.md#section_96C8D26B21184C3E839865DB6F23EA22)
* [Överför webbloggfiler](/help/import/c-data-sources/datasrc-requirements.md#section_DD736FC971FE45C89AB310BEDC1FE707)

## Storleksgränser {#section_77B06D82CB374FFABD39F7D9A49D8E18}

* Varje FTP-konto är begränsat till 50 MB av alla data för alla filer. Bearbetningen pausas om storleken överstiger 50 MB och inte återupptas förrän summan är under 50 MB.

## Datum {#section_2B8E69BA1E0B4DEAB4E2034C2B9E16C2}

* Varje kalenderdag kan du överföra data för 90 unika datum. Om du överskrider gränsen misslyckas överföringen och ett felmeddelande visas om att du överskridit gränsen för antal unika dagar.
* Endast data med aktuella eller tidigare datum kan importeras. Försök inte använda framtida datum i dina datakällsdata.
* Alla rader måste ha ett angivet datum för att rapportdiagramfunktioner ska kunna aktiveras. Om en rad inte innehåller något datum genererar datakällor ett fel och avvisar filen. Datum-/tidsformatet varierar beroende på datakälltyp:

   * **Datakällor med fullständig bearbetning**: Använd datumformatet ISO 8601 för `YYYY-MM-DDThh:mm:ss±UTC_offset` (t.ex. `2013-09-01T12:00:00-07:00`) eller Unix Time Format (antalet sekunder som gått sedan 1 januari 1970).

   * **Standarddatakällor och integreringsdatakällor**: Använd följande datumformat: `MM/DD/YYYY/HH/mm/SS` (t.ex. `01/01/2013/06/00/00`)

## Allmänt {#section_1CD337F660484ABDB7D8CAE96FF46ACF}

* När du överför en datakällfil utför datakällor en grundläggande dataverifiering för att säkerställa att filen inte innehåller formateringsfel. Om ett fel påträffas i en fil skickas ett e-postmeddelande och bearbetningen avbryts.
* Datafält får inte innehålla semikolon. Datakällor hoppar över poster som innehåller ett semikolon.
* Data från webblogg, trafik och vissa allmänna datakällgrupper är inte tillgängliga i Data warehouse eller Discover. Mer information finns i [Datatyper och kategorier](/help/import/c-data-sources/c-datasrc-types/datasrc-categories.md).
* Datakällor stöder inte serialiserade händelser.

## Stöd för flera byte {#section_96C8D26B21184C3E839865DB6F23EA22}

Datakällor har stöd för multibyte-kodning. Datakällor försöker identifiera formatet för den inkommande datakällfilen och konverterar den vid behov till ett format som stöds. I följande tabell visas vanliga teckenformat och deras supportstatus.

<table id="table_F9E685D7EEAB49A9ABAD622AE630EC21"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Teckenformat </th> 
   <th colname="col2" class="entry"> Support </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> UTF-8 </td> 
   <td colname="col2"> <p>Stöds. Rapportsviten som används med datakällor måste ha stöd för flera byte-tecken aktiverat. </p> <p>Se <a href="https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/new-report-suite/new-report-suite.html"  > Ny rapportsvit</a> i hjälpen </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-8 med byteordningsmärke (EF BB BF) </td> 
   <td colname="col2"> <p>Stöds. Det här formatet är inte standard, men många Windows-program sparas i det här formatet. </p> <p>WordPad sparar till exempel i det här formatet om du väljer "UTF-8". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ISO-8859-1 (även Latin-1 eller Windows-1252) </td> 
   <td colname="col2"> Stöds. Microsoft Excel sparar i det här formatet när du väljer en tabbavgränsad export. Rapportsviten måste ha språkversionen ISO-8859-1. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-16 Little-endian, med byteordningsmärke (FF FE) </td> 
   <td colname="col2"> Konverteras till ISO-8859-1 eller UTF-8, enligt rapportsvitens konfiguration. Microsoft Excel sparar i det här formatet när du väljer en Unicode-export. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-16 Big-endian, med byteordningsmärke (EF FF) </td> 
   <td colname="col2"> Konverteras till ISO-8859-1 eller UTF-8, enligt rapportsvitens konfiguration. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-16 utan byteordningsmarkering </td> 
   <td colname="col2"> Stöds inte. </td> 
  </tr> 
 </tbody> 
</table>

Om du skickar en UTF-8- eller ISO-8859-1-fil och rapportsviten inte har konfigurerats för att stödja den händer något av följande:

* Felet upptäcktes under konverteringen. I så fall visas ett meddelande som &quot;Hittade ett felaktigt tecken i filen vid position 18 när UTF-8 konverterades till ISO-8859-1&quot;.
* Filen bearbetas utan fel, men du ser förvrängda data i rapporten.

## Överför webbloggfiler {#section_DD736FC971FE45C89AB310BEDC1FE707}

* De mest användbara rapporterna för att visa webbloggdata är trafikrapporter, till exempel sidvyer.
* Sidnamn visas som hela URL:en, inklusive frågesträngen.
* Varje filbegäran visas som en separat sidvy, inklusive formatmallar och bildfiler.
* Om du lägger till information i URL:en kan filerna spelas in som separata sidor. Adobe registrerar till exempel följande URL:er som två separata sidor:

`/jokes/misc/snail_joke.html?userid=12345`

`/jokes/misc/snail_joke.html?userid=98765`
