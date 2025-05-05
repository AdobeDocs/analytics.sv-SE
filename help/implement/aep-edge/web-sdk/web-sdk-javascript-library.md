---
title: Skicka data till Adobe Analytics med Web SDK JavaScript-biblioteket
description: Börja med en ren Web SDK-implementering för att skicka data till Adobe Analytics med hjälp av JavaScript-biblioteket.
exl-id: 593b63ac-e411-4f88-af7e-78f026269ec0
source-git-commit: bfafc1f8eddf82b34fb45e3d6197213f0cee0d97
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 0%

---

# Skicka data till Adobe Analytics med Web SDK JavaScript-biblioteket

Den här implementeringssökvägen innebär en ny Web SDK-installation med Web SDK JavaScript-biblioteket. Andra implementeringsvägar beskrivs på separata sidor:

* [SDK-taggtillägg för webben](web-sdk-tag-extension.md): En ny SDK-installation med taggtillägget Web SDK. Liknar Web SDK JavaScript Library-metoden (den här sidan), förutom att du hanterar implementeringen med hjälp av taggar i Adobe Experience Platform Data Collection. Det kräver fältgruppen Adobe Analytics ExperienceEvent, som innehåller typiska analysvariabler som ska inkluderas i XDM-schemat.
* [Analystillägg för Web SDK-tillägg](analytics-extension-to-web-sdk.md): Gå från Adobe Analytics-taggtillägg till Web SDK-taggtillägg på ett smidigt och metodiskt sätt. På så sätt slipper du använda XDM tills din organisation är redo att använda Adobe Experience Platform-tjänster, till exempel Customer Journey Analytics. Använd objektet `data` i stället för objektet `xdm` för att skicka data till Adobe.
* [AppMeasurement till Web SDK JavaScript-bibliotek](appmeasurement-to-web-sdk.md): Ett smidigt och metodiskt sätt att migrera till Web SDK, förutom att taggar inte används. I stället kan du ta bort Adobe Analytics datainsamlingsbibliotek (`AppMeasurement.js`) manuellt och ersätta det med Web SDK JavaScript-biblioteket (`alloy.js`).

## Fördelar och nackdelar med implementeringsvägen

Att använda Web SDK JavaScript-biblioteket för att skicka data till Adobe Analytics har både fördelar och nackdelar. Väg noga in varje alternativ för att avgöra vilken metod som är bäst för er organisation.

| Fördelar | Nackdelar |
| --- | --- |
| <ul><li>**Direkt metod**: Den här implementeringsvägen är enklare än strategier som flyttar befintliga Adobe Analytics-implementeringar. Om du inte har någon Adobe Analytics-implementering att tänka på fyller du i de tillämpliga Web SDK XDM-fälten.</li><li>**Fördefinierat schema**: Om din organisation inte behöver ditt eget schema kan du helt enkelt använda det schema som är riktat mot Adobe Analytics. Det här konceptet gäller även när du går mot Customer Journey Analytics; konceptet med props och eVars gäller inte Customer Journey Analytics, men du kan fortsätta använda props och eVars som enkla anpassade dimensioner.</li></ul> | <ul><li>**Implementeringsändringar kräver åtgärd från utvecklaren**: Om du vill ändra implementeringen av din Web SDK måste du arbeta med utvecklingsteamet för att redigera koden på din webbplats. Den metod som använder [Web SDK-taggtillägget](web-sdk-tag-extension.md) undviker den här nackdelen.</li><li>**Låst till att använda ett specifikt schema**: När din organisation flyttas till Customer Journey Analytics måste du välja att fortsätta använda Adobe Analytics-schemat eller migrera till din egen organisations schema (som skulle vara en separat datauppsättning). Om din organisation vill undvika både Adobe Analytics-schemat och migrering till en separat datauppsättning när den flyttar till Customer Journey Analytics rekommenderar Adobe en av följande två metoder:</li><ul><li>Använd objektet `data`: Med objektet `data` kan du skicka data till Adobe Analytics utan att följa ett XDM-schema. När din organisations schema har skapats kan du använda datastream-mappning för att mappa `data` objektfält till XDM. Både [Analytics-tillägget för Web SDK-tillägget](analytics-extension-to-web-sdk.md) och [-AppMeasurementet för Web SDK JavaScript-biblioteket](appmeasurement-to-web-sdk.md) använder det här `data`-objektet.</li><li>Hoppa över Adobe Analytics helt: Om du implementerar Web SDK kan du skicka dessa data till en datauppsättning i Adobe Experience Platform för användning i Customer Journey Analytics. Du kan använda vilket schema som helst. Adobe Analytics är inte involverat alls i det här arbetsflödet och därför krävs inte fältgruppen Adobe Analytics ExperienceEvent. Den här metoden medför minst teknisk skuld, men lämnar också Adobe Analytics helt utanför bilden.</li></ul></ul> |

>[!IMPORTANT]
>
>Den här implementeringsmetoden kräver att du använder ett schema som konfigurerats för Adobe Analytics. Om din organisation planerar att använda ditt eget schema med Customer Journey Analytics i framtiden kan Adobe Analytics-schemat skapa förvirring för dataadministratörer och arkitekter. Det finns flera alternativ för att minska detta hinder:
>
>* Du kan använda Adobe Analytics-schemat i CJA. Observera att CJA inte har något koncept för props eller eVars. De behandlas som andra schemafält. Observera också att användningen av Adobe Analytics-schemat i CJA kan göra det svårare att använda andra plattformstjänster, som Adobe Journey Optimizer och Real-time Customer Data Platform.
>* Du kan använda dataobjektet, ungefär som ett migreringsarbetsflöde. Observera att användningen av dataobjektet kräver att du mappar varje dataobjektfält till ett XDM-schemafält.
>* Du kan hoppa över Adobe Analytics-implementeringen helt och skicka data till Adobe Experience Platform med ditt eget schema. Den här metoden är idealisk på lång sikt och gör att din organisation kan börja använda Customer Journey Analytics.

## Steg som krävs för att implementera JavaScript-biblioteket för Web SDK

Översikt över implementeringsuppgifterna på hög nivå:

![Så här implementerar du Adobe Analytics med hjälp av Web SDK-arbetsflöde, vilket beskrivs i det här avsnittet.](../../assets/websdk-annotated.png)

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
<td> 4</td>
<td><b>Installera den fördefinierade fristående versionen</b>. Du kan referera till biblioteket (<code>alloy.js</code>) på CDN direkt på sidan eller hämta och lagra det på din egen infrastruktur. Du kan också använda NPM-paketet.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/install/library.html?lang=sv-SE">Installera den fördefinierade fristående versionen</a> och <a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/install/npm.html?lang=sv-SE">Använda NPM-paketet</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Konfigurera en datastream</b>. En datastream representerar konfigurationen på serversidan när Adobe Experience Platform Web SDK implementeras.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=sv-SE">Konfigurera ett datastream<a></td> 
</tr>

<td>6</td>
<td><b>Lägg till en Adobe Analytics-tjänst</b> i ditt datastream. Tjänsten styr om och hur data skickas till Adobe Analytics och till vilka rapporteringsprogram.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=sv-SE#analytics">Lägg till Adobe Analytics-tjänst i ett datastream</a></td>
</tr>

<tr>
<td>7</td>
<td><b>Konfigurera Web SDK</b>. Kontrollera att biblioteket som du installerade i steg 4 är korrekt konfigurerat med dataStream ID (tidigare kanttskonfigurations-ID (<code>datastreamId</code>)), organisations-ID (<code>orgId</code>) och andra tillgängliga alternativ. Kontrollera att variablerna mappas korrekt. </td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/commands/configure/overview.html?lang=sv-SE">Konfigurera Web SDK</a><br/><a href="../xdm-var-mapping.md">XDM-objektvariabelmappning</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Kör kommandon</b> och/eller <b>spåra händelser</b>. När baskoden har implementerats på webbsidan kan du börja köra kommandon och spåra händelser med SDK.
</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/commands/sendevent/overview.html?lang=sv-SE">Skicka händelser</a></td>
</tr>

<tr>
<td>9</td><td><b>Utöka och validera implementeringen</b> innan du skickar ut den till produktion.</td><td></td> 
</tr>
</table>
