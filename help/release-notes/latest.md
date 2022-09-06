---
title: Versionsinformation om den senaste analysen
description: Se versionsinformationen för Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: fe00b4d51d7bbfecf12c351530729e144088e248
workflow-type: tm+mt
source-wordcount: '1285'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Analytics (augusti 2022)

**Senaste uppdatering**: 6 september 2022

## Relaterade resurser

* [Information om föregående version för 2022](/help/release-notes/2022.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html)

## Nya eller uppdaterade funktioner i Adobe Analytics

| Funktion | Beskrivning | [Måldatum](releases.md) |
| ----------- | ---------- | ------- |
| Stöd för listvariabler i XDM för Edge Collection | Gör det möjligt för kunder att samla in data via Experience Edge/Web SDK att använda XDM för att ange innehållet i List Variable. [Läs mer](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/list.html?lang=en#list-variables-using-the-web-sdk) | 18 augusti 2022 |
| Användning av SKU-fält i XDM för Edge Collection när produktsträngsvariabler anges | Gör det möjligt för kunder att samla in data via Experience Edge/Web SDK att använda SKU-värdet för att ställa in produktfältet i variabeln products. [Läs mer](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html?lang=en#products-using-the-web-sdk) | 18 augusti 2022 |

{style=&quot;table-layout:auto&quot;}

## Korrigeringar i Adobe Analytics

* Korrigerade flera datafeedrelaterade problem. (AN-297264, AN-297295, AN-297449)

**Korrigeringar för enskilda kunder**:

AN-274281; AN-280956; AN-285670; AN-288176; AN-289221; AN-289665; AN-289768; AN-294632; AN-294970; AN-295078; AN-295233; AN-295482; AN-295549; AN-295633; AN-295712; AN-295749; AN-295963; AN-295977; AN-296094; AN-296153; AN-296167; AN-296177; AN-296297; AN-296383; AN-296394; AN-296414; AN-296431; AN-296459; AN-296486; AN-296510; AN-296514; AN-296540; AN-296734; AN-296840; AN-296841; AN-296977; AN-296987; AN-297002; AN-297141; AN-297158; AN-297267; AN-297396; AN-297397; AN-297522; AN-297704; AN-297705; AN-297829; AN-297895;

## Viktiga meddelanden för Adobe Analytics-administratörer

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **EOL för Data Workbench** | 6 september 2022 | Adobe har för avsikt att upphöra med Datan Workbench som gäller **31 december 2023**. Mer information kommer snart. |
| **SFTP-uppgradering** | 6 september 2022 | Tidigare hade vi meddelat att Adobe skulle uppgradera sina tjänster för SFTP (Secure File Transfer Protocol) i september 2022 för att ge bättre säkerhet vid filöverföring. Vi har skjutit upp uppgraderingen till **TBD**. När den här ändringen görs stöds inte längre vissa SFTP-klientkonfigurationer. Detta påverkar endast data som skickas till eller hämtas från Adobe Analytics med SFTP. FTP-protokollet påverkas inte. För att undvika avbrott i tjänsten bör du se till att dina SFTP-klienter (kod, verktyg, tjänster) följer de detaljerade ändringarna [här](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html). |
| **Uppdatera till enhetssökningar på grund av Google klienttips** | 19 augusti 2022 | Startar i **Oktober 2022** kommer Adobe att börja använda klienttips förutom användaragenten när vissa enhetsuppgifter hämtas från Chromium-webbläsare, som Google Chrome och Microsoft Edge. Detta är som svar på Google plan att gradvis minska informationen som presenteras från användaragentsträngen i stället för data som skickas via klienttips. Läs mer om kundtips [här](https://web.dev/user-agent-client-hints/).<p> I oktober kommer både AppMeasurement- och Web SDK-samlingsbiblioteken att ha stöd för insamling av klienttips och konfigurering av huruvida höga entropiklienttips ska samlas in. Som en del av den här ändringen använder Adobe enhetskartan för alla enhetssökningar som är relaterade till användaragenten. Device Atlas används för närvarande bara för mobilträffar. Uppdateringarna kan resultera i små ändringar av enhetsinformation som historiskt härleds från användaragenten - särskilt webbläsare, webbläsartyp, operativsystem, operativsystemtyp och mobil enhet. |
| **Uppdatera till ny NetAcuity-databas** | 11 juli 2022 | **Från och med oktober 2022**, företagsrelaterad information lagrad i `carrier` i Adobe Analytics Data warehouse och Analytics Data Feeds kommer att ändras. Historiskt sett har dataformatet i den kolumnen `<domain>:<ISP>`. Adobe har en intern uppslagstabell för att mappa dessa `<domain>:<ISP>` värden i företagsnamn för rapportering i Adobe Analytics rapporteringsverktyg (Analysis Workspace, Rapporter och analyser, API för rapportering, data warehouse, LiveStream osv.). Uppslagsfilen (`carrier.tsv`) ingår också i datafeeds så att du kan använda samma mappningar.<p>Den här uppdateringen förbättrar våra datamappningar med hjälp av en mer korrekt transportföretagsdatabas från NetAcuity. Formatet på data i transportföretagskolumnen i Datafeeds ändras under utvecklingen. I stället för `<domain>:<ISP>`, kommer det att innehålla ett transportföretagsnamn. Adobe kommer att fortsätta att använda uppslagstabellen för att upprätthålla så mycket kontinuitet som möjligt med tidigare rapportering. Rapporteringsverktyg där sökningarna tillämpas av Adobe (Analysis Workspace, Rapporter och analyser, rapporterings-API, data warehouse, LiveStream osv.) kan dra nytta av mer exakta mappningar. Vissa mappningar - särskilt för internationella domäner och Internet-leverantörer - kommer att förändras mer än andra när vi antar den nya databasen. Dataflödets sökningsfil för bärare (`carrier.tsv`) behåller de gamla mappningarna och lägger till de nya mappningarna.<p>Analyskällans koppling för analys mappar för närvarande inte transportföretagsfältet, så transportörrapportering är för närvarande inte tillgänglig i AEP, CJA osv. Användning av den nya bärardatabasen kommer därför inte att påverka något i AEP som baseras på data från Analytics Source Connector. |
| **Förbättrad mappning av IP-till-geopositionering** | 11 juli 2022 | Vår leverantör av IP-sökningar, Digital Element, uppgraderar till en ny förbättrad datamängd (NetAcuity Pulse) för IP-till-geopositioneringsmappning. Adobe Analytics kommer att anta den nya datauppsättningen i **Oktober 2022** tidsram. Den nya databasen kommer att vara mer exakt än tidigare versioner. Vissa IP-till-geo-mappningar kommer att ändras/förbättras när den nya databasen antas.<p>Alla Adobe Analytics-verktyg (Analysis Workspace, Rapporter och analyser, API för rapportering, data warehouse, LiveStream, dataflöden osv.) utnyttjar automatiskt de nya förbättrade mappningarna. Dataflödenas format ändras inte. CJA-data som tillhandahålls via Analytics Source Connector drar automatiskt nytta av de nya mappningarna. |
| **Pausa schemalagda rapporter i rapporter och analyser** | 8 juni 2022 | Den 21 april 2022 meddelade vi att flera funktioner som är specifika för schemalagda rapporter skulle tas bort som förberedelse inför det tidigare utkomna livets slut för rapporter och analyser. Bland dessa funktioner fanns möjligheten att schemalägga nya rapporter och nya datautdrag.<p>Som svar på kundförfrågningar om förlängning och för att underlätta övergången från Reports and Analytics har vi beslutat att utöka åtkomsten till dessa funktioner tills **31 jan 2023**. Observera att förfallotiden för både rapporter och dataextrakt fortsätter att vara begränsad till nio månader. leverans av rapport och dataextrahering pausas vid periodens slut om inte schemat återaktiveras.<p>För att upprepa detta kommer dessa funktioner att bli inaktuella den 31 januari 2023. Före detta datum måste du migrera din schemalagda rapportering till någon av de andra mekanismer som är tillgängliga i Adobe Analytics. Om du har ytterligare frågor eller support kan du kontakta Adobe kundtjänst. [Läs mer](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Pausa schemalagda aktiviteter i Report Builder** | 8 juni 2022 | Den 21 april 2022 introducerade vi förändringar av schemalagda arbetsuppgifter i Report Builder som en del av våra insatser för optimering av prestanda och leverans. Dessa ändringar inkluderar borttagning av möjligheten att ha schemalagda leveranser som &quot;upphör efter x förekomster&quot;. Som svar på flera kundförfrågningar som kräver mer tid att utforska och implementera alternativ har vi beslutat att återställa detta alternativ i begränsad omfattning tills **31 jan 2023**.<p>Du kan fortsätta att schemalägga aktiviteter per Report Builder och låta dem sluta efter högst 99 tillfällen. Observera att återställningen endast gäller timuppgifter. &quot;end after x instances&quot; förblir otillgängligt för alla andra leveransintervall (dag, vecka, månad och år). Observera att detta alternativ kommer att vara inaktuellt den 31 januari 2023. Om du har frågor eller support kan du kontakta Adobe kundtjänst. [Läs mer](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **EOL för[!DNL Reports & Analytics]** | 4 januari 2022 | Effektivt **31 december 2023** kommer Adobe att upphöra med sin verksamhet [!DNL Reports & Analytics] och tillhörande rapporter och funktioner. Rapporterna, visualiseringarna och den underliggande tekniken som ligger till grund för [!DNL Reports & Analytics] inte längre uppfyller Adobe teknikstandarder. Mest [!DNL Reports & Analytics] funktioner finns i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Sedan Analysis Workspace släpptes 2015 har [!DNL Reports & Analytics] funktionaliteten och funktionerna har flyttats till Analysis Workspace och ett tröskelvärde för arbetsflödets paritet har uppnåtts. [Detta meddelande](https://spark.adobe.com/page/6WnF8JK6IRDhf/) förklarar processen för att avsluta livscykeln. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

De senaste uppdateringarna av AppMeasurement-versioner (version 2.2.4) finns i [Versionsinformation om AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=en).

