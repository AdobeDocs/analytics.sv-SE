---
title: Skicka data till Adobe Analytics med hjälp av taggtillägget Web SDK
description: Börja med en ren implementering av Adobe Experience Platform Data Collection för att skicka data till Adobe Analytics med XDM och fältgruppen Adobe Analytics ExperienceEvent.
exl-id: 235b3d68-92dd-4ca4-8889-1e1f2d83f47e
source-git-commit: 316ca1074de36db0d7c9545691e7c6d72a2ed2c4
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 0%

---

# Skicka data till Adobe Analytics med hjälp av taggtillägget Web SDK

Den här implementeringssökvägen innebär en ny Web SDK-installation med taggar i Adobe Experience Platform Data Collection. Andra implementeringsvägar beskrivs på separata sidor:

* [JavaScript-bibliotek för Web SDK](web-sdk-javascript-library.md): En ny SDK-installation med JavaScript-biblioteket för Web SDK (`alloy.js`). Liknar taggtilläggsmetoden för Web SDK (den här sidan), förutom att du själv hanterar implementeringen i stället för att använda tagggränssnittet. Det kräver fältgruppen Adobe Analytics ExperienceEvent, som innehåller typiska analysvariabler som ska inkluderas i XDM-schemat.
* [Analystillägg för Web SDK-tillägg](analytics-extension-to-web-sdk.md): Gå från Adobe Analytics-taggtillägg till Web SDK-taggtillägg på ett smidigt och metodiskt sätt. På så sätt slipper du använda XDM tills din organisation är redo att använda Adobe Experience Platform-tjänster, till exempel Customer Journey Analytics. Använd objektet `data` i stället för objektet `xdm` för att skicka data till Adobe.
* [AppMeasurement till Web SDK JavaScript-bibliotek](appmeasurement-to-web-sdk.md): Ett smidigt och metodiskt sätt att migrera till Web SDK, förutom att taggar inte används. I stället tar du bort Adobe Analytics datainsamlingsbibliotek (`AppMeasurement.js`) manuellt och ersätter det med Web SDK JavaScript-biblioteket (`alloy.js`).

## Fördelar och nackdelar med implementeringsvägen

Att använda Web SDK-tillägget för att skicka data till Adobe Analytics har både fördelar och nackdelar. Väg noga in varje alternativ för att avgöra vilken metod som är bäst för er organisation.

| Fördelar | Nackdelar |
| --- | --- |
| <ul><li>**Den mest direkta metoden**: Den här implementeringsvägen är den enklaste och oftast den rekommenderade sökvägen för nya Web SDK-implementeringar. Om du inte har någon Adobe Analytics-implementering att tänka på fyller du i de tillämpliga Web SDK XDM-fälten.</li><li>**Fördefinierat schema**: Om din organisation inte behöver ditt eget schema kan du helt enkelt använda det schema som är riktat mot Adobe Analytics. Det här konceptet gäller även när du går mot Customer Journey Analytics; konceptet med props och eVars gäller inte Customer Journey Analytics, men du kan fortsätta använda props och eVars som enkla anpassade dimensioner.</li><li>**Hantera taggar utan utvecklaråtgärd**: Med taggar kan du hantera implementeringen utan att begära att utvecklare gör kodändringar i implementeringen. Utvecklarna installerar skriptet för tagginläsaren och du har fullständig kontroll över hur data samlas in.</li></ul> | <ul><li>**Låst till att använda ett specifikt schema**: När din organisation flyttas till Customer Journey Analytics måste du välja att fortsätta använda Adobe Analytics-schemat eller migrera till din egen organisations schema (som skulle vara en separat datauppsättning). Om din organisation vill undvika både Adobe Analytics-schemat och migrering till en separat datauppsättning när den flyttar till Customer Journey Analytics rekommenderar Adobe en av följande två metoder:<ul><li>Använd objektet `data`: Med objektet `data` kan du skicka data till Adobe Analytics utan att följa ett XDM-schema. När din organisations schema har skapats kan du använda datastream-mappning för att mappa `data` objektfält till XDM. Både [Analytics-tillägget för Web SDK-tillägget](analytics-extension-to-web-sdk.md) och [-AppMeasurementet för Web SDK JavaScript-biblioteket](appmeasurement-to-web-sdk.md) använder det här `data`-objektet.</li><li>Hoppa över Adobe Analytics helt: Om du implementerar Web SDK kan du skicka dessa data till en datauppsättning i Adobe Experience Platform för användning i Customer Journey Analytics. Du kan använda vilket schema som helst. Adobe Analytics är inte involverat alls i det här arbetsflödet och därför krävs inte fältgruppen Adobe Analytics ExperienceEvent. Den här metoden medför minst teknisk skuld, men lämnar också Adobe Analytics helt utanför bilden.</li></ul></ul> |

>[!IMPORTANT]
>
>Den här implementeringsmetoden kräver att du använder ett schema som konfigurerats för Adobe Analytics. Om din organisation planerar att använda ditt eget schema med Customer Journey Analytics i framtiden kan Adobe Analytics-schemat skapa förvirring för dataadministratörer och arkitekter. Det finns flera alternativ för att minska detta hinder:
>
>* Du kan använda Adobe Analytics-schemat i CJA. Observera att CJA inte har något koncept för props eller eVars. De behandlas som andra schemafält. Observera också att användningen av Adobe Analytics-schemat i CJA kan göra det svårare att använda andra plattformstjänster, som Adobe Journey Optimizer och Real-time Customer Data Platform.
>* Du kan använda dataobjektet, ungefär som ett migreringsarbetsflöde. Observera att användningen av dataobjektet kräver att du mappar varje dataobjektfält till ett XDM-schemafält.
>* Du kan hoppa över Adobe Analytics-implementeringen helt och skicka data till Adobe Experience Platform med ditt eget schema. Den här metoden är idealisk på lång sikt och gör att din organisation kan börja använda Customer Journey Analytics.

## Steg som krävs för att implementera taggtillägget Web SDK

Översikt över implementeringsuppgifterna på hög nivå:

![Så här implementerar du Adobe Analytics med hjälp av ett arbetsflöde för Web SDK-tillägg, vilket beskrivs i det här avsnittet.](../../assets/websdk-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Uppgift</b></th><th style="width:35%"><b>Mer information</b></th>
</tr>

<tr>
<td>1</td>
<td>Se till att du har <b>definierat en rapportserie</b>.</td>
<td><a href="/help/admin/admin/c-manage-report-suites/report-suites-admin.md">Report Suite Manager</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Konfigurera scheman</b>. För att standardisera datainsamlingen för användning i olika program som utnyttjar Adobe Experience Platform har Adobe skapat den öppna och offentligt dokumenterade standarden Experience Data Model (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=sv-SE">Översikt över schemaanvändargränssnittet</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Skapa ett datalager</b> för att hantera spårningen av data på webbplatsen.</td>
<td><a href="../../prepare/data-layer.md">Skapa ett datalager</a></td>
</tr>

<tr>
<td>4</td>
<td><b>Konfigurera en datastream</b>. En datastream representerar konfigurationen på serversidan när Adobe Experience Platform Web SDK implementeras.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=sv-SE">Konfigurera ett datastream<a></td> 
</tr>

<tr>
<td>5</td> 
<td><b>Lägg till en Adobe Analytics-tjänst</b> i ditt datastream. Tjänsten styr om och hur data skickas till Adobe Analytics och till vilka rapporteringsprogram.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=sv-SE#analytics">Lägg till Adobe Analytics-tjänst i ett datastream</a></td>
</tr>

<tr>
<td>6</td>
<td><b>Skapa en taggegenskap</b>. Egenskaper är överliggande behållare som används för att referera till tagghanteringsdata.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=sv-SE#for-web">Skapa eller konfigurera en taggegenskap för webben</a></td>
</tr>

<tr>
<td>7</td> 
<td><b>Installera och konfigurera Web SDK-tillägget</b> i taggegenskapen. Konfigurera Web SDK-tillägget för att skicka data till den dataström som konfigurerats i steg 4.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=sv-SE">Adobe Experience Platform Web SDK-tillägg - översikt</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Upprepa, validera och publicera</b> i produktionen. Bädda in kod för att inkludera taggegenskapen på webbplatsens sidor. Använd sedan dataelement, regler och så vidare för att anpassa implementeringen.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=sv-SE#embed-code">Bädda in kod</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=sv-SE">Översikt över publicering</a></td>
</tr>

</table>
