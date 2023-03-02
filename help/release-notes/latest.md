---
title: Versionsinformation om den senaste analysen
description: Se versionsinformationen för Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 6c6682202e8780ddb9bf96a4bdd61ff0558c9f09
workflow-type: tm+mt
source-wordcount: '1117'
ht-degree: 3%

---

# Aktuell versionsinformation för Adobe Analytics (februari 2023)

**Senaste uppdatering**: 27 februari 2023

Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner i Adobe Analytics

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Uppdaterat användargränssnitt för etiketter för datasekretess** | Det uppdaterade gränssnittet effektiviserar processen att skapa, hantera och redigera dataintegritetsetiketter för rapportsvitens komponenter. [Läs mer](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-setup-reportsuite.html?lang=en) | Ej tillämpligt | 8 februari 2023 |
| **Dölj datumintervall för jämförelse i Mobile Scorecards** | Med Mobile Scorecards kan du växla **[!UICONTROL Include comparison dates]** inställning för att visa eller dölja jämförelsedatum. | Ej tillämpligt | 8 februari 2023 |
| **Kalenderuppdateringar på arbetsytan** | <ul><li>Datum för ankarpanel: Du kan göra datumintervallets komponenter relativa till panelkalendern. [Läs mer](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#relative-panel-dates)</li><li>Uppdateringar av kalenderformat: Kalenderformaten i hela användargränssnittet har uppgraderats för att ge ett mer konsekvent och lättanvänt arbetsflöde.</li><li>Uppdateringar av kalenderformel: Om du använder relativa datum återspeglar alla kalenderformler början av panelens datumintervall. [Läs mer](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#formula-relative-dates)</li></ul> | Ej tillämpligt | 8 februari 2023 |
| **Uppdateringar för paneldatumintervall** | I Workspace har vi lagt till följande förbättringar:<ul><li>Från och med februari-versionen baseras förhandsgranskningarna av komponenter och data på panelens datumintervall och inte på de senaste 90 dagarna. </li><li>Alla dimensionsobjekt som visas är tillgängliga baserat på panelens datumintervall.</li><li>Alla förhandsvisningar av datum i segmentet och beräknade mätvärden baseras på panelens datumintervall (såvida de inte öppnas från komponenthanterarna, som inte har någon associerad panel, kommer de fortfarande att baseras på de senaste 90 dagarna).</li><li>Förhandsgranskningar av data visar data eller komponenter baserat på panelens datumintervall.</li></ul> | Ej tillämpligt | 8 februari 2023 |
| **Rad-/kolumnfiltrering för Adobe Analytics Source Connector-direktuppspelning** | Med Analytics Source Connector i Adobe Experience Platform går det nu att filtrera analysdata som används för att fylla i profiler i [Kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en). Filtrering på radnivå minskar antalet händelser som är associerade med profiler. Filtrering på kolumnnivå bidrar till att minska detaljrikedomen i själva händelserna och gör att du kan optimera användningen av profilberättiganden. Denna filtrering gäller endast data som skickas till kundprofilen i realtid och [Identitetstjänst](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en). **Filtreringen påverkar inte data som skickas till Data Lake för användning i program som Customer Journey Analytics**. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en#filtering-for-profile) | Ej tillämpligt | Omplanerat till 29 mars 2023 |

{style=&quot;table-layout:auto&quot;}

## Korrigeringar i Adobe Analytics

AN-302282; AN-303127; AN-303541; AN-303550; AN-305282; AN-306504; AN-307351; AN-307496; AN-307530; AN-307947; AN-308497; AN-308610; AN-308777; AN-308994; AN-309143; AN-309404; AN-309414; AN-309445; AN-309575; AN-309630; AN-309658; AN-309690; AN-309742; AN-309861; AN-309967; AN-309973; AN-310059; AN-310132; AN-310168; AN-310238; AN-310241; AN-310301; AN-310318; AN-310324; AN-310335; AN-310338; AN-310460; AN-310500; AN-310684; AN-310690; AN-311010; AN-311022; AN-311043; AN-311125; AN-311250; AN-311370; AN-311458;

## Viktiga meddelanden för Adobe Analytics-administratörer

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **Uppdatera till enhetssökningar på grund av Google klienttips** | 27 februari 2023 | Användningen av klienttips, som planerades till den 16 februari 2023, sköts upp för att bättre säkerställa kvaliteten på enhetssökningar med hjälp av tips. Vi fortsätter med den första fasen av releasen för stöd av kundtips den 27 februari 2023. Om allt går bra fortsätter vi till den andra och sista fasen av releasen torsdagen den 2 mars 2023. [Läs mer](/help/technotes/client-hints.md) |
| **Tillgänglighet för Analytics Source Connector** | 15 februari 2023 | Den 28 februari 2023 kommer Analytics Source Connector att vara tillgänglig i Adobe Experience Platform nya datacenter i Kanada. |
| **Automatisk migrering till arkitekturen för klassificeringsuppsättning** | 8 februari 2023 | Under de kommande månaderna planerar Adobe att migrera alla klassificeringar i alla organisationer till den senaste klassificeringsarkitekturen. De sista kunderna som migrerar beräknas inträffa i maj 2023. Ingen kundåtgärd krävs, och ingen driftstopp förväntas. Den nya arkitekturen har många fördelar, bland annat:<ul><li>Betydande minskning av bearbetningstiden (72 timmar → 24 timmar)</li><li>Möjligheten att använda [Klassificeringsuppsättningar](/help/components/classifications/sets/overview.md) UI</li><li>Alternativet att använda klassificeringsdata i Adobe Experience Platform i framtiden via [Adobe Analytics källanslutning för klassificeringsdata](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)</li></ul>Observera följande ändringar som kan påverka organisationens arbetsflöde:<ul><li>Vid användning av webbläsare eller FTP-import, &#39;[!UICONTROL Overwrite on conflict]&#39; är alltid aktiverat.</li><li>När du använder en webbläsare eller FTP-import stöds inte längre alternativet att exportera direkt efter importen.</li><li>API:t för Analytics 2.0 `GetDimensions` slutpunkten returnerar nu strängidentifierare för klassificeringar i stället för numeriska identifierare. Numeriska identifierare kan fortfarande användas, men Adobe rekommenderar att du använder de nya strängidentifierarna där det är möjligt. Numeriska identifierare kan hämtas med `?expansion=hidden` frågesträngsparameter.</li></ul>Kontakta Adobe kundtjänst om du vill ha ett mer specifikt migreringsschema för din organisation, eller har frågor om migreringen. [Läs mer](/help/components/classifications/sets/overview.md) |

{style=&quot;table-layout:auto&quot;}

## EOL-meddelanden (End-of-life)

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **EOL för vissa schemaläggningsfunktioner för rapporter och analyser samt Report Builder** | 9 februari 2023 | Följande schemaläggningsfunktioner upphörde den 31 januari 2023:<ul><li>Alternativet &quot;end after x instances&quot; för timuppgifter i Report Builder</li><li>Möjlighet att schemalägga nya rapporter och ladda ned dataextraheringar i Reports and Analytics</li></ul><p>**Anteckning**: Vi avslutade dessa funktioner i april 2022 men drog tillbaka ändringen. Vi skickade också ett meddelande om att dessa funktioner tillfälligt återställdes och att de skulle avslutas den 31 januari 2023. |
| **EOL för [!UICONTROL Publishing Lists] funktion** | 29 september 2022 | Som en del av ledningscentralen för rapporter och analyser är publiceringslistor avsedda att nå slutet av livscykeln i **December 2023**. Du kommer inte att kunna skapa nya eller använda befintliga publiceringslistor för att skicka eller schemalägga Analysis Workspace-projekt. |
| **EOL för Data Workbench** | 14 september 2022 | Adobe har för avsikt att göra Datan Workbench gällande **31 december 2023**. Se [Datans Workbench meddelande om att livscykeln upphör](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html) för mer information. Kontakta din organisations kontoansvarige på Adobe om du har frågor. |
| **EOL för[!DNL Reports & Analytics]** | 4 januari 2022 | Effektivt **31 december 2023** kommer Adobe att upphöra med sin verksamhet [!DNL Reports & Analytics] och tillhörande rapporter och funktioner. Rapporterna, visualiseringarna och den underliggande tekniken som ligger till grund för [!DNL Reports & Analytics] inte längre uppfyller Adobe teknikstandarder. Mest [!DNL Reports & Analytics] funktioner finns i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Sedan Analysis Workspace släpptes 2015 har [!DNL Reports & Analytics] funktionaliteten och funktionerna har flyttats till Analysis Workspace och ett tröskelvärde för arbetsflödets paritet har uppnåtts. [Detta meddelande](https://spark.adobe.com/page/6WnF8JK6IRDhf/) förklarar processen för att avsluta livscykeln. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

De senaste uppdateringarna av AppMeasurement-versioner (version 2.23.0) finns i [Versionsinformation om AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Relaterade resurser

* [Information om föregående version för 2022](/help/release-notes/2022.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html)
