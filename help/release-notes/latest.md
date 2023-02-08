---
title: Versionsinformation om den senaste analysen
description: Se versionsinformationen för Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: e7140b78b7b2c6c63cb93f1341581cc83af7b33b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Aktuell versionsinformation för Adobe Analytics (februari 2023)

**Senaste uppdatering**: 2 februari 2023

Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner i Adobe Analytics

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Uppdaterat användargränssnitt för etiketter för datasekretess** | Det uppdaterade gränssnittet effektiviserar processen att skapa, hantera och redigera dataintegritetsetiketter för rapportsvitens komponenter. [Läs mer](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-setup-reportsuite.html?lang=en) | Ej tillämpligt | 8 februari 2023 |
| **Jämförelsedatumintervall i Mobile Scorecards** | Med Mobile Scorecards kan du växla **[!UICONTROL Include comparison dates]** inställning för att visa eller dölja jämförelsedatum. | Ej tillämpligt/ | 8 februari 2023 |
| **Kalenderuppdateringar på arbetsytan** | <ul><li>Datum för ankarpanel: Du kan göra datumintervallets komponenter relativa till panelkalendern. [Läs mer](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#relative-panel-dates)</li><li>Uppdateringar av kalenderformat: Kalenderformaten i hela användargränssnittet har uppgraderats för att ge ett mer konsekvent och lättanvänt arbetsflöde.</li><li>Uppdateringar av kalenderformel: Om du använder relativa datum återspeglar alla kalenderformler början av panelens datumintervall. [Läs mer](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#formula-relative-dates)</li></ul> | Ej tillämpligt | 8 februari 2023 |
| **Rad-/kolumnfiltrering för Adobe Analytics Source Connector-direktuppspelning** | Med Analytics Source Connector i Adobe Experience Platform går det nu att filtrera analysdata som används för att fylla i profiler i [Kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en). Filtrering på radnivå minskar antalet händelser som är associerade med profiler. Kolumnnivåfiltrering minskar detaljrikedomen i själva händelserna och gör att du kan optimera användningen av profilberättiganden. Denna filtrering gäller endast data som skickas till kundprofilen i realtid och [Identitetstjänst](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en). **Filtreringen påverkar inte data som skickas till Data Lake för användning i program som Customer Journey Analytics**. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en#filtering-for-profile) | Ej tillämpligt | 22 februari 2023 |

{style=&quot;table-layout:auto&quot;}

## Korrigeringar i Adobe Analytics

AN-302282; AN-303127; AN-303541; AN-303550; AN-305282; AN-306504; AN-307351; AN-307496; AN-307530; AN-307947; AN-308497; AN-308610; AN-308777; AN-308994; AN-309143; AN-309404; AN-309414; AN-309445; AN-309575; AN-309630; AN-309658; AN-309690; AN-309742; AN-309861; AN-309967; AN-309973; AN-310059; AN-310132; AN-310168; AN-310238; AN-310241; AN-310301; AN-310318; AN-310324; AN-310335; AN-310338; AN-310460; AN-310500; AN-310684; AN-310690; AN-311010; AN-311022; AN-311043; AN-311125; AN-311250; AN-311370; AN-311458;

## Viktiga meddelanden för Adobe Analytics-administratörer

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **Uppdatera till enhetssökningar på grund av Google klienttips** | 25 januari 2023 | Användningen av klienttips i enhetssökning börjar på **16 februari 2023**. <p> <p>Från och med oktober 2022 är det möjligt att samla in klienttips med antingen Web SDK- eller AppMeasurement JavaScript-biblioteken. Men klienttips kommer inte att införlivas i enhetssökning förrän i februari 2023. Då kommer Adobe att börja använda klienttips förutom användaragenten när vissa enhetsuppgifter hämtas från Chromium-webbläsare, som Google Chrome och Microsoft Edge. Detta är ett svar på Google plan att gradvis minska informationen som presenteras från användaragentsträngen i stället för data som skickas via klienttips. <p> <p>Som en del av den här ändringen använder Adobe enhetskartan för alla enhetssökningar som är relaterade till användaragenten. [Läs mer](/help/technotes/client-hints.md) |
| **Pausa schemalagda rapporter i rapporter och analyser** | 6 januari 2023 | Adobe har ersatt dessa funktioner på **31 jan 2023**. Observera att förfallotiden för både rapporter och dataextrakt fortsätter att vara begränsad till nio månader. leverans av rapport och dataextrahering pausas vid periodens slut om inte schemat återaktiveras.<p>Före den 31 januari 2023 var du tvungen att migrera din schemalagda rapportering till en av de andra mekanismer som var tillgängliga i Adobe Analytics. Om du har ytterligare frågor eller support kan du kontakta Adobe kundtjänst. [Läs mer](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Pausa schemalagda aktiviteter i Report Builder** | 6 januari 2023 | På **31 januari 2023** som en del av våra insatser för optimering av prestanda och leverans, lade Adobe ut ändringar av schemalagda arbetsuppgifter i Report Builder. Dessa ändringar inkluderar borttagning av möjligheten att ha schemalagda leveranser som &quot;upphör efter x förekomster&quot;.<p>Du kan fortsätta att schemalägga aktiviteter per Report Builder och låta dem sluta efter högst 99 tillfällen. Observera att återställningen endast gäller timuppgifter. &quot;end after x instances&quot; förblir otillgängligt för alla andra leveransintervall (dag, vecka, månad och år). Om du har frågor eller support kan du kontakta Adobe kundtjänst. [Läs mer](/help/analyze/report-builder/r-arb-scheduled-reports.md) |

{style=&quot;table-layout:auto&quot;}

## Information om sista giltighetsdag

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **EOL för Data Workbench** | 14 september 2022 | Adobe har för avsikt att göra Datan Workbench gällande **31 december 2023**. Se [Datans Workbench meddelande om att livscykeln upphör](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html) för mer information. Kontakta din organisations kontoansvarige på Adobe om du har frågor. |
| **EOL för[!DNL Reports & Analytics]** | 4 januari 2022 | Effektivt **31 december 2023** kommer Adobe att upphöra med sin verksamhet [!DNL Reports & Analytics] och tillhörande rapporter och funktioner. Rapporterna, visualiseringarna och den underliggande tekniken som ligger till grund för [!DNL Reports & Analytics] inte längre uppfyller Adobe teknikstandarder. Mest [!DNL Reports & Analytics] funktioner finns i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Sedan Analysis Workspace släpptes 2015 har [!DNL Reports & Analytics] funktionaliteten och funktionerna har flyttats till Analysis Workspace och ett tröskelvärde för arbetsflödets paritet har uppnåtts. [Detta meddelande](https://spark.adobe.com/page/6WnF8JK6IRDhf/) förklarar processen för att avsluta livscykeln. |
| **EOL för [!UICONTROL Publishing Lists] funktion** | 29 september 2022 | Som en del av ledningscentralen för rapporter och analyser är publiceringslistor avsedda att nå slutet av livscykeln i **December 2023**. Du kommer inte att kunna skapa nya eller använda befintliga publiceringslistor för att skicka eller schemalägga Analysis Workspace-projekt. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

De senaste uppdateringarna av AppMeasurement-versioner (version 2.23.0) finns i [Versionsinformation om AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Relaterade resurser

* [Information om föregående version för 2022](/help/release-notes/2022.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html)
