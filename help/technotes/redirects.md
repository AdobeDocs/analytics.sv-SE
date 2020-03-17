---
description: Omdirigerar pekar webbläsaren till en ny plats utan användarinteraktion. De körs antingen i webbläsaren (omdirigering på klientsidan) eller på webbservern (omdirigering på serversidan).
keywords: Analytics Implementation
subtopic: Redirects
title: Omdirigering och alias
topic: Developer and implementation
uuid: 11f9ad7a-5c45-410f-86dd-b7d2cec2aae3
translation-type: tm+mt
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12

---


# Omdirigering och alias

Omdirigerar pekar webbläsaren till en ny plats utan användarinteraktion. De körs antingen i webbläsaren (omdirigering på klientsidan) eller på webbservern (omdirigering på serversidan).

## Omdirigering och alias {#concept_F4F1D53D473947FE8554897332545763}

Omdirigerar pekar webbläsaren till en ny plats utan användarinteraktion. De körs antingen i webbläsaren (omdirigering på klientsidan) eller på webbservern (omdirigering på serversidan).

Eftersom omdirigeringar inte kräver någon användarinteraktion utförs omdirigeringar ofta utan att användaren någonsin märker det. Det enda som tyder på att en omdirigering har gjorts är webbläsarens adressfält. Adressfältet visar en URL som skiljer sig från den länk som webbläsaren ursprungligen begärde.

Även om det bara finns två typer av omdirigeringar kan de implementeras på flera olika sätt. Klientsidan kan till exempel omdirigeras eftersom webbsidan som användaren har pekat på i webbläsaren innehåller skript eller speciell HTML-kod som omdirigerar webbläsaren till en annan URL. Serverbaserade omdirigeringar kan inträffa på grund av att sidan innehåller serverskript eller på grund av att webbservern har konfigurerats för att peka användaren mot en annan URL.

## Analyser och omdirigeringar {#concept_F9132879D0CB4AC1BE7AF45E388A47F7}

[!DNL Analytics] samlar in en del data från webbläsaren och förlitar sig på vissa webbläsaregenskaper. Två av dessa egenskaper, &quot;Refererande URL&quot; (eller &quot;referent&quot;) och &quot;Aktuell URL&quot;, kan ändras av en omdirigering på serversidan. Eftersom webbläsaren är medveten om att en URL har begärts, men en annan URL har returnerats, rensas URL:en Refererande. Resultatet är att den refererande URL:en är tom och [!DNL Analytics] kan rapportera att det inte finns någon referens för sidan.

## Exempel: Bläddra utan omdirigeringar {#section_5C835A4D665A4625A23333C2C21F152D}

Tänk på följande hypotetiska scenario där användaren inte stöter på någon omdirigering:

1. Användaren pekar sin webbläsare mot `www.google.com`och skriver&quot;rabattflygbiljetter&quot; i sökfältet och klickar sedan på **[!UICONTROL Search]** knappen.
1. Webbläsaren visar sökresultaten med en länk till din webbplats [!DNL https://www.example.com/]. När sökresultaten har visats visar webbläsarens adressfält de sökord som användaren har angett i sökfältet ( `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`). Observera att söktermerna ingår i de URL-frågesträngsparametrar som följer `https://www.google.com/search?`.
1. Användaren klickar på länken till din hypotetiska webbplats [!DNL https://www.example.com/]. När användaren klickar på den här länken och länkar på [!DNL example.com] webbplatsen [!DNL Analytics] använder JavaScript för att samla in den refererande URL:en ( `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`) samt den aktuella URL:en ( `https://www.example.com/`).
1. [!DNL Analytics] rapporterar den information som samlats in under denna interaktion i olika rapporter, t.ex. [!UICONTROL Referring Domains], [!UICONTROL Search Engines]och [!DNL Search Keywords].

## Exempel: Bläddra med omdirigeringar {#section_921DDD32932847848C4A901ACEF06248}

Omdirigeringar kan göra att webbläsaren tömmer den refererande URL:en. Tänk på följande scenario:

1. Användaren pekar sin webbläsare mot `https://www.google.com`och skriver *rabattflygbiljetter* i sökfältet och klickar sedan på **[!UICONTROL Search]** .
1. I webbläsarfönstrets adressfält visas de sökord som användaren har angett i sökfältet `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`. Observera att söktermerna ingår i de URL-frågesträngsparametrar som följer `https://www.google.com/search?`. Webbläsaren visar också en sida som innehåller sökresultaten, inklusive en länk till ett av dina domännamn: [!DNL https://www.flytohawaiiforfree.com/]. Den här *huvuddomänen* är konfigurerad att dirigera om användaren till `https://www.example.com/`.
1. Användaren klickar på länken `https://www.flytohawaiiforfree.com/` och dirigeras om av servern till huvudplatsen `https://www.example.com`. När omdirigeringen görs försvinner de data som är viktiga för datainsamlingen eftersom webbläsaren rensar den refererande URL:en. [!DNL Analytics] Den ursprungliga sökinformationen som användes i [!DNL Analytics] rapporterna (till exempel [!UICONTROL Referring Domains], [!UICONTROL Search Engines], [!UICONTROL Search Keywords]) går alltså förlorad.

## Implementera omdirigeringar {#concept_5EC2EE9677A44CC5B90A38ECF28152E7}

För att kunna hämta in [!DNL Analytics] data från omdirigeringar måste fyra mindre ändringar göras i koden som skapar omdirigeringen och [!DNL AppMeasurement] för JavaScript-filen.

<!-- 

redirects_implement.xml

 -->

När du slutför följande steg behålls den information som den ursprungliga referenten (till exempel `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets` i scenariot ovan) skickar till din plats:

## Konfigurera referens åsidosätta JavaScript-kod {#section_87BB1D47D9C345C18339078824645CC4}

<!-- 

redirects_js_override.xml

 -->

Kodfragmentet nedan visar två JavaScript-variabler *`s_referrer`* och *`s_pageURL`*. Denna kod placeras på den slutliga landningssidan för omdirigeringen.

```js
<script language="JavaScript" src="//INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"></script> 
<script language="JavaScript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.campaign="" 
s.referrer="" 
s.pageURL=""
```

>[!IMPORTANT]
>
>Ange *`s.referrer`* bara en gång på sidan. Om du anger det mer än en gång med varje spårningsanrop eller med varje länkklick som spåras, kommer referenten att räknas dubbelt och relaterade dimensioner, som sökmotorer och nyckelord.

## Omdirigeringar med getQueryParam {#section_EE924E399F7A431C8FC8E8A2BEF84DEC}

Även om det [!UICONTROL getQueryParam] är ett enkelt sätt att fylla i [!DNL Analytics] variabler med frågesträngsvärden, måste det implementeras tillsammans med en tillfällig variabel så att berättigade referenser inte skrivs över när frågesträngen är tom. Det bästa sättet att använda [!UICONTROL getQueryParam] är i samband med plugin-programmet [!UICONTROL getValue] enligt följande pseudokod.

```js
// AppMeasurement 1.x 
var tempVar=s.Util.getQueryParam('origref') 
if(tempVar) 
  s.referrer=tempVar;
```

```js
// H Code 
var tempVar=s.getQueryParam('origref') 
if(tempVar) 
  s.referrer=tempVar;
```

## Ändra omdirigeringsmekanismen {#section_2FF9921E8FCA4440B6FF90F15386E548}

<!-- 

redirects_modify_mechanism.xml

 -->

Eftersom webbläsaren rensar den refererande URL:en måste du konfigurera den mekanism som hanterar omdirigeringen (till exempel webbservern, koden på serversidan, koden på klientsidan) så att den skickar den ursprungliga referentinformationen. Om du även vill spela in aliaslänkens URL måste den också skickas till den slutliga landningssidan. Använd variabeln *`s_pageURL`* för att åsidosätta den aktuella URL:en.

Eftersom det finns många sätt att implementera en omdirigering bör du kontakta din webbfunktionsgrupp eller din onlineannonseringspartner för att identifiera de specifika mekanismer som utför omdirigeringar på din webbplats.

## Hämta den ursprungliga referenten {#section_7F1A77F447CF485385B456A64B174050}

<!-- 

redirects_referrer.xml

 -->

Normalt [!DNL Analytics] hämtas den refererande URL:en från webbläsarens [!UICONTROL document.referrer] egenskap och den aktuella URL:en från [!UICONTROL document.location] egenskapen. Genom att skicka värden till *`referrer`* och *`pageURL`* variabler kan du åsidosätta standardbearbetningen. Genom att skicka ett värde till referensvariabeln, kommer du [!DNL Analytics] att ignorera referensinformationen i [!UICONTROL document.referrer] egenskapen och använda ett alternativt värde som du definierar.

Den slutliga versionen av landningssidan måste därför innehålla följande kod för att korrigera de problem som introducerades i scenariot&quot;rabatterade flygbiljetter&quot;.

```js
<script language="JavaScript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"></script> 
<script language="JavaScript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.campaign="" 
s.referrer="https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets" 
// Setting the s.pageURL variable is optional.
s.pageURL="https://www.flytohawaiiforfree.com"
```

## Verifiera referenten med Adobe Debugger {#section_B3E85941982E4E1698B271375AD669B9}

<!-- 

redirects_verify_referrer.xml

 -->

Kör ett test för att verifiera att referenten, ursprunglig URL ( *`s_server`*) och kampanjvariabler samlas in.

Dessa variabler representeras som följande parametrar i [Experience Cloud Debugger](https://marketing.adobe.com/resources/help/en_US/experience-cloud-debugger/).

<table id="table_5F3B987D4D514CA283F7B9F52EBC2301"> 
 <thead> 
  <tr> 
   <th class="entry"> </th> 
   <th class="entry"> <b>URL- eller frågesträngsvärde</b> </th> 
   <th class="entry"> <b>Värde som visas i DigitalPulse-felsökaren</b> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>Ursprunglig referens </p> </td> 
   <td> <p> <span class="filepath"> https://www.google.com/search%3F hl%3Den %26ie%3DUTF826q%3 Drabatt%2BAirlines%2Btickets </span> </p> </td> 
   <td> <p> <span class="filepath"> r=https:/ref=www.google.com/search?hl=en&amp;ie=UTF -8&amp;q=rabatt+flygbolag+biljetter </span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Sidans URL </p> </td> 
   <td> <p> <span class="filepath"> https://www.flytohawaiiforfree.com </span> </p> </td> 
   <td> <p> <span class="filepath"> g=https://www.flytohawaiiforfree.com </span> </p> <p>Det här värdet visas i DigitalPulse-felsökaren om <span class="varname"> pageURL- </span> variabeln används. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>URL för den ultimata landningssidan </p> </td> 
   <td> <p> <span class="filepath"> https://www.example.com </span> </p> </td> 
   <td> <p>Det här värdet visas INTE i DigitalPulse-felsökaren om <span class="varname"> pageURL- </span> variabeln används. </p> </td> 
  </tr> 
 </tbody> 
</table>

Texten som felsökaren visar ska motsvara följande exempel:

```
Image 
 
https://examplecom.112.2o7.net/b/ss/examplecom/1/JS-1.4/s61944015791667?[AQB] 
ndh=1 
t=4/8/2014 13:34:28 4 360 
pageName=Welcome to example.com 
r=https://ref=www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets 
cc=USD 
g=https://www.flytohawaiiforfree.com 
s=1280x1024 
c=32 
j=1.3 
v=Y 
k=Y 
bw=1029 
bh=716 
ct=lan 
hp=N 
[AQE]
```

När du har verifierat att dessa variabler [!UICONTROL Debugger] visas i Adobe är det alltid praktiskt att bekräfta att söktermerna och den ursprungliga referensdomänen (före omdirigeringen) registrerar trafik i rapporter.
