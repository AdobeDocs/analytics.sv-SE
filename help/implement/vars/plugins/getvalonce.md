---
title: getValOnce
description: Förhindra att en Analytics-variabel ställs in på samma värde två gånger i rad.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe plug-in: getValOnce

> [!IMPORTANT] Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Plugin-programmet förhindrar att en variabel ställs in som lika med samma värde mer än en gång. `getValOnce` Adobe rekommenderar att du använder denna plugin när du vill ta bort dubbletter av förekomster där en besökare uppdaterar en sida eller på annat sätt besöker en viss sida flera gånger. Denna plugin behövs inte om du inte är orolig för mätvärdet &#39;Förekomster&#39; i Analysis Workspace.

## Installera plugin-programmet med Adobe Experience Platform Launch-tillägget

Adobe erbjuder ett tillägg som gör att du kan använda de vanligaste plugin-programmen.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på önskad egenskap.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Installera och publicera [!UICONTROL Common Analytics Plugins] tillägget
1. Om du inte redan har det skapar du en regel med namnet&quot;Initiera plugin-program&quot; med följande konfiguration:
   * Villkor: Ingen
   * Händelse: Kärna - Bibliotek inläst (sidan ovanpå)
1. Lägg till en åtgärd i ovanstående regel med följande konfiguration:
   * Tillägg: Plugin-program för vanlig analys
   * Åtgärdstyp: Initiera getValOnce
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

Kopiera och klistra in följande kod var som helst i AppMeasurement-filen efter att Analytics-spårningsobjektet har instansierats (med `s_gi`). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getValOnce v2.0 */
s.getValOnce=function(vtc,cn,et,ep){if(vtc&&(cn=cn||"s_gvo",et=et||0,ep="m"===ep?6E4:864E5,vtc!==this.c_r(cn))){var e=new Date;e.setTime(e.getTime()+et*ep);this.c_w(cn,vtc,0===et?0:ep);return vtc}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

I metoden används följande argument: `getValOnce`

* **`vtc`** (required, string): Variabeln som ska kontrolleras och se om den precis har ställts in på ett identiskt värde
* **`cn`** (valfri, sträng): Namnet på den cookie som innehåller värdet som ska kontrolleras. Standardvärdet är `"s_gvo"`
* **`et`** (valfritt, heltal): Cookie-filens förfallodatum i dagar (eller minuter, beroende på `ep` argumentet). Standardvärdet är `0`, som upphör i slutet av webbläsarsessionen
* **`ep`** (valfri, sträng): Ange bara det här argumentet om även `et` argumentet anges. Ställ in det här argumentet på `"m"` om du vill att `et` argumentet ska förfalla om några minuter i stället för dagar. Standardvärdet är `"d"`, vilket anger `et` argumentet i dagar.

Om argumentet och cookie-värdet matchar returnerar den här metoden en tom sträng. `vtc` Om `vtc` argumentet och cookie-värdet inte matchar returnerar metoden `vtc` argumentet som en sträng.

## Exempelanrop

### Exempel 1

Använd det här anropet för att förhindra att samma värde skickas till s.campaign mer än en gång i rad under de kommande 30 dagarna:

```js
s.campaign=s.getValOnce(s.campaign,"s_campaign",30);
```

I anropet ovan kommer plugin-programmet först att jämföra värdet som redan finns i s_campaign-cookien med värdet som kommer från den aktuella s.campaign-variabeln.   Om ingen matchning görs kommer plugin-programmet att ställa in s_campaign-cookien som lika med det nya värdet som kommer från s.campaign och sedan returnera det nya värdet.   Jämförelsen kommer att göras de kommande trettio dagarna

### Exempel 2

Använd det här anropet för att förhindra att samma värde anges under hela sessionen:

```js
s.eVar2=s.getValOnce(s.eVar2,"s_ev2",0,"m");
```

Den här koden förhindrar att samma värde skickas till s.eVar2 flera gånger i rad under en användarsession.  m-värdet i stycket (i slutet av anropet) ignoreras eftersom förfallotiden är lika med 0.   I koden lagras också jämförelsevärdet i s_ev2-cookien.

## Versionshistorik

### 2.0

* Punktrelease (omkompilerad, mindre kodstorlek).

### 1.1

* Alternativet att välja minuter eller dagar för förfallodatum har lagts till via `t` parametern.
* Variabelns omfång som `k` används för att begränsa den till plugin-programmet har korrigerats. Den här ändringen förhindrar eventuell störning av annan kod på sidan.
