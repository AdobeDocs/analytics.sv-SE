---
title: apl (appendToList)
description: Lägg till värden i variabler som har stöd för flera värden.
exl-id: 08ca43f4-f2cc-43fb-a8eb-7c9dd237dfba
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '1028'
ht-degree: 0%

---

# Adobe plug-in: apl (appendToList)

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med `apl`-plugin-programmet kan du lägga till nya värden i listavgränsade variabler, till exempel [`events`](../page-vars/events/events-overview.md), [`linkTrackVars`](../config-vars/linktrackvars.md), [`list`](../page-vars/list.md) och andra.

* Om värdet som du vill lägga till inte finns i variabeln läggs värdet till i slutet av strängen.
* Om värdet som du vill lägga till redan finns i variabeln ändras inte värdet av det här plugin-programmet. Med den här funktionen kan implementeringen undvika dubblettvärden.
* Om variabeln som du vill lägga till i är tom ställs variabeln in på det nya värdet av plugin-programmet.

Adobe rekommenderar att du använder det här plugin-programmet om du vill lägga till nya värden till befintliga variabler som innehåller en sträng med avgränsade värden. Denna plugin behövs inte om du föredrar att sammanfoga strängar för variabler som innehåller avgränsade värden.

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
   * Åtgärdstyp: Initiera APL (Bifoga till lista)
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
/* Adobe Consulting Plugin: apl (appendToList) v4.0 */
function apl(lv,va,d1,d2,cc){var b=lv,d=va,e=d1,c=d2,g=cc;if("-v"===b)return{plugin:"apl",version:"4.0"};var h=function(){if("undefined"!==typeof window.s_c_il)for(var k=0,b;k<window.s_c_il.length;k++)if(b=window.s_c_il[k],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof h&&(h.contextData.apl="4.0");window.inList=window.inList||function(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1};if(!b||"string"===typeof b){if("string"!==typeof d||""===d)return b;e=e||",";c=c||e;1==c&&(c=e,g||(g=1));2==c&&1!=g&&(c=e);d=d.split(",");h=d.length;for(var f=0;f<h;f++)window.inList(b,d[f],e,g)||(b=b?b+c+d[f]:d[f])}return b};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Metoden `apl` använder följande argument:

* **`lv`** (required, string): Variabeln som innehåller en avgränsad lista med objekt som ett nytt värde ska läggas till i
* **`vta`** (required, string): En kommaavgränsad lista över nya värden som ska läggas till i  `lv` argumentets värde.
* **`d1`** (valfri, sträng): Avgränsaren som används för att separera de enskilda värden som redan finns i  `lv` argumentet.  Standardvärdet är ett kommatecken (`,`) när inget anges.
* **`d2`** (valfri, sträng): Utdataavgränsaren. Standardvärdet är samma som `d1` om det inte anges.
* **`cc`** (valfritt, boolesk): En flagga som anger om en skiftlägeskänslig kontroll används. Om `true` är dupliceringskontrollen skiftlägeskänslig. Om `false` eller inte anges är dubblettkontrollen inte skiftlägeskänslig. Standardvärdet är `false`.

Metoden `apl` returnerar värdet för argumentet `lv` plus alla icke-dubblettvärden i argumentet `vta`.

## Exempelanrop

### Exempel 1

Om..

```js
s.events = "event22,event24";
```

...och följande kod körs...

```js
s.events = s.apl(s.events, "event23");
```

... det slutliga värdet för s.events blir:

```js
s.events = "event22,event24,event23";
```

### Exempel 2

Om..

```js
s.events = "event22,event23";
```

...och följande kod körs...

```js
s.events = s.apl(s.events, "event23");
```

... det slutliga värdet för s.events kommer fortfarande att vara:

```js
s.events = "event22,event23";
```

I det här exemplet har anropet apl inte gjort några ändringar i s.events eftersom s.events redan innehöll &quot;event23&quot;

### Exempel 2

Om..

```js
s.events = ""; //blank value
```

...och följande kod körs...

```js
s.events = s.apl(s.events, "event23");
```

... det slutliga värdet för s.events blir..

```js
s.events = "event23";
```

### Exempel 4

Om..

```js
s.prop4 = "hello|people";
```

...och följande kod körs...

```js
s.eVar5 = s.apl(s.prop4, "today", "|");
```

... det slutliga värdet för s.prop4 kommer fortfarande att vara ...

```js
s.prop4 = "hello|people";
```

...men slutvärdet för s.eVar5 kommer att vara

```js
s.eVar5 = "hello|people|today";
```

Tänk på att plugin-programmet bara returnerar ett värde. det behöver inte nödvändigtvis &quot;återställa&quot; variabeln som skickas via lv-argumentet.

### Exempel 5

Om..

```js
s.prop4 = "hello|people";
```

...och följande kod körs...

```js
s.prop4 = s.apl(s.prop4, "today");
```

... det slutliga värdet för s.prop4 blir..

```js
s.prop4 = "hello|people,today";
```

Se till att avgränsaren är konsekvent mellan vad som finns i lv-argumentets värde och vad som finns i d1/d2-argumenten

### Exempel 6

Om..

```js
s.events = "event22,event23";
```

...och följande kod körs...

```js
s.events = s.apl(s.events,"EVenT23", ",", ",", true);
```

... det slutliga värdet för s.events blir:

```js
s.events = "event22,event23,EVentT23";
```

Det här exemplet är inte praktiskt, men det visar att du måste använda försiktighet när du använder den skiftlägeskänsliga flaggan.

### Exempel 7

Om..

```js
s.events = "event22,event23";
```

...och följande kod körs...

```js
s.events = s.apl(s.events, "event23,event24,event25");
```

... det slutliga värdet för s.events blir:

```js
s.events = "event22,event23,event24,event25");
```

Plugin-programmet lägger inte till &quot;event23&quot; till s.events eftersom det redan finns i s.events.  Men den lägger till både event24 och event25 till s.events eftersom ingen av dem fanns tidigare i s.events.

### Exempel 8

Om..

```js
s.linkTrackVars = "events,eVar1";
```

...och följande kod körs...

```js
s.linkTrackVars = s.apl(s.linkTrackVars, "campaign", ",", ",", false);
```

... det slutliga värdet för s.linkTrackVars blir:

```js
s.linkTrackVars = "events,eVar1,campaign";
```

De tre sista argumenten (dvs. &quot;,&quot;, &quot;,&quot;, false) i slutet av det här anropet är inte nödvändiga, men skadar inte något genom att anges eftersom de matchar standardargumentvärdena.

### Exempel 9

Om..

```js
s.events = "event22,event24";
```

...och följande kod körs...

```js
s.apl(s.events, "event23");
```

... det slutliga värdet för s.events kommer fortfarande att vara:

```js
s.events = "event22,event24";
```

Om du kör plugin-programmet separat (utan att tilldela returvärdet till en variabel) &quot;återställs&quot; inte variabeln som skickas via lv-argumentet.

### Exempel 10

Om..

```js
s.list2 = "casesensitivevalue|casesensitiveValue"
```

...och följande kod körs...

```js
s.list2 = s.apl(s.list2, "CasESensiTiveValuE", "|", "-", true);
```

... det slutliga värdet för s.list2 blir:

```js
s.list2 = "casesensitivevalue-casesensitiveValue-CasESensiTiveValuE"
```

Eftersom de två avgränsarargumenten är olika avgränsas det värde som skickas av det första avgränsarargumentet (&quot;|&quot;) och sedan sammanfogas med det andra avgränsarargumentet (&quot;-&quot;)

## Versionshistorik

### 4.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 3.2 (25 september 2019)

* Korrigerade kompatibilitetsproblem med `apl`-anrop som använde äldre versioner av plugin-programmet
* Konsolvarningar har tagits bort för att minska storleken
* `inList 2.1` har lagts till

### 3.1 (22 april 2018)

* `d2` argument får nu som standard värdet för  `d1` argumentet när det inte anges

### 3.0 (16 april 2018)

* Fullständig omanalys/omskrivning av plugin-program
* Avancerad felkontroll har lagts till
* Argumentet `vta` tar nu emot flera värden samtidigt
* Lade till argumentet `d2` för att formatera returvärdet
* Ändrade `cc`-argumentet till ett booleskt värde

### 2.5 (18 februari 2016)

* Använder nu metoden `inList` för jämförelsebearbetning

### 2.0 (26 januari 2016)

* `d` (Delimiter)-argument är nu valfritt (som standard ett komma)
* `u` (Flagga för skiftlägeskänslighet) är nu valfritt (standardvärdet är skiftlägeskänsligt)
* Oavsett argumentet `u` (flagga för skiftlägeskänslighet) lägger plugin-programmet inte längre till ett värde i en lista om värdet redan finns i listan
