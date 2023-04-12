---
title: p_fo (endast sida först)
description: Se till att vissa rutiner bara aktiveras en gång per sida.
feature: Variables
exl-id: e82d77f9-2ea9-4b1b-b645-b12879c344ec
source-git-commit: bbb138d979968ec2536e53ff07001b43156df095
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 0%

---

# Adobe plug-in: p_fo (endast sida först)

{{plug-in}}

The `p_fo` plug-in är ett verktyg som kontrollerar om det finns ett specifikt JavaScript-objekt. Om objektet inte finns skapar plugin-programmet objektet och returnerar `true`. Om JavaScript-objektet redan finns på sidan returneras det `false`. Denna plugin är användbar för att köra kod exakt en gång på en sida. Flera andra plugin-program använder den här koden för att fungera. Denna plugin behövs inte om du inte är orolig för hur många gånger koden körs på en sida eller om du inte använder några beroende plugin-program.

## Installera plugin-programmet med Web SDK-tillägget

Adobe har ett tillägg som gör att du kan använda de vanligaste plugin-programmen med Web SDK.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka **[!UICONTROL Tags]** till vänster och klicka sedan på den önskade taggegenskapen.
1. Klicka **[!UICONTROL Extensions]** till vänster och klicka sedan på **[!UICONTROL Catalog]** tab
1. Leta rätt på och installera **[!UICONTROL Common Web SDK Plugins]** tillägg.
1. Klicka **[!UICONTROL Data Elements]** till vänster och klicka sedan på det önskade dataelementet.
1. Ange det önskade dataelementnamnet med följande konfiguration:
   * Tillägg: Vanliga SDK-plugin-program för webben
   * Dataelement: `p_fo`
1. Spara och publicera ändringarna i dataelementet.

## Installera plugin-programmet manuellt för att implementera Web SDK

Denna plugin stöds ännu inte för användning i en manuell implementering av Web SDK.

## Installera plugin-programmet med Adobe Analytics-tillägget

Adobe har ett tillägg som gör att du kan använda de vanligaste plugin-programmen med Adobe Analytics.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Extensions] klickar du på [!UICONTROL Catalog] knapp
1. Installera och publicera [!UICONTROL Common Analytics Plugins] extension
1. Om du inte redan har det skapar du en regel med namnet&quot;Initiera plugin-program&quot; med följande konfiguration:
   * Villkor: Ingen
   * Händelse: Kärna - Bibliotek inläst (sidan ovanpå)
1. Lägg till en åtgärd i ovanstående regel med följande konfiguration:
   * Tillägg: Plugin-program för vanlig analys
   * Åtgärdstyp: Initiera p_fo
1. Spara och publicera ändringarna i regeln.

## Installera plugin-programmet med en anpassad kodredigerare

Om du inte vill använda tillägget för Common Analytics-plugin-program kan du använda den anpassade kodredigeraren.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på önskad egenskap.
1. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** under Adobe Analytics-tillägget.
1. Expandera [!UICONTROL Configure tracking using custom code] dragspelspanel, som visar [!UICONTROL Open Editor] -knappen.
1. Öppna den anpassade kodredigeraren och klistra in den plugin-kod som finns nedan i redigeringsfönstret.
1. Spara och publicera ändringarna i Analytics-tillägget.

## Installera plugin-programmet med AppMeasurement

Kopiera och klistra in följande kod var som helst i AppMeasurement-filen när Analytics-spårningsobjektet har instansierats (med [`s_gi`](../functions/s-gi.md)). Genom att bevara kommentarer och versionsnummer i koden i implementeringen kan Adobe felsöka eventuella problem.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v3.0 (Requires AppMeasurement) */
function p_fo(c){if("-v"===c)return{plugin:"p_fo",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c){a=b;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.p_fo="3.0");window.__fo||(window.__fo={});if(window.__fo[c])return!1;window.__fo[c]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Använda plugin-programmet

The `p_fo` funktionen använder följande argument:

* **på** (required, string): Namnet på det JavaScript-objekt som skapas av plugin-programmet om objektet inte finns på sidan än.

Om objektet inte finns än returneras den här funktionen `true` och skapar objektet. Om objektet redan finns returnerar funktionen `false`.

## Exempelanrop

### Exempel 1

Följande kod kontrollerar om det finns ett &quot;myobject&quot;-objekt på sidan.  Om &quot;myobject&quot;-objektet inte finns, skapar koden &quot;myobject&quot;-objektet och returnerar värdet true.  Därför kommer koden i villkorssatsen (t.ex. Console.log(&#39;hello&#39;);) att köras.

Å andra sidan, om objektet &quot;myobject&quot; redan finns när anropet p_fo inträffar, returnerar funktionen p_fo värdet false och villkorssatsen betraktas därför som false.  I det här fallet kommer koden i villkorssatsen inte att köras.

```js
if(p_fo("myobject"))
{
  console.log("hello");
}
```

**OBS!** Varje gång ett nytt sidobjekt/DOM läses in (eller den aktuella sidan läses in igen), finns inte längre det objekt som anges i on-argumentet och plug-in-filen p_fo returnerar alltså true igen första gången den körs efter att sidan har lästs in.

## Versionshistorik

### 3.0 (19 mars 2021)

* Versionsnummer har lagts till som kontextdata.

### 2.0

* Punktrelease (omkompilerad, mindre kodstorlek).
* Ändrad typ av returvärde från heltal till booleskt värde

### 1.0

* Ursprunglig version.
