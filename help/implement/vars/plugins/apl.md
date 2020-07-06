---
title: apl (appendToList)
description: Lägg till värden i variabler som har stöd för flera värden.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '1015'
ht-degree: 0%

---


# Adobe plug-in: apl (appendToList)

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med `apl` plugin-programmet kan du lägga till nya värden i listavgränsade variabler som [`events`](../page-vars/events/events-overview.md), [`linkTrackVars`](../config-vars/linktrackvars.md)[`list`](../page-vars/list.md), med flera.

* Om värdet som du vill lägga till inte finns i variabeln läggs värdet till i slutet av strängen.
* Om värdet som du vill lägga till redan finns i variabeln ändras inte värdet av det här plugin-programmet. Med den här funktionen kan implementeringen undvika dubblettvärden.
* Om variabeln som du vill lägga till i är tom ställs variabeln in på det nya värdet av plugin-programmet.

Adobe rekommenderar att du använder denna plugin om du vill lägga till nya värden till befintliga variabler som innehåller en sträng med avgränsade värden. Denna plugin behövs inte om du föredrar att sammanfoga strängar för variabler som innehåller avgränsade värden.

## Installera plugin-programmet med tillägget Adobe Experience Platform Launch

Adobe erbjuder ett tillägg som gör att du kan använda de vanligaste plugin-programmen.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på önskad egenskap.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Installera och publicera [!UICONTROL Common Analytics Plugins] tillägget
1. Om du inte redan har det skapar du en regel med namnet&quot;Initiera plugin-program&quot; med följande konfiguration:
   * Villkor: Ingen
   * Händelse: Kärna - Bibliotek inläst (sidan ovanpå)
1. Lägg till en åtgärd i ovanstående regel med följande konfiguration:
   * Tillägg: Vanliga Analytics-plugin-program
   * Åtgärdstyp: Initiera APL (Bifoga till lista)
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med den anpassade kodredigeraren för Launch

Om du inte vill använda plugin-programtillägget kan du använda den anpassade kodredigeraren.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på önskad egenskap.
1. Gå till [!UICONTROL Extensions] fliken och klicka sedan på [!UICONTROL Configure] knappen under Adobe Analytics-tillägget.
1. Expandera dragspelsfliken så att [!UICONTROL Configure tracking using custom code] den visar [!UICONTROL Open Editor] knappen.
1. Öppna den anpassade kodredigeraren och klistra in den plugin-kod som finns nedan i redigeringsfönstret.
1. Spara och publicera ändringarna i Analytics-tillägget.

## Installera plugin-programmet med AppMeasurement

Kopiera och klistra in följande kod var som helst i AppMeasurement-filen när Analytics-spårningsobjektet har instansierats (med [`s_gi`](../functions/s-gi.md)). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

I metoden används följande argument: `apl`

* **`lv`** (required, string): Variabeln som innehåller en avgränsad lista med objekt som ett nytt värde ska läggas till i
* **`vta`** (required, string): En kommaavgränsad lista över nya värden som ska läggas till i `lv` argumentets värde.
* **`d1`** (valfri, sträng): Avgränsaren som används för att separera de enskilda värden som redan finns i `lv` argumentet.  Standardvärdet är ett kommatecken (`,`) när inget anges.
* **`d2`** (valfri, sträng): Utdataavgränsaren. Standardvärdet är samma som `d1` när det inte anges.
* **`cc`** (valfritt, boolesk): En flagga som anger om en skiftlägeskänslig kontroll används. Om `true`det är skiftlägeskänsligt. Om du `false` anger det eller inte gör det är dubblettkontrollen inte skiftlägeskänslig. Standardvärdet är `false`.

Metoden returnerar `apl` värdet för `lv` argumentet plus eventuella icke-duplicerade värden i `vta` argumentet.

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

### Exempel 3

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

...men det slutliga värdet för s.eVar5 kommer att vara

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

### 3.2 (25 september 2019)

* Korrigerade kompatibilitetsproblem med `apl` anrop som använde äldre versioner av plugin-programmet
* Konsolvarningar har tagits bort för att minska storleken
* Tillagd `inList 2.1`

### 3.1 (22 april 2018)

* `d2` argument får nu som standard värdet för `d1` argumentet om det inte anges

### 3.0 (16 april 2018)

* Fullständig omanalys/omskrivning av plugin-program
* Avancerad felkontroll har lagts till
* Argumentet `vta` tar nu emot flera värden samtidigt
* Argumentet har lagts till för att formatera returvärdet `d2`
* Argumentet har ändrats till ett booleskt `cc` argument

### 2.5 (18 februari 2016)

* Använder nu `inList` metoden för jämförelsebearbetning

### 2.0 (26 januari 2016)

* `d` (Delimiter)-argument är nu valfritt (som standard ett komma)
* `u` (Flagga för skiftlägeskänslighet) är nu valfritt (standardvärdet är skiftlägeskänsligt)
* Oavsett argumentet `u` (Skiftlägeskänslighetsflagga) lägger plugin-programmet inte längre till ett värde i en lista om värdet redan finns i listan