---
title: Versionsinformation om den senaste analysen
description: Se versionsinformationen för Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 95f05bbf620c140f3e17a070d95b21b62db58bcc
workflow-type: tm+mt
source-wordcount: '1077'
ht-degree: 2%

---

# Aktuell versionsinformation för Adobe Analytics (juni 2022)

>[!NOTE]
>
>Den här sidan innehåller information om förhandsversioner och kan komma att ändras.

**Senaste uppdatering**: 15 juni 2022

## Relaterade resurser

* [Information om föregående version för 2022](/help/release-notes/2022.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html)

## Nya funktioner i Adobe Analytics

| Funktion | Beskrivning | [Måldatum](releases.md) |
| ----------- | ---------- | ------- |
| **Nytt gränssnitt för visualisering av flöde** | Ger ytterligare funktionalitet i vår Flow-visualisering så att den blir kraftfullare och mer funktionell. [Läs mer](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/flow/create-flow.html?lang=en) | 15 juni 2022 |
| **Dela anteckningar i Mobile Scorecards** | Du kan visa anteckningar som har skapats i Workspace - i Mobile Scorecards. På så sätt kan ni dela kontextuella datanunkter och insikter om organisationen och kampanjer direkt i Mobile Scorecard-projekt, som kan visas i mobilappen för kontrollpaneler i Analytics. [Läs mer](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/annotations/mobile-annotations.html?lang=en) | 15 juni 2022 |
| **Stöd för produktsyntaxversion av Merchandising Variables med Edge Collection** | Nu kan du ställa in variabler för försäljning med hjälp av motsvarande produktsyntax genom att ställa in relevanta XDM-fält. Läs mer om produktsyntax för variabler [här](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html?lang=en). Se mappningarna för produktsyntax [här](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=en#aep-edge). | 15 juni 2022 |
| **Fylla i livscykeldimensioner och mätvärden med Experience Edge** | Mobila livscykeldata som skickas via Experience Edge visas nu i analysrapporter. I dokumentationen finns mer information om vilka XDM-fält som mappar till befintlig mobil Lifecycle-rapportering. [Läs mer](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) | 27 maj 2022 |
| **Bearbetningsregler för mobiltjänster som är tillgängliga i analysbearbetningsregler** | Adobe Mobile Services upphör den 31 december 2022. Befintliga bearbetningsregler som skapats eller genererats av Adobe Mobile Services migreras automatiskt till Adobe Analytics bearbetningsregler, där du kan redigera och hantera dem. De kan visas, men kan inte längre redigeras i Mobile Services förrän produkten har solnedgång. Om du har ytterligare frågor eller support kan du kontakta Adobe kundtjänst. [Läs mer](https://experienceleague.adobe.com/docs/mobile-services/using/eol.html?lang=en) | 15 juni 2022 |
| **Ny klassificeringsupplevelse - fas 1** | Den här stegvisa releasen av en ny användarupplevelse för klassificeringsuppsättningar ökar synligheten i kundägda klassificeringsdata avsevärt. [Allmän tillgänglighet](/help/release-notes/releases.md) beräknas vara tidigt 2023. | Begränsad testning börjar 15 juni 2022 |

{style=&quot;table-layout:auto&quot;}

### Korrigeringar i Adobe Analytics

AN-251686; AN-283542; AN-286572; AN-286945; AN-286784; AN-286944; AN-287012; AN-287319; AN-287333; AN-287348; AN-287429; AN-288238; AN-288281; AN-288660; AN-288769; AN-288798; AN-288871; AN-288872; AN-288941; AN-288951; AN-288952; AN-288956; AN-289062; AN-289340; AN-289346; AN-289488; AN-289562; AN-289580; AN-289861; AN-289892;

### Viktiga meddelanden för Adobe Analytics-administratörer

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **Pausa schemalagda rapporter i rapporter och analyser** | 8 juni 2022 | Den 21 april 2022 meddelade vi att flera funktioner som är specifika för schemalagda rapporter skulle tas bort som förberedelse inför det tidigare utkomna livets slut för rapporter och analyser. Bland dessa funktioner fanns möjligheten att schemalägga nya rapporter och nya datautdrag.<p>Som svar på kundförfrågningar om förlängning och för att underlätta övergången från Reports and Analytics har vi beslutat att utöka åtkomsten till dessa funktioner tills **31 jan 2023**. Observera att förfallotiden för både rapporter och dataextrakt fortsätter att vara begränsad till nio månader. leverans av rapport och dataextrahering pausas vid periodens slut om inte schemat återaktiveras.<p>För att upprepa detta kommer dessa funktioner att bli inaktuella den 31 januari 2023. Före detta datum måste du migrera din schemalagda rapportering till någon av de andra mekanismer som är tillgängliga i Adobe Analytics. Om du har ytterligare frågor eller support kan du kontakta Adobe kundtjänst. [Läs mer](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Pausa schemalagda aktiviteter i Report Builder** | 8 juni 2022 | Den 21 april 2022 introducerade vi förändringar av schemalagda arbetsuppgifter i Report Builder som en del av våra insatser för optimering av prestanda och leverans. Dessa ändringar inkluderar borttagning av möjligheten att ha schemalagda leveranser som &quot;upphör efter x förekomster&quot;. Som svar på flera kundförfrågningar som kräver mer tid att utforska och implementera alternativ har vi beslutat att återställa detta alternativ i begränsad omfattning tills **31 jan 2023**.<p>Du kan fortsätta att schemalägga aktiviteter per Report Builder och låta dem sluta efter högst 99 tillfällen. Observera att återställningen endast gäller timuppgifter. &quot;end after x instances&quot; förblir otillgängligt för alla andra leveransintervall (dag, vecka, månad och år). Observera att detta alternativ kommer att vara inaktuellt den 31 januari 2023. Om du har frågor eller support kan du kontakta Adobe kundtjänst. [Läs mer](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **SFTP-uppgradering** | 9 maj 2022 | Tidigare hade vi meddelat att Adobe skulle uppgradera sina tjänster för SFTP (Secure File Transfer Protocol) i maj 2022 för att ge bättre säkerhet vid filöverföring. Vi har skjutit upp uppgraderingen till **Sommaren 2022**. När den här ändringen görs stöds inte längre vissa SFTP-klientkonfigurationer. Detta påverkar endast data som skickas till eller hämtas från Adobe Analytics med SFTP. FTP-protokollet påverkas inte. För att undvika avbrott i tjänsten bör du se till att dina SFTP-klienter (kod, verktyg, tjänster) följer de detaljerade ändringarna [här](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html). |
| **Uppdatering till webbläsarkrypteringsmetoder som stöds av vissa kunder** | 28 mars 2022 | Adobe erbjuder två krypteringsnivåer för att uppfylla olika kundbehov när det gäller säkerhet vid datainsamling från första part. På **23 juni 2022** support tas bort för vissa HTTPS-krypteringsalgoritmer, så kallade ciphers, för kunder med säkerhetsnivån inställd på Hög. Den här åtgärden innebär att vissa äldre operativsystem inte längre kan skicka data till Analytics eftersom de inte har stöd för moderna krypteringsmetoder. Kunder som använder standardsäkerhetsinställningarna för chiffrering påverkas inte. Alla kunder som för närvarande använder inställningen &quot;Hög&quot; har redan kontaktats direkt. En detaljerad lista över de cifer som påverkas av detta |
| **2022 ISO-regionuppdateringar** | 11 mars 2021 | Adobe utförde 2022 ISO-regionsuppdateringar på **10 juni 2022**. Efter den här versionen förväntas mindre uppdateringar av geoinformation visas. |
| **EOL för[!DNL Reports & Analytics]** | 4 januari 2022 | Effektivt **31 december 2023** kommer Adobe att upphöra med sin verksamhet [!DNL Reports & Analytics] och tillhörande rapporter och funktioner. Rapporterna, visualiseringarna och den underliggande tekniken som ligger till grund för [!DNL Reports & Analytics] inte längre uppfyller Adobe teknikstandarder. Mest [!DNL Reports & Analytics] funktioner finns i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Sedan Analysis Workspace släpptes 2015 har [!DNL Reports & Analytics] funktionaliteten och funktionerna har flyttats till Analysis Workspace och ett tröskelvärde för arbetsflödets paritet har uppnåtts. [Detta meddelande](https://spark.adobe.com/page/6WnF8JK6IRDhf/) förklarar processen för att avsluta livscykeln. |

{style=&quot;table-layout:auto&quot;}

### AppMeasurement

De senaste uppdateringarna av AppMeasurement-versioner (version 2.2.4) finns i [Versionsinformation om AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=en).

