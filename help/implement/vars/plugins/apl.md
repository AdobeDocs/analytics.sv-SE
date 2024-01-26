---
title: apl (appendToList)
description: Lägg till värden i variabler som stöder flera värden.
feature: Variables
exl-id: 08ca43f4-f2cc-43fb-a8eb-7c9dd237dfba
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 0%

---

# Adobe plug-in: apl (appendToList)

{{plug-in}}

The `apl` Med plugin-programmet kan du lägga till nya värden i listavgränsade variabler, som [`events`](../page-vars/events/events-overview.md), [`linkTrackVars`](../config-vars/linktrackvars.md), [`list`](../page-vars/list.md)och andra.

* Om värdet som du vill lägga till inte finns i variabeln läggs värdet till i slutet av strängen.
* Om värdet som du vill lägga till redan finns i variabeln ändras inte värdet av det här plugin-programmet. Med den här funktionen kan implementeringen undvika dubblettvärden.
* Om variabeln som du vill lägga till i är tom ställs variabeln in på det nya värdet av plugin-programmet.

Adobe rekommenderar att du använder det här plugin-programmet om du vill lägga till nya värden till befintliga variabler som innehåller en sträng med avgränsade värden. Denna plugin behövs inte om du föredrar att sammanfoga strängar för variabler som innehåller avgränsade värden.

## Installera plugin-programmet med Web SDK- eller Web SDK-tillägget

Det här plugin-programmet stöds ännu inte för användning i Web SDK.

## Installera plugin-programmet med Adobe Analytics-tillägget

Adobe har ett tillägg som gör att du kan använda de vanligaste plugin-programmen med Adobe Analytics.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Extensions] klickar du på [!UICONTROL Catalog] knapp
1. Installera och publicera [!UICONTROL Common Analytics Plugins] extension
1. Om du inte redan har det skapar du en regel med namnet&quot;Initiera plugin-program&quot; med följande konfiguration:
   * Villkor: Inget
   * Händelse: Kärna - Bibliotek inläst (sidan ovanpå)
1. Lägg till en åtgärd i ovanstående regel med följande konfiguration:
   * Tillägg: Plugin-program för gemensam analys
   * Åtgärdstyp: Initiera APL (Bifoga till lista)
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med en anpassad kodredigerare

Om du inte vill använda tillägget för Common Analytics-plugin-program kan du använda den anpassade kodredigeraren.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på önskad egenskap.
1. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** under Adobe Analytics-tillägget.
1. Expandera [!UICONTROL Configure tracking using custom code] dragspelspanel, som visar [!UICONTROL Open Editor] -knappen.
1. Öppna den anpassade kodredigeraren och klistra in den plugin-kod som finns nedan i redigeringsfönstret.
1. Spara och publicera ändringarna i Analytics-tillägget.

## Installera plugin-programmet med AppMeasurementet

Kopiera och klistra in följande AppMeasurement var som helst i analysfilen efter att Analytics-spårningsobjektet har initierats (med [`s_gi`](../functions/s-gi.md)). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: apl (appendToList) v4.0 */
function apl(lv,va,d1,d2,cc){var b=lv,d=va,e=d1,c=d2,g=cc;if("-v"===b)return{plugin:"apl",version:"4.0"};var h=function(){if("undefined"!==typeof window.s_c_il)for(var k=0,b;k<window.s_c_il.length;k++)if(b=window.s_c_il[k],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof h&&(h.contextData.apl="4.0");window.inList=window.inList||function(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1};if(!b||"string"===typeof b){if("string"!==typeof d||""===d)return b;e=e||",";c=c||e;1==c&&(c=e,g||(g=1));2==c&&1!=g&&(c=e);d=d.split(",");h=d.length;for(var f=0;f<h;f++)window.inList(b,d[f],e,g)||(b=b?b+c+d[f]:d[f])}return b};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

The `apl` funktionen använder följande argument:

* **`lv`** (required, string): Variabeln som innehåller en avgränsad lista med objekt som ett nytt värde ska läggas till i
* **`vta`** (required, string): En kommaavgränsad lista över nya värden som ska läggas till i `lv` argumentets värde.
* **`d1`** (valfri, sträng): Den avgränsare som används för att separera de enskilda värden som redan finns i `lv` argument.  Standardvärdet är ett komma (`,`) när den inte är inställd.
* **`d2`** (valfri, sträng): Utdataavgränsaren. Standardvärdet är samma som `d1` när den inte är inställd.
* **`cc`** (valfritt, booleskt): En flagga som anger om en skiftlägeskänslig kontroll används. If `true`, är dubbelkontrollen skiftlägeskänslig. If `false` Om du inte anger det är dubblettkontrollen inte skiftlägeskänslig. Standardvärdet är `false`.

The `apl` funktionen returnerar värdet för `lv` argument plus icke-duplicerade värden i `vta` argument.

## Exempel

```js
// Set the events variable to "event22,event24,event23".
s.events = "event22,event24";
s.events = apl(s.events,"event23");

// The events variable remains unchanged because the apl function does not add duplicate values
s.events = "event22,event23";
s.events = apl(s.events,"event23");

// Set the events variable to "event23" if the events variable is blank
s.events = "";
s.events = apl(s.events,"event23");

// Append a value to eVar5. The value of prop4 remains unchanged.
// The value of eVar5 is "hello|people|today".
s.prop4 = "hello|people";
s.eVar5 = apl(s.prop4, "today", "|");

// Sets prop4 to "hello|people,today". Be mindful of correct delimiters!
s.prop4 = "hello|people";
s.prop4 = apl(s.prop4, "today");

// Sets the events variable to "event22,event23,EVentT23". Be mindful of capitalization when using the cc argument!
s.events = "event22,event23";
s.events = apl(s.events,"EVenT23", ",", ",", true);

// Sets the events variable to "event22,event23,event24,event25".
s.events = "event22,event23";
s.events = apl(s.events, "event23,event24,event25");

// Sets linkTrackVars to "events,eVar1,campaign".
// The last three arguments at the end of this apl call are not necessary because they match the default argument values.
s.linkTrackVars = "events,eVar1";
s.linkTrackVars = apl(s.linkTrackVars, "campaign", ",", ",", false);

// This apl call does not do anything because the code does not assign the returned value to a variable.
s.events = "event22,event24";
apl(s.events, "event23");

// Sets the list2 variable to "apple-APPLE-Apple".
// Since the two delimiter arguments are different, the value passed in is delimited by "|", then joined together by "-".
s.list2 = "apple|APPLE";
s.list2 = apl(s.list2, "Apple", "|", "-", true);

// Sets the list3 variable to "value1,value1,value1" (unchanged).
// Only new values are deduplicated. Existing duplicate values remain.
s.list3 = "value1,value1,value1";
s.list3 = apl(s.list3,"value1");
```

## Tidigare versioner

### 4.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 3.2 (25 september 2019)

* Korrigerade kompatibilitetsproblem med `apl` anrop som använde äldre versioner av plugin-programmet
* Konsolvarningar har tagits bort för att minska storleken
* Tillagd `inList 2.1`

### 3.1 (22 april 2018)

* `d2` är nu standardvärdet för `d1` argument när de inte anges

### 3.0 (16 april 2018)

* Fullständig omanalys/omskrivning av plugin-program
* Avancerad felkontroll har lagts till
* The `vta` argument tar nu emot flera värden samtidigt
* Lagt till `d2` argument för att formatera returvärdet
* Ändrad `cc` argument till ett booleskt

### 2.5 (18 februari 2016)

* Använder nu `inList` funktion för jämförelsebearbetning

### 2.0 (26 januari 2016)

* `d` (Delimiter)-argument är nu valfritt (som standard ett komma)
* `u` (Flagga för skiftlägeskänslighet) är nu valfritt (standardvärdet är skiftlägeskänsligt)
* Oavsett `u` (Flagga för skiftlägeskänslighet) lägger plugin-programmet inte längre till ett värde i en lista om värdet redan finns i listan
