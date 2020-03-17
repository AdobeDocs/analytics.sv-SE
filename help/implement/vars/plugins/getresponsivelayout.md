---
title: getResponsiveLayout
description: Bestäm vilken layout för en webbplats som visas just nu.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Adobe plug-in: getResponsiveLayout

> [!IMPORTANT] Denna plugin tillhandahålls av Adobe Consulting för att hjälpa er att få ut mer av Adobe Analytics. Adobes kundtjänst ger ingen support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med `getResponsiveLayout` plugin-programmet kan du hålla reda på vilken version av den responsiva designbaserade webbplatsen som en besökare tittar på just nu. Adobe rekommenderar att du använder denna plugin om webbplatsen har en responsiv design och du vill spåra den version av webbplatsen som besökaren visar. Denna plugin behövs inte om webbplatsen inte använder responsiv design.

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
   * Åtgärdstyp: Initiera getResponsiveLayout
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
/* Adobe Consulting Plugin: getResponsiveLayout v1.0 */
var getResponsiveLayout=function(ppw,plw,tw){if(!(isNaN(ppw)||isNaN(plw)||isNaN(tw)||plw<ppw||tw<plw)){var b=window.innerWidth|| document.documentElement.clientWidth||document.body.clientWidth;return(ppw<plw&&b<=plw?b<=ppw?"phone portrait layout":"phone landscape layout":b<=plw?"phone layout":b<=tw?"tablet layout":"desktop layout")+":"+b+"x"+(window.innerHeight|| document.documentElement.clientHeight||document.body.clientHeight)}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

I metoden används följande argument: `getResponsiveLayout`

* **`ppw`** (obligatoriskt, heltal): Den maximala pixelbredden som ett webbläsarfönster kan ha innan sidan växlar från en stående telefonlayout till en liggande telefonlayout
* **`plw`** (obligatoriskt, heltal): Den maximala pixelbredden som ett webbläsarfönster kan ha innan sidan växlar från en liggande telefonlayout till en surfplattebaserad layout
* **`tw`** (obligatoriskt, booleskt): Den maximala pixelbredden som ett webbläsarfönster kan ha innan sidan växlar från en surfplattelayout till en skrivbordsbaserad layout

Om den här metoden anropas returneras en sträng som innehåller två delar. I den första delen används av följande värden, beroende på webbläsarens bredd och ovanstående argument:

* `"phone portrait layout"`
* `"phone landscape layout"`
* `"phone layout"` (för webbplatser som inte har både stående och liggande layout)
* `"tablet layout"`
* `"desktop layout"`

Den andra delen av den returnerade strängen är webbläsarens bredd- och höjdmått. Exempel, `"desktop layout:1243x700"`.

## Exempelanrop

### Exempel 1

Om..

* Webbplatsen växlar från stående telefonläge till liggande telefonläge när webbläsarbredden är större än 500 pixlar
* Webbplatsen växlar från liggande telefonläge till surfplatteläge när webbläsarbredden är större än 700 pixlar
* Webbplatsen växlar från surfplatteläge till skrivbordsläge när webbläsarbredden är större än 1 000 pixlar

...följande kod ställer in eVar10 lika med den aktuella responsiva designlayouten som besökaren upplever, liksom webbläsarens bredd och dimensioner

```js
s.eVar10 = getResponsiveLayout(500, 700, 1000);
```

### Exempel 2

Om..

* Webbplatsen har endast telefonläge, surfplatteläge och skrivbordsläge
* Webbplatsen växlar från telefonläge till surfplatteläge när webbläsarbredden är större än 500 pixlar
* Webbplatsen växlar från surfplatteläge till skrivbordsläge när webbläsarbredden är större än 1 100 pixlar

...följande kod ställer in eVar10 lika med den aktuella responsiva designlayouten som besökaren upplever, liksom webbläsarens bredd och dimensioner

```js
s.eVar10 = getResponsiveLayout(500, 500, 1100);
```

## Versionshistorik

### 1.0 (2 maj 2018)

* Ursprunglig version.
