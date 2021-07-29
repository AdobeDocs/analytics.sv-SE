---
title: formatTime
description: Konvertera ett antal sekunder till motsvarande antal minuter, timmar osv.
exl-id: 4b98e7fe-f05b-4346-b284-697268adc1a2
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 0%

---

# Adobe plug-in: formatTime

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med plugin-programmet `formatTime` kan du ta valfritt antal sekunder och presentera dem i ett paketerat format, avrundat till önskat referensvärde. Adobe rekommenderar att du använder det här plugin-programmet om du vill hämta ett tidsvärde i sekunder och konvertera det till ett bucket-format (till exempel minuter, dagar eller veckor). Detta plugin-program behövs inte om du inte vill bucket med sekundbaserade värden i ett tidslinjeformat.

## Installera plugin-programmet med hjälp av taggar i Adobe Experience Platform

Adobe har ett tillägg som gör att du kan använda de vanligaste plugin-programmen.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Catalog]
1. Installera och publicera tillägget [!UICONTROL Common Analytics Plugins]
1. Om du inte redan har det skapar du en regel med namnet&quot;Initiera plugin-program&quot; med följande konfiguration:
   * Villkor: Ingen
   * Händelse: Kärna - Bibliotek inläst (sidan ovanpå)
1. Lägg till en åtgärd i ovanstående regel med följande konfiguration:
   * Tillägg: Plugin-program för vanlig analys
   * Åtgärdstyp: Initiera formatTime
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med en anpassad kodredigerare

Om du inte vill använda plugin-programtillägget kan du använda den anpassade kodredigeraren.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics-tillägget.
1. Expandera dragspelet [!UICONTROL Configure tracking using custom code], som visar knappen [!UICONTROL Open Editor].
1. Öppna den anpassade kodredigeraren och klistra in den plugin-kod som finns nedan i redigeringsfönstret.
1. Spara och publicera ändringarna i Analytics-tillägget.

## Installera plugin-programmet med AppMeasurement

Kopiera och klistra in följande kod var som helst i AppMeasurement-filen när Analytics-spårningsobjektet har instansierats (med [`s_gi`](../functions/s-gi.md)). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: formatTime v2.0 */
function formatTime(ns,tf,bml){var f=ns,d=tf,e=bml;function h(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(arguments&&"-v"===arguments[0])return{plugin:"formatTime",version:"2.0"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var b=0,c;b<window.s_c_il.length;b++)if(c=window.s_c_il[b],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.formatTime="2.0");if(!("undefined"===typeof f||isNaN(f)||0>Number(f))){b="";if("string"===typeof d&&"d"===d||("string"!==typeof d||!h("h,m,s",d))&&86400<=f){var c=86400;var g="days";b=isNaN(e)?1:c/(e*c)}else"string"===typeof d&&"h"===d||("string"!==typeof d||!h("m,s",d))&&3600<=f?(c=3600,g="hours",b=isNaN(e)?4:c/(e*c)):"string"===typeof d&&"m"===d||("string"!==typeof d||!h("s",d))&&60<=f?(c=60,g="minutes",b=isNaN(e)?2:c/(e*c)):(c=1,g="seconds",b=isNaN(e)?.2:c/e);b=Math.round(f*b/c)/b+" "+g;0===b.indexOf("1 ")&&(b=b.substring(0,b.length-1));return b}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Metoden `formatTime` använder följande argument:

* **`ns`** (obligatoriskt, heltal): Antal sekunder att konvertera eller formatera
* **`tf`** (valfri, sträng): Den typ av format som ska returnera sekunder in; standard är sekunder
   * Ange `"d"` om du vill ha tiden i dagar (avrundat till närmaste 1/4-dagars test som standard)
   * Ange `"h"` om du vill ha tiden i timmar (avrundat till närmaste 1/4-timmars riktmärke som standard)
   * Ange `"m"` om du vill att tiden ska vara i minuter (avrundat till närmaste 1/2-minuters test som standard)
   * Ange `"s"` om du vill ha tiden i sekunder (avrundat till närmaste 5 sekunder som standard)
* **`bml`** (valfritt, antal): Längden på avrundningsriktmärkena. Standardvärdet är de referensvärden som anges i `tf`-argumentet

Metoden returnerar antalet sekunder som formaterats med den enhet som du anger i `tf`-argumentet. Om `tf`-argumentet inte har angetts:

* Allt som är mindre än en minut avrundas till närmaste 5-sekunders test
* Allt mellan en minut och en timme avrundas till närmaste 1/2-minuters test
* Allt som är mellan en timme och en dag avrundas till närmaste kvart-timmars riktmärke
* Allt som är större än en dag avrundas till närmaste dagtest

## Exempel

### Exempel 1

Följande kod...

```js
s.eVar1 = s.formatTime(38242);
```

...ställs in s.eVar1 till &quot;10,5 timmar&quot;

Argumentet som skickades - 38 242 sekunder - är lika med 10 timmar, 37 minuter och 22 sekunder.  Eftersom tf-argumentet inte anges i det här anropet och antalet sekunder som skickas är mellan en timme och en dag, kommer plugin-programmet att returnera antalet sekunder som konverterats till närmaste kvarts-test.

### Exempel 2

Följande kod...

```js
s.eVar1 = s.formatTime(38250);
```

...ställs in s.eVar1 till &quot;10,75 timmar&quot;
Argumentet som skickades - 38 250 sekunder - är lika med 10 timmar, 37 minuter och 30 sekunder.  Genom att avrunda antalet sekunder som skickas in till det närmaste kvart-timmars-riktvärdet i detta fall kommer det slutliga värdet att anges till 10,75 timmar

### Exempel 2

Följande kod...

```js
s.eVar1 = s.formatTime(38242, "m");
```

...ställs in s.eVar1 till &quot;637.5 minuter&quot;

I det här fallet tvingar argumentet &quot;m&quot; plugin-programmet att konvertera sekunder till närmaste halvminuters test

### Exempel 4

Följande kod...

```js
s.eVar1 = s.formatTime(38242, "m", 20);
```

...anges s.eVar1 till &quot;640 minuter&quot;

Värdet för tf-argumentet (&quot;m&quot;) tvingar plugin-programmet att konvertera sekunder till minuter, men värdet för bml-argumentet (20) tvingar också plugin-programmet att avrunda minutkonverteringen till närmaste 20-minutersprenumeration.

### Exempel 5

Följande kod...

```js
s.eVar1 = s.formatTime(125, "s", 2);
```

...ställs in s.eVar1 till &quot;126 sekunder&quot;, vilket är det närmsta 2-sekundersvärdet till 125 sekunder

### Exempel 6

Följande kod...

```js
s.eVar1 = s.formatTime(125, "m", 3);
```

...ställs in s.eVar1 till &quot;3 minuter&quot;, vilket är det närmaste 3-minuterstestet till 125 sekunder

### Exempel 7

Följande kod...

```js
s.eVar1 = s.formatTime(145, "m", .4);
```

...är lika med &quot;2,4 minuter&quot;, vilket är det närmsta 2/5 minuter långa riktvärdet (t.ex. .4 = 2/5) till 145 sekunder

## Versionshistorik

### 2.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 1.1 (21 maj 2018)

* Argumentet `bml` har lagts till för att ge mer flexibilitet vid avrundning

### 1.0 (15 april 2018)

* Inledande version.
