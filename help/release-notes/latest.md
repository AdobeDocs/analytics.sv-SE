---
title: Versionsinformation om den senaste analysen
description: Se versionsinformationen för Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 31387d369428727a486a19b986bf9d891a36e714
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 4%

---

# Aktuell versionsinformation för Adobe Analytics (maj 2022)

**Senaste uppdatering**: 17 maj 2022

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
| Inga nya funktioner den här månaden | Ej tillämpligt | Ej tillämpligt |

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
| **SFTP-uppgradering** | 9 maj 2022 | Tidigare hade vi meddelat att Adobe skulle uppgradera sina tjänster för SFTP (Secure File Transfer Protocol) i maj 2022 för att ge bättre säkerhet vid filöverföring. Vi har skjutit upp uppgraderingen till sommaren 2022. När den här ändringen görs stöds inte längre vissa SFTP-klientkonfigurationer. Detta påverkar endast data som skickas till eller hämtas från Adobe Analytics med SFTP. FTP-protokollet påverkas inte. För att undvika avbrott i tjänsten bör du se till att dina SFTP-klienter (kod, verktyg, tjänster) följer de detaljerade ändringarna [här](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html). |
| **CDA-berättigande (Cross-Device Analytics)** | 13 april 2022 | Effektivt **1 maj 2022**, nya implementeringar av [CDA](/help/components/cda/overview.md) begränsas till högst tre RSID:er (Report Suite ID) per kund. |
| **Ändra till hur Adobe Analytics hanterar A4T-data som samlats in via Experience Edge** | 31 mars 2022 | Den 7 mars 2022 ändrade Analytics hur det hanterar vissa anrop från Experience Edge som innehåller Target-innehåll som är avsett för A4T-rapportering (Analytics for Target). Från och med den 7 mars ändras alla träffar med A4T-rapportinnehåll så att de inte behandlas som sidvy eller länkhändelser. Startar **31 mars 2022**, är logiken mer selektiv så att standardhändelserna för sidvisning och klickning inte ändras. Framöver är de enda händelser som ändras endast personliga anrop som bara har A4T-innehåll. |
| **Uppdatering till webbläsarkrypteringsmetoder som stöds av vissa kunder** | 28 mars 2022 | Adobe erbjuder två krypteringsnivåer för att uppfylla olika kundbehov när det gäller säkerhet vid datainsamling från första part. På **23 juni 2022** support tas bort för vissa HTTPS-krypteringsalgoritmer, så kallade ciphers, för kunder med säkerhetsnivån inställd på Hög. Den här åtgärden innebär att vissa äldre operativsystem inte längre kan skicka data till Analytics eftersom de inte har stöd för moderna krypteringsmetoder. Kunder som använder standardsäkerhetsinställningarna för chiffrering påverkas inte. Alla kunder som för närvarande använder inställningen &quot;Hög&quot; har redan kontaktats direkt. Här finns en detaljerad lista över de cifer som påverkas av denna ändring. |
| **Pausa äldre schemalagda rapporter** | 12 april 2022 | Effektivt **20 april 2022** kommer Adobe att pausa alla schemalagda rapporter som har ett skapandedatum som är större än två år (skapat före den 31 januari 2020). Inga rapporter eller data tas bort. Endast rapporter som identifieras som äldre än två år pausas och inga ytterligare schemalagda rapporter skickas. Läs mer |
| **2022 ISO-regionuppdateringar** | 11 mars 2021 | Adobe planerar att genomföra 2022 ISO-regionsuppdateringar på **10 juni 2022**. Efter den här versionen förväntas mindre uppdateringar av geoinformation visas. |
| **Pausa tidigare schemalagda Report Builder-aktiviteter** | 12 april 2022 | Effektivt **20 april 2022** kommer Adobe att göra uppehåll i alla schemalagda uppdrag i Report Builder som skapades för mer än två år sedan. Den här pausen gäller i synnerhet alla uppgifter som skapats före den 31 januari 2020. Inga uppgifter, arbetsböcker eller data tas bort. Uppgifter som identifieras som äldre än två år pausas dock och inga ytterligare schemalagda aktiviteter skickas. Läs mer |
| **Tillåtelselista EOL-tillägget för OAuth/JWT-integreringar med äldre Analytics upphör att gälla** | 14 januari 2022 | På **25 maj 2022**, [Analytics 1.3 API, 1.4 SOAP API och Legacy Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) Tillägget tillåtelselista upphör att gälla. Den har erbjudits kunder som använder äldre [!DNL Adobe Analytics] OAuth/JWT-autentiseringsuppgifter ger ytterligare tid att migrera sina klientintegreringar till [Adobe IMS-autentiseringsuppgifter](https://developer.adobe.com/console). Detta påverkar (men är inte begränsat till) [!DNL Adobe Analytics Livestream] och [!DNL Adobe Campaign] kunder som inte har slutfört sina nödvändiga IMS-migreringar. Kunder som för närvarande använder äldre [!DNL Analytics] OAuth/JWT-inloggningsuppgifter via tillägget tillåtelselista och som inte slutfört migreringen till IMS-inloggningsuppgifter senast den 25 maj 2022 förlorar åtkomst till Adobes tjänster. Privatpersoner kan referera till dessa [instruktioner](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) när deras klientprogram migreras till IMS-autentiseringsuppgifter. [!DNL Campaign] kan man kontakta Adobe för att uppgradera till den senaste versionen av [!DNL Campaign]. |
| **EOL för[!DNL Reports & Analytics]** | 4 januari 2022 | Effektivt **31 december 2023** kommer Adobe att upphöra med sin verksamhet [!DNL Reports & Analytics] och tillhörande rapporter och funktioner. Rapporterna, visualiseringarna och den underliggande tekniken som ligger till grund för [!DNL Reports & Analytics] inte längre uppfyller Adobe teknikstandarder. Mest [!DNL Reports & Analytics] funktioner finns i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Sedan Analysis Workspace släpptes 2015 har [!DNL Reports & Analytics] funktionaliteten och funktionerna har flyttats till Analysis Workspace och ett tröskelvärde för arbetsflödets paritet har uppnåtts. [Detta meddelande](https://spark.adobe.com/page/6WnF8JK6IRDhf/) förklarar processen för att avsluta livscykeln. |

{style=&quot;table-layout:auto&quot;}

### AppMeasurement

De senaste uppdateringarna av AppMeasurement-versioner (version 2.2.4) finns i [Versionsinformation om AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=en).

