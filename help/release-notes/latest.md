---
title: Versionsinformation om den senaste analysen
description: Se versionsinformationen för Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 9a16f3942505028624e5c07568342a9acac898d7
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Aktuell versionsinformation för Adobe Analytics (maj 2022)

**Senaste uppdatering**: 8 juni 2022

## Relaterade resurser

* [Information om föregående version för 2022](/help/release-notes/2022.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html)

## Nya funktioner i Adobe Analytics

| Funktion | Beskrivning | [Måldatum](releases.md) |
| ----------- | ---------- | ------- |
| Fylla i livscykeldimensioner och mätvärden med Experience Edge | Mobila livscykeldata som skickas via Experience Edge visas nu i analysrapporter. I dokumentationen finns mer information om vilka livscykeldata som samlas in via Experience Edge och hur de motsvarar befintliga livscykelrapporter. [Läs mer - kommer snart] | 27 maj 2022 |

{style=&quot;table-layout:auto&quot;}

### Korrigeringar i Adobe Analytics

(Korrigeringar för flera kunder)

Ej tillämpligt

### Ytterligare korrigeringar i Adobe Analytics

(Korrigeringar för enskilda kunder)

AN-274429; AN-279640; AN-280918; AN-280945; AN-282884; AN-283565; AN-284785; AN-284814; AN-284854; AN-284989; AN-285244; AN-285253; AN-285432; AN-285528; AN-285535; AN-285710; AN-286255; AN-286340; AN-286434; AN-286454; AN-286630; AN-286716; AN-286854; AN-286911

### Viktiga meddelanden för Adobe Analytics-administratörer

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| Pausa schemalagda rapporter i rapporter och analyser | 8 juni 2022 | Den 21 april 2022 meddelade vi att ett antal funktioner som är specifika för schemalagda rapporter skulle tas bort som förberedelse för de tidigare annonserade [slutet på livscykeln för rapporter och analyser](https://express.adobe.com/page/6WnF8JK6IRDhf/). Bland dessa funktioner fanns möjligheten att schemalägga nya rapporter och nya datautdrag.<p>Som svar på kundförfrågningar om förlängning och för att underlätta övergången från Reports and Analytics har vi beslutat att utöka åtkomsten till dessa funktioner tills **31 jan 2023**. Observera att förfallotiden för både rapporter och dataextrakt fortsätter att vara begränsad till nio månader. leverans av rapport och dataextrahering pausas vid periodens slut om inte schemat återaktiveras. <p>För att upprepa detta kommer dessa funktioner att bli inaktuella den 31 januari 2023, innan du måste migrera din schemalagda rapportering till någon av de andra mekanismer som är tillgängliga i Adobe Analytics. Om du har ytterligare frågor eller support kan du kontakta Adobe kundtjänst. |
| Pausa schemalagda aktiviteter i Report Builder | 8 juni 2022 | Den 21 april 2022 introducerade vi förändringar av schemalagda arbetsuppgifter i Report Builder som en del av våra insatser för optimering av prestanda och leverans. Dessa ändringar inkluderar borttagning av möjligheten att ha schemalagda leveranser som &quot;upphör efter x förekomster&quot;. Som svar på flera kundförfrågningar som kräver mer tid att utforska och implementera alternativ har vi beslutat att återställa detta alternativ i begränsad omfattning tills **31 jan 2023**.<p>Du kommer även fortsättningsvis att kunna schemalägga aktiviteter per Report Builder och låta dem sluta efter högst 99 tillfällen. Observera att återställningen endast gäller timuppgifter. &quot;end after x instances&quot; förblir otillgängligt för alla andra leveransintervall (dag, vecka, månad och år). Observera att detta alternativ kommer att vara inaktuellt den 31 januari 2023. Om du har frågor eller support kan du kontakta Adobe kundtjänst. |
| **SFTP-uppgradering** | 9 maj 2022 | Tidigare hade vi meddelat att Adobe skulle uppgradera sina tjänster för SFTP (Secure File Transfer Protocol) i maj 2022 för att ge bättre säkerhet vid filöverföring. Vi har skjutit upp uppgraderingen till **Sommaren 2022**. När den här ändringen görs stöds inte längre vissa SFTP-klientkonfigurationer. Detta påverkar endast data som skickas till eller hämtas från Adobe Analytics med SFTP. FTP-protokollet påverkas inte. För att undvika avbrott i tjänsten bör du se till att dina SFTP-klienter (kod, verktyg, tjänster) följer de detaljerade ändringarna [här](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html). |
| **Uppdatering till webbläsarkrypteringsmetoder som stöds av vissa kunder** | 28 mars 2022 | Adobe erbjuder två krypteringsnivåer för att uppfylla olika kundbehov när det gäller säkerhet vid datainsamling från första part. På **23 juni 2022** support tas bort för vissa HTTPS-krypteringsalgoritmer, så kallade ciphers, för kunder med säkerhetsnivån inställd på Hög. Den här åtgärden innebär att vissa äldre operativsystem inte längre kan skicka data till Analytics eftersom de inte har stöd för moderna krypteringsmetoder. Kunder som använder standardsäkerhetsinställningarna för chiffrering påverkas inte. Alla kunder som för närvarande använder inställningen &quot;Hög&quot; har redan kontaktats direkt. Här finns en detaljerad lista över de cifer som påverkas av denna ändring. |
| **2022 ISO-regionuppdateringar** | 11 mars 2021 | Adobe planerar att genomföra 2022 ISO-regionsuppdateringar på **10 juni 2022**. Efter den här versionen förväntas mindre uppdateringar av geoinformation visas. |
| **EOL för[!DNL Reports & Analytics]** | 4 januari 2022 | Effektivt **31 december 2023** kommer Adobe att upphöra med sin verksamhet [!DNL Reports & Analytics] och tillhörande rapporter och funktioner. Rapporterna, visualiseringarna och den underliggande tekniken som ligger till grund för [!DNL Reports & Analytics] inte längre uppfyller Adobe teknikstandarder. Mest [!DNL Reports & Analytics] funktioner finns i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Sedan Analysis Workspace släpptes 2015 har [!DNL Reports & Analytics] funktionaliteten och funktionerna har flyttats till Analysis Workspace och ett tröskelvärde för arbetsflödets paritet har uppnåtts. [Detta meddelande](https://spark.adobe.com/page/6WnF8JK6IRDhf/) förklarar processen för att avsluta livscykeln. |

{style=&quot;table-layout:auto&quot;}

### AppMeasurement

De senaste uppdateringarna av AppMeasurement-versioner (version 2.2.4) finns i [Versionsinformation om AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=en).

