---
title: getResponsiveLayout
description: Bestäm vilken layout för en webbplats som visas just nu.
exl-id: 5b192d02-fc3c-4b82-acb4-42902202ab5f
source-git-commit: ab078c5da7e0e38ab9f0f941b407cad0b42dd4d1
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---

# Adobe plug-in: getResponsiveLayout

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du kontohanteraren i din organisation. De kan ordna ett möte med en konsult för att få hjälp.

Med `getResponsiveLayout` plugin-programmet kan du spåra vilken version av den responsiva designbaserade webbplatsen som en besökare tittar på just nu. Adobe rekommenderar att du använder denna plugin om webbplatsen använder responsiv design och du vill spåra den version av webbplatsen som besökaren visar. Denna plugin behövs inte om webbplatsen inte använder responsiv design.

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
   * Åtgärdstyp: Initiera getResponsiveLayout
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
/* Adobe Consulting Plugin: getResponsiveLayout v1.1 (Requires AppMeasurement) */
var getResponsiveLayout=function(ppw,plw,tw){var c=ppw,b=plw,e=tw;if("-v"===c)return{plugin:"getResponsiveLayout",version:"1.1"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var d;a<window.s_c_il.length;a++)if(d=window.s_c_il[a],d._c&&"s_c"===d._c){a=d;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.getResponsiveLayout="1.1");if(!(isNaN(c)||isNaN(b)||isNaN(e)||b<c||e<b))return a=window.innerWidth||document.documentElement.clientWidth||document.body.clientWidth,(c<b&&a<=b?a<=c?"phone portrait layout":"phone landscape layout":a<=b?"phone layout":a<=e?"tablet layout":"desktop layout")+":"+a+"x"+(window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

Funktionen `getResponsiveLayout` använder följande argument:

* **`ppw`** (obligatoriskt, heltal): Den maximala pixelbredden som ett webbläsarfönster kan ha innan sidan växlar från en stående telefonlayout till en liggande telefonlayout
* **`plw`** (obligatoriskt, heltal): Den maximala pixelbredden som ett webbläsarfönster kan ha innan sidan växlar från en liggande telefonlayout till en surfplattebaserad layout
* **`tw`** (obligatoriskt, heltal): Den maximala pixelbredden som ett webbläsarfönster kan ha innan sidan växlar från en surfplattelayout till en skrivbordsbaserad layout

När den här funktionen anropas returneras en sträng som innehåller två delar avgränsade med kolon (`:`). Den första delen av strängen innehåller ett av följande värden, beroende på webbläsarens bredd och argumenten ovan:

* `"phone portrait layout"`
* `"phone landscape layout"`
* `"phone layout"` (för webbplatser som inte har både stående och liggande layout)
* `"tablet layout"`
* `"desktop layout"`

Den andra delen av den returnerade strängen är webbläsarens bredd- och höjdmått. Exempel, `"desktop layout:1243x700"`.

## Exempel

```js
// A visitor accesses your site on their laptop. The browser window is maximized.
// * Your site switches from phone portrait mode to phone landscape mode when the browser width is greater than 500 pixels
// * Your site switches from phone landscape mode to tablet mode when the browser width is greater than 700 pixels
// * Your site switches from tablet mode to desktop mode when the browser width is greater than 1000 pixels
// Sets eVar10 to "desktop layout:1920x937".
s.eVar10 = getResponsiveLayout(500, 700, 1000);

// A visitor accesses your site on their phone.
// * Your site has only a phone mode, a tablet mode, and a desktop mode
// * Your site switches from phone mode to tablet mode when the browser width is greater than 800 pixels
// * Your site switches from tablet mode to desktop mode when the browser width is greater than 1,100 pixels
// Sets eVar10 to "phone portrait layout:720x1280"
s.eVar10 = getResponsiveLayout(800, 800, 1100);
```

## Versionshistorik

### 1.1 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 1.0 (2 maj 2018)

* Ursprunglig version.
