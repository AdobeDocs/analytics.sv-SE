---
title: clearStr
description: Ta bort eller ersätt alla onödiga tecken från en sträng.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe plug-in: clearStr

> [!IMPORTANT] Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Plugin-programmet `cleanStr` tar bort eller ersätter alla onödiga tecken från en sträng, inklusive HTML-taggar, extra blanksteg, tabbar och radmatnings-/radmatningstecken. Den ersätter också inledande och avslutande citattecken (`‘` och `’`) raka enkla citattecken (`'`). Adobe rekommenderar att du använder det här plugin-programmet om du vill ta bort onödiga tecken från variabelvärden, och funktionen&quot;Clean text&quot; i Launch inte uppfyller dina implementeringsbehov. Detta plugin-program är inte nödvändigt om insamlade data inte innehåller onödiga tecken, eller om funktionen &quot;Rengör text&quot; i Launch är tillräcklig.

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
   * Åtgärdstyp: Initiera cleanStr
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
/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"");str=str.trim(); str=str.replace(/[\u2018\u2019\u201A]/g,"'");str=str.replace(/\t+/g,"");for(str=str.replace(/[\n\r]/g," ");-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

I metoden används följande argument: `cleanStr`

* **`str`** (required, string): Värdet som du vill rensa HTML-kodning, extra blanksteg, tabbar eller andra onödiga tecken.

Metoden returnerar värdet för `str` argumentet med alla onödiga tecken borttagna.

## Exempel

### Exempel 1

Anta följande (där punkterna representerar mellanslag och pilarna representerar tabbtecken)

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

När du kör följande kod..

```js
s.eVar1 = cleanStr(s.eVar1)
```

...eVar1 kommer att anges som lika med &quot;this is a messystring&quot; (med alla extra blanksteg och alla tabbtecken borttagna)

### Exempel 2

Om..

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

...och följande kod körs...

```js
cleanStr(s.eVar1)
```

...det slutliga värdet för s.eVar1 kommer fortfarande att vara:

```js
"»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

Om du kör plugin-programmet för sig själv (utan att tilldela returvärdet till en variabel) &quot;återställs&quot; inte variabeln som skickas via str-argumentet.

## Versionshistorik

### 1.0 (15 april 2018)

* Ursprunglig version.
