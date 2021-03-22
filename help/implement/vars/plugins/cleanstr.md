---
title: cleanStr
description: Ta bort eller ersätt alla onödiga tecken från en sträng.
translation-type: tm+mt
source-git-commit: c1a19f79eba3e992747a14146ca93306f84b355b
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 1%

---


# Adobe plug-in: clearStr

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Plugin-programmet `cleanStr` tar bort eller ersätter alla onödiga tecken från en sträng, inklusive HTML-taggar, extra blanksteg, tabbar och radmatningar. Den ersätter också vänster/höger enkla citattecken (`‘` och `’`) med raka enkla citattecken (`'`). Adobe rekommenderar att du använder det här plugin-programmet om du vill ta bort onödiga tecken från variabelvärden, och funktionen&quot;Clean text&quot; i Launch uppfyller inte dina implementeringsbehov. Detta plugin-program är inte nödvändigt om insamlade data inte innehåller onödiga tecken, eller om funktionen &quot;Rengör text&quot; i Launch är tillräcklig.

## Installera plugin-programmet med Adobe Experience Platform Launch-tillägget

Adobe har ett tillägg som gör att du kan använda de vanligaste plugin-programmen.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt Adobe-ID.
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Catalog]
1. Installera och publicera tillägget [!UICONTROL Common Analytics Plugins]
1. Om du inte redan har det skapar du en regel med namnet&quot;Initiera plugin-program&quot; med följande konfiguration:
   * Villkor: Ingen
   * Händelse: Kärna - Bibliotek inläst (sidan ovanpå)
1. Lägg till en åtgärd i ovanstående regel med följande konfiguration:
   * Tillägg: Plugin-program för vanlig analys
   * Åtgärdstyp: Initiera cleanStr
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med den anpassade kodredigeraren för Launch

Om du inte vill använda plugin-programtillägget kan du använda den anpassade kodredigeraren.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt Adobe-ID.
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics-tillägget.
1. Expandera dragspelet [!UICONTROL Configure tracking using custom code], som visar knappen [!UICONTROL Open Editor].
1. Öppna den anpassade kodredigeraren och klistra in den plugin-kod som finns nedan i redigeringsfönstret.
1. Spara och publicera ändringarna i Analytics-tillägget.

## Installera plugin-programmet med AppMeasurement

Kopiera och klistra in följande kod var som helst i AppMeasurement-filen när Analytics-spårningsobjektet har instansierats (med [`s_gi`](../functions/s-gi.md)). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: cleanStr v2.0 (No Prerequisites Required) */
function cleanStr(str){var a=str;if("-v"===a)return{plugin:"cleanStr",version:"2.0"};a:{if("undefined"!==typeof window.s_c_il){var b=0;for(var c;b<window.s_c_il.length;b++)if(c=window.s_c_il[b],c._c&&"s_c"===c._c){b=c;break a}}b=void 0}"undefined"!==typeof b&&(b.contextData.cleanStr="2.0");if("string"===typeof a){a=a.replace(/<\/?[^>]+(>|$)/g,"");a=a.trim();a=a.replace(/[\u2018\u2019\u201A]/g,"'");a=a.replace(/\t+/g,"");for(a=a.replace(/[\n\r]/g," ");-1<a.indexOf("  ");)a=a.replace(/\s\s/g," ");return a}return""}
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Metoden `cleanStr` använder följande argument:

* **`str`** (required, string): Värdet som du vill rensa HTML-kodning, extra blanksteg, tabbar eller andra onödiga tecken.

Metoden returnerar värdet för argumentet `str` med alla onödiga tecken borttagna.

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

...eVar1 anges som lika med &quot;this is a messystring&quot; (alla extra blanksteg och alla tabbtecken tas bort)

### Exempel 3

Om..

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

...och följande kod körs...

```js
cleanStr(s.eVar1)
```

...Slutvärdet för s.eVar1 kommer fortfarande att vara:

```js
"»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

Om du kör plugin-programmet för sig själv (utan att tilldela returvärdet till en variabel) &quot;återställs&quot; inte variabeln som skickas via str-argumentet.

## Versionshistorik

### 2.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 1.0 (15 april 2018)

* Ursprunglig version.
