---
title: Versionsinformation om den senaste analysen
description: Se versionsinformationen för Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: bedda6ba1f3022562976ada7e73a9514947b5071
workflow-type: tm+mt
source-wordcount: '1097'
ht-degree: 2%

---

# Aktuell versionsinformation för Adobe Analytics (juli 2022)

**Senaste uppdatering**: 13 juli 2022

>[!NOTE]
>
>Den här sidan innehåller information om förhandsversioner och kan komma att ändras.

## Relaterade resurser

* [Information om föregående version för 2022](/help/release-notes/2022.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html)

## Nya funktioner i Adobe Analytics

| Funktion | Beskrivning | [Måldatum](releases.md) |
| ----------- | ---------- | ------- |
| Stöd för marknadsföring av variabler i XDM för Edge Collection | Gör det möjligt för kunder att samla in data via Experience Edge/Web SDK att använda XDM för att ange de olika värdena för Merchandising-variabler (eVars). [Läs mer](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/evar-merchandising.html?lang=en) | 29 juni 2022 |

{style=&quot;table-layout:auto&quot;}

## Korrigeringar i Adobe Analytics

* Korrigerade vissa segmentkonverteringsfel. (AN-291262, AN-294092)

**Korrigeringar för enskilda kunder**:

AN-280192; AN-281628; AN-287022; AN-287104; AN-287876; AN-288802; AN-288457; AN-288779; AN-288799; AN-289198; AN-289852; AN-289931; AN-290162; AN-290213; AN-291059; AN-291090; AN-291270; AN-294091; AN-294135; AN-294152; AN-294158; AN-294285; AN-294317; AN-294404; AN-294531; AN-294769; AN-294984; AN-295172; AN-295211; AN-295224; AN-295413; AN-295440; AN-295465; AN-295499; AN-295516;

## Viktiga meddelanden för Adobe Analytics-administratörer

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **Ny domän för systemgenererade e-postmeddelanden** | 13 juli 2022 | På **18 maj 2022**, har Adobe ändrat avsändarens domän för e-post från projekt, aviseringar och varningsmeddelanden på arbetsytan från `noreply@omniture.com` till `noreply@adobe.com`. Lägg till det här nya e-postmeddelandet i tillåtelselista om din organisation bara tillåter vissa avsändare. |
| **Uppdatera till ny NetAcuity-databas** | 11 juli 2022 | **Från och med oktober 2022**, företagsrelaterad information lagrad i `carrier` i Adobe Analytics Data warehouse och Analytics kommer dataflödena att ändras. Historiskt sett har dataformatet i den kolumnen `<domain>:<ISP>`. Adobe har en intern uppslagstabell för att mappa dessa `<domain>:<ISP>` värden i transportföretagsnamn för rapportering i Adobe Analytics rapporteringsverktyg (Analysis Workspace, Rapporter och analyser, API för rapportering, data warehouse, LiveStream osv.) Uppslagsfilen (operator.tsv) tillhandahålls också med dataflöden så att datamatningskunder kan använda samma mappningar.<p>Den här uppdateringen förbättrar våra datamappningar med hjälp av en mer korrekt transportföretagsdatabas från NetAcuity. Formatet på data i transportföretagskolumnen i dataflöden ändras under utvecklingen. I stället för `<domain>:<ISP>`, kommer det att innehålla ett transportföretagsnamn. Adobe kommer att fortsätta att använda uppslagstabellen för att upprätthålla så mycket kontinuitet som möjligt med tidigare rapportering. Rapporteringsverktyg där sökningarna tillämpas av Adobe (Analysis Workspace, Rapporter och analyser, rapporterings-API, data warehouse, LiveStream osv.) kan dra nytta av mer exakta mappningar. Vissa mappningar - särskilt för internationella domäner och Internet-leverantörer - kommer att förändras mer än andra när vi antar den nya databasen. Datafeeds-transportörens sökningsfil (operator.tsv) bevarar de gamla mappningarna och lägger till de nya mappningarna.<p>Analyskällans koppling för analys mappar för närvarande inte transportföretagsfältet, så transportörrapportering är för närvarande inte tillgänglig i AEP, CJA osv. Användning av den nya bärardatabasen kommer därför inte att påverka något i AEP som baseras på data från Analytics Source Connector. |
| **Förbättrad mappning av IP-till-geopositionering** | 11 juli 2022 | Vår leverantör av IP-sökningar, Digital Element, uppgraderar till en ny förbättrad datamängd (NetAcuity Pulse) för IP-till-geopositioneringsmappning. Adobe Analytics kommer att anta den nya datauppsättningen i **Oktober 2022** tidsram. Den nya databasen kommer att vara mer exakt än tidigare versioner. Vissa IP-till-geo-mappningar kommer att ändras/förbättras när den nya databasen antas.<p>Alla Adobe Analytics-verktyg (Analysis Workspace, Rapporter och analyser, API för rapportering, data warehouse, LiveStream, dataflöden osv.) utnyttjar automatiskt de nya förbättrade mappningarna. Dataflödenas format ändras inte. CJA-data som tillhandahålls via Analytics Source Connector drar automatiskt nytta av de nya mappningarna. |
| **Pausa schemalagda rapporter i rapporter och analyser** | 8 juni 2022 | Den 21 april 2022 meddelade vi att flera funktioner som är specifika för schemalagda rapporter skulle tas bort som förberedelse inför det tidigare utkomna livets slut för rapporter och analyser. Bland dessa funktioner fanns möjligheten att schemalägga nya rapporter och nya datautdrag.<p>Som svar på kundförfrågningar om förlängning och för att underlätta övergången från Reports and Analytics har vi beslutat att utöka åtkomsten till dessa funktioner tills **31 jan 2023**. Observera att förfallotiden för både rapporter och dataextrakt fortsätter att vara begränsad till nio månader. leverans av rapport och dataextrahering pausas vid periodens slut om inte schemat återaktiveras.<p>För att upprepa detta kommer dessa funktioner att bli inaktuella den 31 januari 2023. Före detta datum måste du migrera din schemalagda rapportering till någon av de andra mekanismer som är tillgängliga i Adobe Analytics. Om du har ytterligare frågor eller support kan du kontakta Adobe kundtjänst. [Läs mer](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Pausa schemalagda aktiviteter i Report Builder** | 8 juni 2022 | Den 21 april 2022 introducerade vi förändringar av schemalagda arbetsuppgifter i Report Builder som en del av våra insatser för optimering av prestanda och leverans. Dessa ändringar inkluderar borttagning av möjligheten att ha schemalagda leveranser som &quot;upphör efter x förekomster&quot;. Som svar på flera kundförfrågningar som kräver mer tid att utforska och implementera alternativ har vi beslutat att återställa detta alternativ i begränsad omfattning tills **31 jan 2023**.<p>Du kan fortsätta att schemalägga aktiviteter per Report Builder och låta dem sluta efter högst 99 tillfällen. Observera att återställningen endast gäller timuppgifter. &quot;end after x instances&quot; förblir otillgängligt för alla andra leveransintervall (dag, vecka, månad och år). Observera att detta alternativ kommer att vara inaktuellt den 31 januari 2023. Om du har frågor eller support kan du kontakta Adobe kundtjänst. [Läs mer](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **SFTP-uppgradering** | 9 maj 2022 | Tidigare hade vi meddelat att Adobe skulle uppgradera sina tjänster för SFTP (Secure File Transfer Protocol) i maj 2022 för att ge bättre säkerhet vid filöverföring. Vi har skjutit upp uppgraderingen till **Sommaren 2022**. När den här ändringen görs stöds inte längre vissa SFTP-klientkonfigurationer. Detta påverkar endast data som skickas till eller hämtas från Adobe Analytics med SFTP. FTP-protokollet påverkas inte. För att undvika avbrott i tjänsten bör du se till att dina SFTP-klienter (kod, verktyg, tjänster) följer de detaljerade ändringarna [här](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html). |
| **EOL för[!DNL Reports & Analytics]** | 4 januari 2022 | Effektivt **31 december 2023** kommer Adobe att upphöra med sin verksamhet [!DNL Reports & Analytics] och tillhörande rapporter och funktioner. Rapporterna, visualiseringarna och den underliggande tekniken som ligger till grund för [!DNL Reports & Analytics] inte längre uppfyller Adobe teknikstandarder. Mest [!DNL Reports & Analytics] funktioner finns i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Sedan Analysis Workspace släpptes 2015 har [!DNL Reports & Analytics] funktionaliteten och funktionerna har flyttats till Analysis Workspace och ett tröskelvärde för arbetsflödets paritet har uppnåtts. [Detta meddelande](https://spark.adobe.com/page/6WnF8JK6IRDhf/) förklarar processen för att avsluta livscykeln. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

De senaste uppdateringarna av AppMeasurement-versioner (version 2.2.4) finns i [Versionsinformation om AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=en).

