---
title: Versionsinformation om den senaste analysen
description: Se versionsinformationen för Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 433a750ddf4aca56fd9fbe5ec2482f66cf45125f
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Aktuell versionsinformation för Adobe Analytics (mars 2022)

**Senast uppdaterad: 31 mars 2022**

* For February 2022 release notes, go [här](/help/release-notes/2022.md).
* För versionsinformation om Customer Journey Analytics går du till [här](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)
* Versionsinformation om Media Analytics finns på [här](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=en)
* Läs om de senaste versionsuppdateringarna för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html). Få den senaste självhjälpsdokumentationen, självstudiekurserna och kurserna om Experience League.

## Nya funktioner i Adobe Analytics {#aa-features}

| Funktion | Beskrivning | [Måldatum](releases.md) |
| ----------- | ---------- | ------- |
| Anteckningar i arbetsytan | Anteckningar i Workspace gör att du effektivt kan kommunicera kontextuella datanunkter och insikter till din organisation. [Läs mer](/help/analyze/analysis-workspace/components/annotations/overview.md) | Den gradvisa utrullningen börjar den 23 mars 2022. Allmän tillgänglighet: 11 april 2022 |
| Uppdateringar av Adobe Analytics landningssida | Uppdateringar till landningssidan för arbetsyta/rapporter och analyser som förbättrar användbarheten och underlättar navigeringen. [Läs mer](/help/analyze/landing.md) | 1 april 2022 |
| [!UICONTROL Next item] eller [!UICONTROL Previous item] Panelen Arbetsyta | The [!UICONTROL Next or Previous item] kan du utforska objekt som följer efter eller föregår ett önskat dimensionsobjekt. Använd den om du till exempel vill se nästa eller föregående sidor till en viss produktsida, marknadsföringskanal eller till och med enhetstyp. Den här panelen går längre än äldre rapportering nästa/föregående eftersom den gör att du kan titta på alla dimensioner och inte kräver någon ny implementering för att få insikter. | 1 april 2022 |
| [!UICONTROL Page Summary] Panelen Arbetsyta | The [!UICONTROL Page Summary] ger en djupgående analys av en sida du väljer. Det innehåller samma information som tidigare rapporter och analyser [!UICONTROL Page Summary] och mycket annat. | 1 april 2022 |

{style=&quot;table-layout:auto&quot;}

## Korrigeringar i Adobe Analytics

* Korrigerade ett problem som resulterade i ett fel vid försök att få åtkomst till Activity Map. (AN-267177)
* Ett problem med misslyckade överföringar av användarresurser har korrigerats. (AN-279813)
* Problem med A4T Workspace-panelen har korrigerats. (AN-281594) AN-282418)
* Ett problem har korrigerats där vissa användare inte kunde få åtkomst till Adobe Analytics. (AN-282776)
* Korrigerade problem med vissa nyligen skapade rapportsviter som inte samlar in data. (AN-283114, AN-283311)
* Korrigerade problem med felaktigt skickade e-postmeddelanden om datafeeds. (AN-280255; AN-282051)

### Ytterligare korrigeringar i Adobe Analytics

AN-256929; AN-270937; AN-272158; AN-275130; AN-277830; AN-278635; AN-279066; AN-279683; AN-279899; AN-280504; AN-280617; AN-280663; AN-281423; AN-281523; AN-281608; AN-281671; AN-281963; AN-282027; AN-282218; AN-282593; AN-282605; AN-282632; AN-282654; AN-282694; AN-282744; AN-282756; AN-282804; AN-282838; AN-282862; AN-282903; AN-282937; AN-282892; AN-283315; AN-283338; AN-283388; AN-283417; AN-283474; AN-283511; AN-283691, AN-283895; AN-283943; AN-283957; AN-284030; AN-284100; AN-284142; AN-284162

## Viktiga meddelanden för Adobe Analytics-administratörer

**Senast uppdaterad: 31 mars 2022**

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| Ändra till hur Analytics hanterar A4T-data som samlats in via Experience Edge | 31 mars 2022 | På **7 mars 2022** har vi ändrat hur vi hanterar vissa anrop från Experience Edge som innehåller målinnehåll som är avsett för analys av målrapportering (A4T). Från och med den 7 mars ändrades alla träffar med A4T-rapportinnehåll så att de inte behandlades som sidvy eller länkhändelser. **Från 31 mars 2022** har vi ändrat vår logik så att den är mer selektiv så att standardhändelserna för sidvisning och klickning inte ändras. Framöver kommer de enda händelser som kommer att ändras att vara personliga anrop som bara har A4T-innehåll. |
| Uppdatering till webbläsarkrypteringsmetoder som stöds av vissa kunder | 28 mars 2022 | Adobe erbjuder två krypteringsnivåer för att uppfylla olika kundbehov när det gäller säkerhet vid datainsamling från första part. På **23 juni 2022** vi kommer att ta bort stöd för vissa HTTPS-krypteringsalgoritmer, så kallade ciphers, för kunder med säkerhetsnivån inställd på&quot;Hög&quot;. Detta innebär att vissa äldre operativsystem inte längre kan skicka data till Analytics eftersom de inte har stöd för moderna krypteringsmetoder. Kunder som använder standardsäkerhetsinställningarna för chiffrering påverkas inte. Alla kunder som för närvarande använder inställningen &quot;Hög&quot; har redan kontaktats direkt. En detaljerad lista över de ciphers som påverkas av den här ändringen finns [här](/help/technotes/rdc/encryption-algos.md). |
| Pausa äldre schemalagda rapporter | 11 mars 2022 | Effektivt **15 april 2022** kommer Adobe att pausa alla schemalagda rapporter som har ett skapandedatum som är större än två år (skapat före den 31 januari 2020). Inga rapporter eller data kommer att tas bort. Endast rapporter som identifieras som äldre än två år kommer att pausas och inga ytterligare schemalagda rapporter kommer att skickas. [Läs mer](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| 2022 ISO-regionuppdateringar | 11 mars 2021 | Adobe kommer att utföra 2022 ISO-regionsuppdateringar på **10 juni 2022**. Efter den här versionen förväntas mindre uppdateringar av geoinformation visas. |
| Pausa tidigare schemalagda Report Builder-aktiviteter | 24 februari 2022 | **Gäller från 15 april 2022** kommer Adobe att göra uppehåll i alla schemalagda uppdrag i Report Builder som skapades för mer än två år sedan. Den här pausen gäller i synnerhet alla uppgifter som skapats före den 31 januari 2020. Inga uppgifter, arbetsböcker eller data tas bort. Uppgifter som identifieras som äldre än två år kommer dock att pausas och inga ytterligare schemalagda aktiviteter kommer att skickas. [Läs mer](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| Tillåtelselista EOL-tillägget för OAuth/JWT-integreringar med äldre Analytics upphör att gälla | 14 januari 2022 | På **25 maj 2022**, [Analytics 1.3 API, 1.4 SOAP API och Legacy Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) Tillägget tillåtelselista upphör att gälla. Den har erbjudits kunder som använder äldre [!DNL Adobe Analytics] OAuth/JWT-autentiseringsuppgifter ger ytterligare tid att migrera sina klientintegreringar till [Adobe IMS-autentiseringsuppgifter](https://developer.adobe.com/console). Detta påverkar (men är inte begränsat till) [!DNL Adobe Analytics Livestream] och [!DNL Adobe Campaign] kunder som inte har slutfört sina nödvändiga IMS-migreringar. Kunder som för närvarande använder äldre [!DNL Analytics] OAuth/JWT-autentiseringsuppgifter via tillägget tillåtelselista och som inte slutfört migreringen till IMS-autentiseringsuppgifter senast den 25 maj 2022 förlorar åtkomsten till Adobes tjänster. Privatpersoner kan referera till dessa [instruktioner](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) när deras klientprogram migreras till IMS-autentiseringsuppgifter. [!DNL Campaign] kan man kontakta Adobe för att uppgradera till den senaste versionen av [!DNL Campaign]. |
| SFTP-uppgradering (Secure File Transfer Protocol) | 3 mars 2022 | På **15 maj 2022**, [!DNL Adobe Analytics] kommer att uppgradera sina SFTP-tjänster (Secure File Transfer Protocol) för att ge bättre säkerhet för filöverföringar. Den här ändringen innebär att vissa SFTP-klientkonfigurationer inte längre stöds. Vi kommer även att lägga till några anslutningsalternativ som är tillgängliga via **1 mars 2022**. Detta påverkar endast data som skickas till eller hämtas från Adobe Analytics med SFTP. FTP-protokollet påverkas inte. För att undvika avbrott i tjänsten bör du se till att dina SFTP-klienter (kod, verktyg, tjänster) följer de detaljerade ändringarna [här](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html). |
| EOL för [!DNL Reports & Analytics] | 4 januari 2022 | Effektivt **31 december 2023** kommer Adobe att upphöra med sin verksamhet [!DNL Reports & Analytics] och tillhörande rapporter och funktioner. Rapporterna, visualiseringarna och den underliggande tekniken som ligger till grund för [!DNL Reports & Analytics] inte längre uppfyller Adobe teknikstandarder. Mest [!DNL Reports & Analytics] funktioner finns i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Sedan Analysis Workspace släpptes 2015 har [!DNL Reports & Analytics] funktionaliteten och funktionerna har flyttats till Analysis Workspace och ett tröskelvärde för arbetsflödets paritet har uppnåtts. [Detta meddelande](https://spark.adobe.com/page/6WnF8JK6IRDhf/) förklarar processen för att avsluta livscykeln. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement {#appm}

De senaste uppdateringarna av AppMeasurement-versioner (version 2.2.4) finns i [Versionsinformation om AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=en).

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] versionsinformation](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)
