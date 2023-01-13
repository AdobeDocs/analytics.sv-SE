---
title: Versionsinformation om den senaste analysen
description: Se versionsinformationen för Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: b6c22fdeab68c55f145ed72002532ed87c06a258
workflow-type: tm+mt
source-wordcount: '1461'
ht-degree: 2%

---

# Versionsinformation för Adobe Analytics

**Senaste uppdatering**: 12 januari 2023

Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner i Adobe Analytics

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Mappar på arbetsytan** | Med mappar kan du ordna och kategorisera dina projekt så att de blir lättare att hämta och komma åt. Dessutom har en delad **[!UICONTROL Company]** kan administratörer enkelt skapa och dela innehåll med alla Workspace-användare. [Läs mer](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.html) | Ej tillämpligt | 11 januari 2023 |
| **Standardstartsida** | The [ny landningssida](/help/analyze/landing.md) som introducerades tidigare 2022 kommer att bli standardupplevelsen för alla användare på **11 januari 2023**. Den gamla landningssidan kommer att bli inaktuell och alla kommer att behöva använda den nya upplevelsen. | Ej tillämpligt | 11 januari 2023 |
| **Project Manager-sidan är inaktuell** | I och med lanseringen av den nya landningssidan har vi ersatt **[!UICONTROL Project Manager]** enligt **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Components]**. Den nya landningssidan har alla funktioner som finns på den gamla Project Manager-sidan och mycket mer. Läs mer | Ej tillämpligt | 11 januari 2023 |
| **Spara nya projekt automatiskt** | Analysis Workspace sparar nu automatiskt nya projekt. Om du av någon anledning oväntat förlorar åtkomsten till ett nyligen skapat projekt innan du sparar det manuellt, är en återställningsversion av ditt projekt nu tillgänglig. Tidigare sparades projekt bara automatiskt efter att de först sparats manuellt. [Läs mer](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md) | Ej tillämpligt | 11 januari 2023 |
| **Förbättrade användarinställningar** | Nu kan du konfigurera ytterligare inställningar på användarnivå (i [!UICONTROL Components] > [!UICONTROL Preferences]). När du anger användarinställningar spänner markeringarna över flera projekt, tabeller och visualiseringar. Sidan Inställningar innehåller nu följande nya flikar som alla innehåller många nya konfigurationsalternativ:<ul><li>Frihandstabell</li><li>Visualiseringar</li></ul>Fler inställningar finns nu på **[!UICONTROL General]** och **[!UICONTROL Project]** -tabbar.<p>Tidigare var många av dessa inställningar endast konfigurerbara för enskilda projekt, tabeller och visualiseringar. [Läs mer](/help/analyze/analysis-workspace/user-preferences.md) | Ej tillämpligt | 11 januari 2023 |

{style=&quot;table-layout:auto&quot;}

## Korrigeringar i Adobe Analytics

AN-282634; AN-289684; AN-299597; AN-299630; AN-300128; AN-301633; AN-301683; AN-301745; AN-302238; AN-302521; AN-302601; AN-303325; AN-303363; AN-303867; AN-304120; AN-304185; AN-304221; AN-304222; AN-304510; AN-304591; AN-304872; AN-305151; AN-305159; AN-305233; AN-305235; AN-305241; AN-305250; AN-305274; AN-305292; AN-305311; AN-305314; AN-305331; AN-305335; AN-305348; AN-305372; AN-305382; AN-305442; AN-305504; AN-305517; AN-305572; AN-305584; AN-305588; AN-305612; AN-305640; AN-305663; AN-305718; AN-305723; AN-305767; AN-305769; AN-305703; AN-305711; AN-305775; AN-305883; AN-305886; AN-305882; AN-305886; AN-305916; AN-305969; AN-305997; AN-306052; AN-306088; AN-306199; AN-306214; AN-306233; AN-306251; AN-306348; AN-306372; AN-306390; AN-306413; AN-306430; AN-306514; AN-306578; AN-306612; AN-306886; AN-306893; AN-306905; AN-306984; AN-306989; AN-307038; AN-307061; AN-307062; AN-307176; AN-307209; AN-307233; AN-307257; AN-307280; AN-307292; AN-307293; AN-307318; AN-307319; AN-307320; AN-307325; AN-307368; AN-307381; AN-307403; AN-307461; AN-307480; AN-307650; AN-307767; AN-307790; AN-307813; AN-307833; AN-307835; AN-307867; AN-307899; AN-307907; AN-307934; AN-307991; AN-308031; AN-308057; AN-308240; AN-308242; AN-308302; AN-308363; AN-308373; AN-308450; AN-308591; AN-308673; AN-308725; AN-309171;

## Viktiga meddelanden för Adobe Analytics-administratörer

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **Pausa schemalagda rapporter i rapporter och analyser** | 6 januari 2023 | Detta är en påminnelse om att Adobe kommer att ta bort dessa funktioner på **31 jan 2023**. Observera att förfallotiden för både rapporter och dataextrakt fortsätter att vara begränsad till nio månader. leverans av rapport och dataextrahering pausas vid periodens slut om inte schemat återaktiveras.<p>För att upprepa detta kommer dessa funktioner att bli inaktuella den 31 januari 2023. Före detta datum måste du migrera din schemalagda rapportering till någon av de andra mekanismer som är tillgängliga i Adobe Analytics. Om du har ytterligare frågor eller support kan du kontakta Adobe kundtjänst. [Läs mer](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Pausa schemalagda aktiviteter i Report Builder** | 6 januari 2023 | På **31 januari 2023** kommer Adobe att införa förändringar i schemalagda aktiviteter i Report Builder som en del av våra insatser för optimering av prestanda och leverans. Dessa ändringar inkluderar borttagning av möjligheten att ha schemalagda leveranser &quot;end after x instances&quot;.<p>Du kan fortsätta att schemalägga aktiviteter per Report Builder och låta dem sluta efter högst 99 tillfällen. Observera att återställningen endast gäller timuppgifter. &quot;end after x instances&quot; förblir otillgängligt för alla andra leveransintervall (dag, vecka, månad och år). Observera att detta alternativ kommer att vara inaktuellt den 31 januari 2023. Om du har frågor eller support kan du kontakta Adobe kundtjänst. [Läs mer](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **Förbättrad mappning av IP-till-geopositionering** | 4 januari 2023 | Vår leverantör av IP-sökningar, Digital Element, uppgraderar till en ny förbättrad datamängd (NetAcuity Pulse) för IP-till-geopositioneringsmappning. Ursprungligen planerad för oktober 2022 kommer Adobe Analytics att anta denna nya datauppsättning den **11 januari 2023**. Den nya databasen kommer att vara mer exakt än tidigare versioner. Vissa IP-till-geo-mappningar kommer att ändras/förbättras när den nya databasen antas.<p>Alla Adobe Analytics-verktyg (Analysis Workspace, Rapporter och analyser, Rapporterings-API, Data warehouse, LiveStream, Analytics Data Feeds och så vidare) utnyttjar automatiskt de nya förbättrade mappningarna. Dataflödenas format ändras inte. CJA-data som tillhandahålls via Analytics Source Connector drar automatiskt nytta av de nya mappningarna. |
| **Uppdatera till ny NetAcuity-databas** | 4 januari 2023 | Den här uppdateringen, som ursprungligen planerades den 5 oktober 2022, kommer nu att äga rum den **11 januari 2023**. Transportföretagsrelaterad information lagrad i `carrier` i Adobe Analytics Data warehouse och Analytics Data Feeds kommer att ändras. Historiskt sett har dataformatet i den kolumnen `<domain>:<ISP>`. Adobe har en intern uppslagstabell för att mappa dessa `<domain>:<ISP>` värden i företagsnamn för rapportering i Adobe Analytics rapporteringsverktyg (Analysis Workspace, Rapporter och analyser, Rapporterings-API, Data warehouse, LiveStream osv.). Uppslagsfilen (`carrier.tsv`) ingår också i datafeeds så att du kan använda samma mappningar.<p>Den här uppdateringen förbättrar våra datamappningar med hjälp av en mer korrekt transportföretagsdatabas från NetAcuity. Formatet på data i transportföretagskolumnen i Datafeeds ändras under utvecklingen. I stället för `<domain>:<ISP>`, kommer det att innehålla ett transportföretagsnamn. Adobe kommer att fortsätta att använda uppslagstabellen för att upprätthålla så mycket kontinuitet som möjligt med tidigare rapportering. Rapporteringsverktyg där sökningarna tillämpas av Adobe (Analysis Workspace, Rapporter och analyser, rapporterings-API, data warehouse, LiveStream osv.) kan dra nytta av mer exakta mappningar. Vissa mappningar - särskilt för internationella domäner och Internet-leverantörer - kommer att förändras mer än andra när Adobe antar den nya databasen. Dataflödets sökningsfil för bärare (`carrier.tsv`) behåller de gamla mappningarna och lägger till de nya mappningarna.<p>Analyskällans koppling för analys mappar för närvarande inte transportföretagsfältet, vilket innebär att det inte finns några rapporter för transportföretag i Experience Platform, CJA och så vidare. Användning av den nya databasen för transportörer kommer därför inte att påverka någonting i Experience Platform som baseras på data från Analytics Source Connector. |
| **Uppdaterade riktlinjer för trafikspikes-meddelanden** | 18 november 2022 | Tidigare riktlinjer baserades strikt på träffvolymer. The [nya riktlinjer](https://experienceleague.adobe.com/docs/analytics/admin/traffic-management/traffic-lead-time.html?lang=en) baseras på en kombination av rapportsvitens storlek och procentuell ökning. |
| **Uppdatera till enhetssökningar på grund av Google klienttips** | 6 januari 2023 | Användningen av klienttips i enhetssökning börjar på **25 januari 2023**. <p> <p>Från och med oktober 2022 är det möjligt att samla in klienttips med antingen Web SDK- eller AppMeasurement JavaScript-biblioteken. Men klienttips kommer inte att införlivas i enhetssökning förrän i januari 2023. Då kommer Adobe att börja använda klienttips förutom användaragenten när vissa enhetsuppgifter hämtas från Chromium-webbläsare, som Google Chrome och Microsoft Edge. Detta är ett svar på Google plan att gradvis minska informationen som presenteras från användaragentsträngen i stället för data som skickas via klienttips. <p> <p>Som en del av den här ändringen använder Adobe enhetskartan för alla enhetssökningar som är relaterade till användaragenten. [Läs mer](/help/technotes/client-hints.md) |

{style=&quot;table-layout:auto&quot;}

## Information om sista giltighetsdag

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
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
