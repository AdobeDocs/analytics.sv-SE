---
description: Du kan skilja länkar åt genom att anpassa länk-ID med variabeln s_objectID, genom att anpassa regionen och genom att anpassa modulen AppMeasurement ActivityMap.
title: Differentiera länkar som refererar till samma länk-ID och region
uuid: f2da0cda-a33b-4a12-8d99-1f58386d6d30
feature: Activity Map
role: User, Admin
exl-id: 43fe4eb9-08fe-4e20-bc02-3f712c3dec1d
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 6%

---

# Differentiera länkar som refererar till samma länk-ID och region

Du kan differentiera länkar genom att anpassa länk-ID med variabeln s_objectID, genom att anpassa regionen och genom att anpassa modulen AppMeasurement ActivityMap.

Låt oss säga att du har flera&quot;Köp&quot;-länkar som identifieras av Activity Map under samma Link ID och Region:

<table id="table_3020E2C0175D455C84E794CF51BE5A93">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Kodexempel </th>
   <th colname="col2" class="entry"> Länk-ID </th>
   <th colname="col3" class="entry"> Län </th>
  </tr>
 </thead>
  <tbody>
  <tr>
   <td colname="col1">
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td>
   <td colname="col2">
     <br/>
     <br/>
    Köp<br/>
     <br/>
     <br/>
    Köp<br/>
     <br/>
     <br/>
    Köp<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    rekommendationspanel<br/>
     <br/>
     <br/>
    rekommendationspanel<br/>
     <br/>
     <br/>
    rekommendationspanel<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

Hur kan du anpassa din webbsida och taggning för att särskilja länkarnas värden? Du har tre alternativ: Du kan anpassa länk-ID:t, anpassa regionen eller anpassa filen AppMeasurement ActivityMap Module.

## Anpassa länk-ID med s_objectID {#section_01B0D463397B4837B2D46F087A6E5937}

Genom att skapa ett unikt objekt-ID, `s_objectID`, för en länk eller länkplats på en sida kan du antingen förbättra spårningen av Activity Map eller använda Activity Map för att rapportera en länktyp eller plats, i stället för länkens URL. Klicka [här](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html) om du vill ha mer information om variabeln `s_objectID`.

>[!IMPORTANT]
>
>Observera att ett avslutande semikolon (`;`) krävs när du använder `s_objectID` i Activity Map.
<table id="table_9439A5F320304E439A19842CF3EBA456">
 <thead>
  <tr>
   <th colname="col02" class="entry"> Kodexempel </th>
   <th colname="col2" class="entry"> Länk-ID </th>
   <th colname="col3" class="entry"> Län </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col02">
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product1';"&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt; </code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product2';"&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt; </code><br/>
    <code>&nbsp;&lt;div&gt; </code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product3';"&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td> 
   <td colname="col2">
     <br/>
     <br/>
    Produkt1<br/>
     <br/>
     <br/>
    Produkt2<br/>
     <br/>
     <br/>
    Produkt3<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    rekommendationspanel<br/>
     <br/>
     <br/>
    rekommendationspanel<br/>
     <br/>
     <br/>
    rekommendationspanel<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

## Anpassa regionen {#section_6B1EF302573B445DBAF44176D0A12DB9}

Du kan anpassa regionen genom att se till att varje köplänk har en egen region definierad. Om du vill göra det lägger du till en `"id"`-parameter i en av de överordnade taggarna för varje Buy-ankartagg.

>[!NOTE]
>Du är inte strikt begränsad till parametern `"id"` som en regionidentifierare. Du kan också ange en egen identifierare med JavaScript-variabeln `"s.ActivityMap.regionIDAttribute"`.
>
>
><table id="table_250DB52A869C466B942517BABA1C287B">
 <thead>
  <tr>
   <th colname="col02" class="entry"> Kodexempel </th>
   <th colname="col2" class="entry"> Länk-ID </th>
   <th colname="col3" class="entry"> Län </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col02">
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;a"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;b"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;c"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td> 
   <td colname="col2">
     <br/>
     <br/>
    Köp<br/>
     <br/>
     <br/>
    Köp<br/>
     <br/>
     <br/>
    Köp<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    region a<br/>
     <br/>
     <br/>
    region b<br/>
     <br/>
     <br/>
    region c<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

## Anpassa filen AppMeasurement ActivityMap Module {#section_B933BB9F944E4D5389002908A5A881F8}

>[!CAUTION]
Kontrollera att du testar den ändrade koden så att den fungerar som den ska. Adobe ansvarar inte för hur den ändrade koden fungerar.

Här är några exempel på **generiska** länk-/regionfunktioner som du kan inkludera (i ändrad form) i filen AppMeasurement.js.

```
s.ActivityMap.link = function(ele, linkName) {
  if (linkName) {
    return linkName;
  }
  if (ele) {
    if (ele.tagName == 'A' && ele.href) {
      return ele.href;
    }
  }
}
```

`linkName` skickas under anrop till `s.tl()`.

```
s.ActivityMap.region = function(ele) {
  var className,
  classNames = {
    'header': 1,
    'navbar': 1,
    'left-content': 1,
    'main-content': 1,
    'footer': 1,
  }; 
  while ((ele && (ele = ele.parentNode))) {
    if ((className=ele.className) && classNames[className]) {
      return className;
    }
  }
  return "BODY";
}
```
