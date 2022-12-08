---
title: Versionsinformation om den senaste analysen
description: Se versionsinformationen för Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d5d4d1c9274bba8c3a40ee8fe86da311c1d1220b
workflow-type: tm+mt
source-wordcount: '1445'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Analytics (oktober/november 2022)

**Senaste uppdatering**: 18 november 2022

Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner i Adobe Analytics

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **[!UICONTROL Key metric summary]** visualisering | The [!UICONTROL Key metric summary] visualisering gör att du kan se hur viktiga mätvärden trendar inom en enda tidsram. Du kan också jämföra mätprestanda över två tidsramar. [Läs mer](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/key-metric.html) | 5 oktober 2022 | 19 oktober 2023 |
| **Skiftlägesokänsliga multivärdesvariabler** | För skiftlägesokänsliga multivärdesvariabler lagras värdena i `mvvar1 - mvvar3` och `post_mvvar1 - post_mvvar3` i Dataflöden kommer inte längre att sänkas automatiskt. I stället kommer dataflöden (och data som skickas via Analytics Source Connector till Adobe Experience Platform och CJA) att återspegla det ursprungliga fallet som skickades från sidan. | Ej tillämpligt | 24 oktober 2022 |

{style=&quot;table-layout:auto&quot;}

## Korrigeringar i Adobe Analytics

* Ett problem har korrigerats där de senaste MacOS-versionerna felaktigt hade namnet &quot;Macintosh&quot;. Med den här korrigeringen börjar OS-dimensionen använda versionsnumrering från&quot;MacOS&quot;, med början från MacOS 11. (AN-301834)
* Ett problem med datumintervallet &quot;fasta datum&quot; i Report Builder har korrigerats. (AN-303684)
* Ett problem har korrigerats där användargränssnittet för dataflöden inte lästes in. (AN-303803, AN-303784)

### Andra korrigeringar

AN-295574; AN-296354; AN-297143; AN-299501; AN-301755; AN-302054; AN-302304; AN-302631; AN-302811; AN-303090; AN-303372; AN-303428; AN-303429; AN-303432; AN-303434; AN-303437; AN-303438; AN-303519; AN-303610; AN-303656; AN-303659; AN-303663; AN-303664; AN-303818; AN-303823; AN-303837; AN-304036; AN-304195; AN-304321; AN-304325; AN-304339; AN-304356; AN-304435; AN-304457; AN-304509; AN-304519; AN-304534

## Viktiga meddelanden för Adobe Analytics-administratörer

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **Uppdaterade riktlinjer för trafikspikes-meddelanden** | 18 november 2022 | Tidigare riktlinjer baserades strikt på träffvolymer. The [nya riktlinjer](https://experienceleague.adobe.com/docs/analytics/admin/traffic-management/traffic-lead-time.html?lang=en) baseras på en kombination av rapportsvitens storlek och procentuell ökning. |
| **Uppdatera till enhetssökningar på grund av Google klienttips** | 14 oktober 2022 | Användningen av klienttips i enhetssökning, som ursprungligen planerades till 26 oktober 2022, har skjutits upp till **Januari 2023**. <p> <p>Från och med oktober 2022 är det möjligt att samla in klienttips med antingen Web SDK- eller AppMeasurement JavaScript-biblioteken. Men klienttips kommer inte att införlivas i enhetssökning förrän i januari 2023. Vid det datumet kommer Adobe att börja använda klienttips förutom användaragenten när vissa enhetsuppgifter hämtas för träffar från Chromium-webbläsare, som Google Chrome och Microsoft Edge. Detta är ett svar på Google plan att gradvis minska informationen som presenteras från användaragentsträngen i stället för data som skickas via klienttips. <p> <p>Som en del av den här ändringen använder Adobe enhetskartan för alla enhetssökningar som är relaterade till användaragenten. [Läs mer](/help/technotes/client-hints.md) |
| **Standardstartsida** | 29 september 2022 | The [ny landningssida](/help/analyze/landing.md) som introducerades tidigare i år kommer att bli standardupplevelsen för alla användare i **Januari 2023**. Den aktuella sidan kommer att bli inaktuell och alla kommer att behöva använda den nya upplevelsen. |
| **[!UICONTROL Anomaly detection]autokörningsförhållanden** | 29 september 2022 | Idag [!UICONTROL Anomaly detection] körs automatiskt på alla kolumner i friformstabeller i tidsserier. För att säkerställa att data är tillgängliga för analys och att projekt läses in snabbare kommer Adobe att ändra hur automatisk detektering av avvikelser körs. Startar **26 oktober 2022**, [!UICONTROL Anomaly detection] körs bara automatiskt på den första måttkolumnen i en tabell. Du kan konfigurera kolumninställningar så att avvikelseidentifiering körs på andra kolumner, om det behövs. |
| **Uppdatera till ny NetAcuity-databas** | 26 september 2022 | Denna uppdatering, som ursprungligen planerades till den 5 oktober 2022, har skjutits upp till **Januari 2023**. Transportföretagsrelaterad information lagrad i `carrier` i Adobe Analytics Data warehouse och Analytics Data Feeds kommer att ändras. Historiskt sett har dataformatet i den kolumnen `<domain>:<ISP>`. Adobe har en intern uppslagstabell för att mappa dessa `<domain>:<ISP>` värden i företagsnamn för rapportering i Adobe Analytics rapporteringsverktyg (Analysis Workspace, Rapporter och analyser, API för rapportering, Data warehouse, LiveStream osv.). Uppslagsfilen (`carrier.tsv`) ingår också i datafeeds så att du kan använda samma mappningar.<p>Den här uppdateringen förbättrar våra datamappningar med hjälp av en mer korrekt transportföretagsdatabas från NetAcuity. Formatet på data i transportföretagskolumnen i Datafeeds ändras under utvecklingen. I stället för `<domain>:<ISP>`, kommer det att innehålla ett transportföretagsnamn. Adobe kommer att fortsätta att använda uppslagstabellen för att upprätthålla så mycket kontinuitet som möjligt med tidigare rapportering. Rapporteringsverktyg där sökningarna tillämpas av Adobe (Analysis Workspace, Rapporter och analyser, rapporterings-API, data warehouse, LiveStream osv.) kan dra nytta av mer exakta mappningar. Vissa mappningar - särskilt för internationella domäner och Internet-leverantörer - kommer att förändras mer än andra när Adobe antar den nya databasen. Dataflödets sökningsfil för bärare (`carrier.tsv`) behåller de gamla mappningarna och lägger till de nya mappningarna.<p>Analyskällans koppling för analys mappar för närvarande inte transportföretagsfältet, så det finns för närvarande ingen tillgänglig transportörrapportering i Experience Platform, CJA osv. Användning av den nya databasen för transportörer kommer därför inte att påverka någonting i Experience Platform som baseras på data från Analytics Source Connector. |
| **Förbättrad mappning av IP-till-geopositionering** | 26 september 2022 | Vår leverantör av IP-sökningar, Digital Element, uppgraderar till en ny förbättrad datamängd (NetAcuity Pulse) för IP-till-geopositioneringsmappning. Ursprungligen planerad för oktober 2022 kommer Adobe Analytics att anta denna nya datauppsättning i **Januari 2023**. Den nya databasen kommer att vara mer exakt än tidigare versioner. Vissa IP-till-geo-mappningar kommer att ändras/förbättras när den nya databasen antas.<p>Alla Adobe Analytics-verktyg (Analysis Workspace, Rapporter och analyser, API för rapportering, data warehouse, LiveStream, dataflöden osv.) utnyttjar automatiskt de nya förbättrade mappningarna. Dataflödenas format ändras inte. CJA-data som tillhandahålls via Analytics Source Connector drar automatiskt nytta av de nya mappningarna. |
| **Pausa schemalagda rapporter i rapporter och analyser** | 8 juni 2022 | Den 21 april 2022 meddelade Adobe att ett flertal funktioner som är specifika för schemalagda rapporter skulle tas bort som förberedelse inför det tidigare utkomna livstidsarbetet för rapporter och analyser. Bland dessa funktioner fanns möjligheten att schemalägga nya rapporter och nya datautdrag.<p>Som svar på kundförfrågningar om förlängning och för att underlätta övergången från rapporter och analyser har Adobe beslutat att utöka åtkomsten till dessa funktioner till **31 jan 2023**. Observera att förfallotiden för både rapporter och dataextrakt fortsätter att vara begränsad till nio månader. leverans av rapport och dataextrahering pausas vid periodens slut om inte schemat återaktiveras.<p>För att upprepa detta kommer dessa funktioner att bli inaktuella den 31 januari 2023. Före detta datum måste du migrera din schemalagda rapportering till någon av de andra mekanismer som är tillgängliga i Adobe Analytics. Om du har ytterligare frågor eller support kan du kontakta Adobe kundtjänst. [Läs mer](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Pausa schemalagda aktiviteter i Report Builder** | 8 juni 2022 | Den 21 april 2022 införde Adobe ändringar i schemalagda aktiviteter i Report Builder som en del av våra insatser för optimering av prestanda och leverans. Dessa ändringar inkluderar borttagning av möjligheten att ha schemalagda leveranser som &quot;upphör efter x förekomster&quot;. Som svar på ett flertal kundförfrågningar om mer tid för att utforska och implementera alternativ har Adobe beslutat att återställa detta alternativ på ett begränsat sätt tills **31 jan 2023**.<p>Du kan fortsätta att schemalägga aktiviteter per Report Builder och låta dem sluta efter högst 99 tillfällen. Observera att återställningen endast gäller timuppgifter. &quot;end after x instances&quot; förblir otillgängligt för alla andra leveransintervall (dag, vecka, månad och år). Observera att detta alternativ kommer att vara inaktuellt den 31 januari 2023. Om du har frågor eller support kan du kontakta Adobe kundtjänst. [Läs mer](/help/analyze/report-builder/r-arb-scheduled-reports.md) |

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
