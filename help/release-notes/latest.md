---
title: Versionsinformation om den senaste analysen
description: Se versionsinformationen för Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 74c347c72394b75cc332ae459b9cbf1f72fa033b
workflow-type: tm+mt
source-wordcount: '1205'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Analytics (september 2022)

**Senaste uppdatering**: 9 september 2022

>[!NOTE]
>
>Den här sidan innehåller förhandsversion av innehåll och kan komma att ändras.

## Relaterade resurser

* [Information om föregående version för 2022](/help/release-notes/2022.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html)

## Nya eller uppdaterade funktioner i Adobe Analytics

| Funktion | Beskrivning | [Måldatum](releases.md) |
| ----------- | ---------- | ------- |
| Visualisering av kombinationsdiagram i arbetsytan | Med kombinationsdiagram kan du jämföra mätvärden enklare och intuitivare i Workspace. [Läs mer](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/combo-charts.html) | 14 september 2022 |

{style=&quot;table-layout:auto&quot;}

## Korrigeringar i Adobe Analytics

* Problem med import och export av klassificeringar har korrigerats. (AN-299267)

**Korrigeringar för enskilda kunder**:

AN-288519; AN-289300; AN-297387; AN-297465; AN-297520; AN-297641; AN-298134; AN-298351; AN-298429; AN-298483; AN-298520; AN-298582; AN-298816; AN-298832; AN-298855; AN-298864; AN-299407; AN-299545; AN-299644; AN-299715

## Viktiga meddelanden för Adobe Analytics-administratörer

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **SFTP-uppgradering** | 9 september 2022 | Tidigare hade vi meddelat att Adobe skulle uppgradera sina tjänster för SFTP (Secure File Transfer Protocol) i september 2022 för att ge bättre säkerhet vid filöverföring. Vi har skjutit upp uppgraderingen till **mitten till slutet av september 2022**. När den här ändringen görs stöds inte längre vissa SFTP-klientkonfigurationer. Detta påverkar endast data som skickas till eller hämtas från Adobe Analytics med SFTP. FTP-protokollet påverkas inte. För att undvika avbrott i tjänsten bör du se till att dina SFTP-klienter (kod, verktyg, tjänster) följer de detaljerade ändringarna [här](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html). |
| **EOL för Data Workbench** | 9 september 2022 | Adobe har för avsikt att upphöra med Datan Workbench som gäller **31 december 2023**. Mer information kommer snart. |
| **Uppdatera till enhetssökningar på grund av Google klienttips** | 9 september 2022 | Från **29 september 2022** kommer Adobe att börja använda klienttips förutom användaragenten när vissa enhetsuppgifter hämtas från Chromium-webbläsare, som Google Chrome och Microsoft Edge. Detta är som svar på Google plan att gradvis minska informationen som presenteras från användaragentsträngen i stället för data som skickas via klienttips. Läs mer om kundtips [här](https://web.dev/user-agent-client-hints/).<p> I oktober kommer både AppMeasurement- och Web SDK-samlingsbiblioteken att ha stöd för insamling av klienttips och konfigurering av huruvida höga entropiklienttips ska samlas in. Som en del av den här ändringen använder Adobe enhetskartan för alla enhetssökningar som är relaterade till användaragenten. Device Atlas används för närvarande bara för mobilträffar. Uppdateringarna kan resultera i små ändringar av enhetsinformation som historiskt härleds från användaragenten - särskilt webbläsare, webbläsartyp, operativsystem, operativsystemtyp och mobil enhet. |
| **Uppdatera till ny NetAcuity-databas** | 9 september 2022 | **Från och med 5 oktober 2022**, företagsrelaterad information lagrad i `carrier` i Adobe Analytics Data warehouse och Analytics Data Feeds kommer att ändras. Historiskt sett har dataformatet i den kolumnen `<domain>:<ISP>`. Adobe har en intern uppslagstabell för att mappa dessa `<domain>:<ISP>` värden i företagsnamn för rapportering i Adobe Analytics rapporteringsverktyg (Analysis Workspace, Rapporter och analyser, API för rapportering, data warehouse, LiveStream osv.). Uppslagsfilen (`carrier.tsv`) ingår också i datafeeds så att du kan använda samma mappningar.<p>Den här uppdateringen förbättrar våra datamappningar med hjälp av en mer korrekt transportföretagsdatabas från NetAcuity. Formatet på data i transportföretagskolumnen i Datafeeds ändras under utvecklingen. I stället för `<domain>:<ISP>`, kommer det att innehålla ett transportföretagsnamn. Adobe kommer att fortsätta att använda uppslagstabellen för att upprätthålla så mycket kontinuitet som möjligt med tidigare rapportering. Rapporteringsverktyg där sökningarna tillämpas av Adobe (Analysis Workspace, Rapporter och analyser, rapporterings-API, data warehouse, LiveStream osv.) kan dra nytta av mer exakta mappningar. Vissa mappningar - särskilt för internationella domäner och Internet-leverantörer - kommer att förändras mer än andra när vi antar den nya databasen. Dataflödets sökningsfil för bärare (`carrier.tsv`) behåller de gamla mappningarna och lägger till de nya mappningarna.<p>Analyskällans koppling för analys mappar för närvarande inte transportföretagsfältet, så transportörrapportering är för närvarande inte tillgänglig i AEP, CJA osv. Användning av den nya bärardatabasen kommer därför inte att påverka något i AEP som baseras på data från Analytics Source Connector. |
| **Förbättrad mappning av IP-till-geopositionering** | 9 september 2022 | Vår leverantör av IP-sökningar, Digital Element, uppgraderar till en ny förbättrad datamängd (NetAcuity Pulse) för IP-till-geopositioneringsmappning. Adobe Analytics kommer att anta den nya datauppsättningen den **5 oktober 2022**. Den nya databasen kommer att vara mer exakt än tidigare versioner. Vissa IP-till-geo-mappningar kommer att ändras/förbättras när den nya databasen antas.<p>Alla Adobe Analytics-verktyg (Analysis Workspace, Rapporter och analyser, API för rapportering, data warehouse, LiveStream, dataflöden osv.) utnyttjar automatiskt de nya förbättrade mappningarna. Dataflödenas format ändras inte. CJA-data som tillhandahålls via Analytics Source Connector drar automatiskt nytta av de nya mappningarna. |
| **Pausa schemalagda rapporter i rapporter och analyser** | 8 juni 2022 | Den 21 april 2022 meddelade vi att flera funktioner som är specifika för schemalagda rapporter skulle tas bort som förberedelse inför det tidigare utkomna livets slut för rapporter och analyser. Bland dessa funktioner fanns möjligheten att schemalägga nya rapporter och nya datautdrag.<p>Som svar på kundförfrågningar om förlängning och för att underlätta övergången från Reports and Analytics har vi beslutat att utöka åtkomsten till dessa funktioner tills **31 jan 2023**. Observera att förfallotiden för både rapporter och dataextrakt fortsätter att vara begränsad till nio månader. leverans av rapport och dataextrahering pausas vid periodens slut om inte schemat återaktiveras.<p>För att upprepa detta kommer dessa funktioner att bli inaktuella den 31 januari 2023. Före detta datum måste du migrera din schemalagda rapportering till någon av de andra mekanismer som är tillgängliga i Adobe Analytics. Om du har ytterligare frågor eller support kan du kontakta Adobe kundtjänst. [Läs mer](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Pausa schemalagda aktiviteter i Report Builder** | 8 juni 2022 | Den 21 april 2022 introducerade vi förändringar av schemalagda arbetsuppgifter i Report Builder som en del av våra insatser för optimering av prestanda och leverans. Dessa ändringar inkluderar borttagning av möjligheten att ha schemalagda leveranser som &quot;upphör efter x förekomster&quot;. Som svar på flera kundförfrågningar som kräver mer tid att utforska och implementera alternativ har vi beslutat att återställa detta alternativ i begränsad omfattning tills **31 jan 2023**.<p>Du kan fortsätta att schemalägga aktiviteter per Report Builder och låta dem sluta efter högst 99 tillfällen. Observera att återställningen endast gäller timuppgifter. &quot;end after x instances&quot; förblir otillgängligt för alla andra leveransintervall (dag, vecka, månad och år). Observera att detta alternativ kommer att vara inaktuellt den 31 januari 2023. Om du har frågor eller support kan du kontakta Adobe kundtjänst. [Läs mer](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **EOL för[!DNL Reports & Analytics]** | 4 januari 2022 | Effektivt **31 december 2023** kommer Adobe att upphöra med sin verksamhet [!DNL Reports & Analytics] och tillhörande rapporter och funktioner. Rapporterna, visualiseringarna och den underliggande tekniken som ligger till grund för [!DNL Reports & Analytics] inte längre uppfyller Adobe teknikstandarder. Mest [!DNL Reports & Analytics] funktioner finns i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Sedan Analysis Workspace släpptes 2015 har [!DNL Reports & Analytics] funktionaliteten och funktionerna har flyttats till Analysis Workspace och ett tröskelvärde för arbetsflödets paritet har uppnåtts. [Detta meddelande](https://spark.adobe.com/page/6WnF8JK6IRDhf/) förklarar processen för att avsluta livscykeln. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

De senaste uppdateringarna av AppMeasurement-versioner (version 2.2.4) finns i [Versionsinformation om AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=en).

