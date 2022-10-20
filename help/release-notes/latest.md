---
title: Versionsinformation om den senaste analysen
description: Se versionsinformationen för Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 15dcca7a00598db422244d705cb0d6be6ce97c5e
workflow-type: tm+mt
source-wordcount: '1546'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Analytics (oktober 2022)

**Senaste uppdatering**: 19 oktober 2022

Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Relaterade resurser

* [Information om föregående version för 2022](/help/release-notes/2022.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html)

## Nya eller uppdaterade funktioner i Adobe Analytics

| Funktion | Beskrivning | [Måldatum](releases.md) |
| ----------- | ---------- | ------- |
| **[!UICONTROL Key metric summary]** visualisering | The [!UICONTROL Key metric summary] visualisering gör att du kan se hur viktiga mätvärden trendar inom en enda tidsram. Du kan också jämföra mätprestanda över två tidsramar. [Läs mer](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/key-metric.html?lang=en) | Avfasad utrullning från 5 oktober 2022 |
| Nytt **[!UICONTROL Classification sets]** användarupplevelse | Den nya användarupplevelsen ger ett enda gränssnitt för att hantera klassificeringar och regler och ger en bättre överblick över kundägda klassificeringsdata. [Läs mer](https://experienceleague.adobe.com/docs/analytics/components/classifications/sets/overview.html?lang=en) | 5 oktober 2022 |
| Mobilapp: **Anpassade detaljvyer** | Med anpassade detaljvyer kan ni målinrikta er ännu mer om vilken information ni delar med er målgrupp genom att låta dem fokusera på det som är viktigast. Du kan ändra layouten för den detaljvy som är kopplad till varje styrkortsplatta och du kan lägga till text för att bättre förklara vad slutanvändaren kan se i data. [Läs mer](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html?lang=en) | 5 oktober 2022 |
| **Skiftlägesokänsliga multivärdesvariabler** | För skiftlägesokänsliga multivärdesvariabler lagras värdena i `mvvar1` - `mvvar3` i dataflöden inte längre automatiskt sänks. I stället kommer dataflöden (och data som skickas via Analytics Source Connector till Adobe Experience Platform och CJA) att återspegla det ursprungliga fallet som skickades från sidan. | 24 oktober 2022 |

{style=&quot;table-layout:auto&quot;}

## Korrigeringar i Adobe Analytics

AN-298512; AN-300117; AN-301754; AN-301584; AN-301685; AN-301783; AN-301818; AN-301825; AN-301834; AN-301965; AN-302095; AN-302189; AN-302269; AN-302290; AN-302301; AN-302348; AN-302531; AN-302533;


## Viktiga meddelanden för Adobe Analytics-administratörer

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **Uppdatera till enhetssökningar på grund av Google klienttips** | 14 oktober 2022 | Användningen av klienttips i enhetssökning, som ursprungligen planerades till 26 oktober 2022, har skjutits upp till **Januari 2023**. <p> <p>Från och med oktober 2022 är det möjligt att samla in klienttips med antingen Web SDK- eller AppMeasurement JavaScript-biblioteken. Men klienttips kommer inte att införlivas i enhetssökning förrän i januari 2023. Vid det datumet kommer Adobe att börja använda klienttips förutom användaragenten när vissa enhetsuppgifter hämtas för träffar från Chromium-webbläsare, som Google Chrome och Microsoft Edge. Detta är ett svar på Google plan att gradvis minska informationen som presenteras från användaragentsträngen i stället för data som skickas via klienttips. <p> <p>Som en del av den här ändringen använder Adobe enhetskartan för alla enhetssökningar som är relaterade till användaragenten. [Läs mer](/help/technotes/client-hints.md) |
| **Standardstartsida** | 29 september 2022 | The [ny landningssida](/help/analyze/landing.md) som introducerades tidigare i år kommer att bli standardupplevelsen för alla användare i **Januari 2023**. Den aktuella sidan kommer att bli inaktuell och alla kommer att behöva använda den nya upplevelsen. |
| **[!UICONTROL Anomaly detection]autokörningsförhållanden** | 29 september 2022 | Idag [!UICONTROL Anomaly detection] körs automatiskt på alla kolumner i friformstabeller i tidsserier. För att säkerställa att data är tillgängliga för analys och att projekt läses in snabbare kommer Adobe att ändra hur automatisk detektering av avvikelser körs. Startar **26 oktober 2022**, [!UICONTROL Anomaly detection] körs bara automatiskt på den första måttkolumnen i en tabell. Du kan konfigurera kolumninställningar så att avvikelseidentifiering körs på andra kolumner, om det behövs. |
| **Uppdatera till ny NetAcuity-databas** | 26 september 2022 | Denna uppdatering, som ursprungligen planerades till den 5 oktober 2022, har skjutits upp till **Januari 2023**. Transportföretagsrelaterad information lagrad i `carrier` i Adobe Analytics Data warehouse och Analytics Data Feeds kommer att ändras. Historiskt sett har dataformatet i den kolumnen `<domain>:<ISP>`. Adobe har en intern uppslagstabell för att mappa dessa `<domain>:<ISP>` värden i företagsnamn för rapportering i Adobe Analytics rapporteringsverktyg (Analysis Workspace, Rapporter och analyser, API för rapportering, Data warehouse, LiveStream osv.). Uppslagsfilen (`carrier.tsv`) ingår också i datafeeds så att du kan använda samma mappningar.<p>Den här uppdateringen förbättrar våra datamappningar med hjälp av en mer korrekt transportföretagsdatabas från NetAcuity. Formatet på data i transportföretagskolumnen i Datafeeds ändras under utvecklingen. I stället för `<domain>:<ISP>`, kommer det att innehålla ett transportföretagsnamn. Adobe kommer att fortsätta att använda uppslagstabellen för att upprätthålla så mycket kontinuitet som möjligt med tidigare rapportering. Rapporteringsverktyg där sökningarna tillämpas av Adobe (Analysis Workspace, Rapporter och analyser, rapporterings-API, data warehouse, LiveStream osv.) kan dra nytta av mer exakta mappningar. Vissa mappningar - särskilt för internationella domäner och Internet-leverantörer - kommer att förändras mer än andra när Adobe antar den nya databasen. Dataflödets sökningsfil för bärare (`carrier.tsv`) behåller de gamla mappningarna och lägger till de nya mappningarna.<p>Analyskällans koppling för analys mappar för närvarande inte transportföretagsfältet, så det finns för närvarande ingen tillgänglig transportörrapportering i Experience Platform, CJA osv. Användning av den nya databasen för transportörer kommer därför inte att påverka någonting i Experience Platform som baseras på data från Analytics Source Connector. |
| **Förbättrad mappning av IP-till-geopositionering** | 26 september 2022 | Vår leverantör av IP-sökningar, Digital Element, uppgraderar till en ny förbättrad datamängd (NetAcuity Pulse) för IP-till-geopositioneringsmappning. Ursprungligen planerad för oktober 2022 kommer Adobe Analytics att anta denna nya datauppsättning i **Januari 2023**. Den nya databasen kommer att vara mer exakt än tidigare versioner. Vissa IP-till-geo-mappningar kommer att ändras/förbättras när den nya databasen antas.<p>Alla Adobe Analytics-verktyg (Analysis Workspace, Rapporter och analyser, API för rapportering, data warehouse, LiveStream, dataflöden osv.) utnyttjar automatiskt de nya förbättrade mappningarna. Dataflödenas format ändras inte. CJA-data som tillhandahålls via Analytics Source Connector drar automatiskt nytta av de nya mappningarna. |
| **SFTP-uppgradering** | 19 september 2022 | Tidigare hade Adobe meddelat att Adobe skulle uppgradera sina tjänster för SFTP (Secure File Transfer Protocol) i september 2022 för att ge bättre säkerhet vid filöverföring. Adobe utförde uppgraderingen den **20 september 2022**. När den här ändringen utfördes stöds inte längre vissa SFTP-klientkonfigurationer. Detta påverkar endast data som skickas till eller hämtas från Adobe Analytics med SFTP. FTP-protokollet påverkas inte. För att undvika avbrott i tjänsten bör du se till att dina SFTP-klienter (kod, verktyg, tjänster) följer de detaljerade ändringarna [här](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html). |
| **Pausa schemalagda rapporter i rapporter och analyser** | 8 juni 2022 | Den 21 april 2022 meddelade Adobe att ett flertal funktioner som är specifika för schemalagda rapporter skulle tas bort som förberedelse inför det tidigare utkomna livstidsarbetet för rapporter och analyser. Bland dessa funktioner fanns möjligheten att schemalägga nya rapporter och nya datautdrag.<p>Som svar på kundförfrågningar om förlängning och för att underlätta övergången från rapporter och analyser har Adobe beslutat att utöka åtkomsten till dessa funktioner till **31 jan 2023**. Observera att förfallotiden för både rapporter och dataextrakt fortsätter att vara begränsad till nio månader. leverans av rapport och dataextrahering pausas vid periodens slut om inte schemat återaktiveras.<p>För att upprepa detta kommer dessa funktioner att bli inaktuella den 31 januari 2023. Före detta datum måste du migrera din schemalagda rapportering till någon av de andra mekanismer som är tillgängliga i Adobe Analytics. Om du har ytterligare frågor eller support kan du kontakta Adobe kundtjänst. [Läs mer](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Pausa schemalagda aktiviteter i Report Builder** | 8 juni 2022 | Den 21 april 2022 införde Adobe ändringar i schemalagda aktiviteter i Report Builder som en del av våra insatser för optimering av prestanda och leverans. Dessa ändringar inkluderar borttagning av möjligheten att ha schemalagda leveranser som &quot;upphör efter x förekomster&quot;. Som svar på ett flertal kundförfrågningar om mer tid för att utforska och implementera alternativ har Adobe beslutat att återställa detta alternativ på ett begränsat sätt tills **31 jan 2023**.<p>Du kan fortsätta att schemalägga aktiviteter per Report Builder och låta dem sluta efter högst 99 tillfällen. Observera att återställningen endast gäller timuppgifter. &quot;end after x instances&quot; förblir otillgängligt för alla andra leveransintervall (dag, vecka, månad och år). Observera att detta alternativ kommer att vara inaktuellt den 31 januari 2023. Om du har frågor eller support kan du kontakta Adobe kundtjänst. [Läs mer](/help/analyze/report-builder/r-arb-scheduled-reports.md) |

{style=&quot;table-layout:auto&quot;}

## Information om sista giltighetsdag

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **EOL för [!UICONTROL Publishing Lists] funktion** | 29 september 2022 | Som en del av ledningscentralen för rapporter och analyser är publiceringslistor avsedda att nå slutet av livscykeln i **December 2023**. Du kommer inte att kunna skapa nya eller använda befintliga publiceringslistor för att skicka eller schemalägga Analysis Workspace-projekt. [Läs mer](/help/admin/admin/publishing-list.md) |
| **EOL för Data Workbench** | 14 september 2022 | Adobe har för avsikt att göra Datan Workbench gällande **31 december 2023**. Kontakta kundtjänst för att få en alternativ lösning till Datan Workbench eller om du har några frågor. [Läs mer](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html) |
| **EOL för[!DNL Reports & Analytics]** | 4 januari 2022 | Effektivt **31 december 2023** kommer Adobe att upphöra med sin verksamhet [!DNL Reports & Analytics] och tillhörande rapporter och funktioner. Rapporterna, visualiseringarna och den underliggande tekniken som ligger till grund för [!DNL Reports & Analytics] inte längre uppfyller Adobe teknikstandarder. Mest [!DNL Reports & Analytics] funktioner finns i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Sedan Analysis Workspace släpptes 2015 har [!DNL Reports & Analytics] funktionaliteten och funktionerna har flyttats till Analysis Workspace och ett tröskelvärde för arbetsflödets paritet har uppnåtts. [Detta meddelande](https://spark.adobe.com/page/6WnF8JK6IRDhf/) förklarar processen för att avsluta livscykeln. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

De senaste uppdateringarna av AppMeasurement-versioner (version 2.23.0) finns i [Versionsinformation om AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=en).
