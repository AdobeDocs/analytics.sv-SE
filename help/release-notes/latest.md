---
title: Versionsinformation om den senaste analysen
description: Se versionsinformationen för Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: c29515da8c74ad3332aa9797db9de505af7fe3aa
workflow-type: tm+mt
source-wordcount: '1056'
ht-degree: 3%

---

# Aktuell versionsinformation för Adobe Analytics (april 2022)

**Senaste uppdatering**: 28 april 2022

## Relaterade resurser

* [Information om föregående version för 2022](/help/release-notes/2022.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html)

## Nya funktioner i Adobe Analytics

| Funktion | Beskrivning | [Måldatum](releases.md) |
| ----------- | ---------- | ------- |
| Uppdateringar av Adobe Analytics landningssida | Uppdateringar till landningssidan för arbetsyta/rapporter och analyser som förbättrar användbarheten och underlättar navigeringen. [Läs mer](/help/analyze/landing.md) | 20 april 2022 |
| [!UICONTROL Next item] eller [!UICONTROL Previous item] Panelen Arbetsyta | The [!UICONTROL Next or Previous item] kan du utforska objekt som följer efter eller föregår ett önskat dimensionsobjekt. Använd den om du till exempel vill se nästa eller föregående sidor till en viss produktsida, marknadsföringskanal eller till och med enhetstyp. Den här panelen går längre än äldre rapportering nästa/föregående eftersom den gör att du kan titta på alla dimensioner och inte kräver någon ny implementering för att få insikter. [Läs mer](/help/analyze/analysis-workspace/c-panels/next-previous.md) | 20 april 2022 |
| [!UICONTROL Page Summary] Panelen Arbetsyta | The [!UICONTROL Page Summary] ger en djupgående analys av en sida du väljer. Det innehåller samma information som tidigare rapporter och analyser [!UICONTROL Page Summary] och mycket annat. [Läs mer](/help/analyze/analysis-workspace/c-panels/page-summary.md) | 20 april 2022 |
| Borttaget krav på `x-proxy-global-company-id` header för 2.0 API-anrop | API:erna för Adobe Analytics 2.0 kräver inte längre `x-proxy-global-company-id` eftersom den här informationen är en del av slutpunkts-URL:en. Du kan fortfarande inkludera det här huvudet, men du får inte längre ett fel om det saknas. | 20 april 2022 |

{style=&quot;table-layout:auto&quot;}

## Korrigeringar i Adobe Analytics

* Korrigerade ett fel i datafeeds, där start- och slutdatum ändrades automatiskt efter att datafeeden sparades när användargränssnittet för dataflöden skapades. Datumen uppdaterades automatiskt en dag. (AN-281262)
* Korrigerade ett problem som förhindrade förnyelse av schemalagda projekt via e-postlänk. (AN-283622)
* Korrigerade ett problem som gjorde att de senaste versionerna av Apple Safari och Microsoft Edge inte identifierades korrekt i söktabellen för webbläsartyp i Adobe. Liknar när [webbläsarversioner uppdateras](/help/components/dimensions/browser.md), uppdaterar sökningstabeller för webbläsartyper och korrigerar bara data som flyttas framåt. Uppslagstabellerna för webbläsarversionen uppdaterades den 20 april och uppslagstabellerna för webbläsartypen uppdaterades den 28 april. (AN-284872) AN-285753; AN-286257)

### Ytterligare korrigeringar i Adobe Analytics

AN-274486; AN-279258; AN-279995; AN-280918; AN-281423; AN-282084; AN-282435; AN-283508; AN-283517; AN-283706; AN-283762; AN-283921; AN-284195; AN-284663; AN-284573; AN-284721; AN-284790; AN-284867; AN-284870; AN-284872; AN-284884; AN-284914; AN-284930; AN-284933; AN-284967; AN-284970; AN-285187; AN-285328; AN-285337; AN-285375; AN-285447; AN-285724; AN-285753; AN-285761

## Viktiga meddelanden för Adobe Analytics-administratörer

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **CDA-berättigande (Cross-Device Analytics)** | 13 april 2022 | Effektivt **1 maj 2022**, ny implementering av [CDA](/help/components/cda/overview.md) begränsas till högst tre RSID:er (Report Suite ID) per kund. |
| **Ändra till hur Adobe Analytics hanterar A4T-data som samlats in via Experience Edge** | 31 mars 2022 | Den 7 mars 2022 ändrade Analytics hur det hanterar vissa anrop från Experience Edge som innehåller Target-innehåll som är avsett för A4T-rapportering (Analytics for Target). Från och med den 7 mars ändras alla träffar med A4T-rapportinnehåll så att de inte behandlas som sidvy eller länkhändelser. Startar **31 mars 2022**, är logiken mer selektiv så att standardhändelserna för sidvisning och klickning inte ändras. Framöver är de enda händelser som ändras endast personliga anrop som bara har A4T-innehåll. |
| **Uppdatering till webbläsarkrypteringsmetoder som stöds av vissa kunder** | 28 mars 2022 | Adobe erbjuder två krypteringsnivåer för att uppfylla olika kundbehov när det gäller säkerhet vid datainsamling från första part. På **23 juni 2022** support tas bort för vissa HTTPS-krypteringsalgoritmer, så kallade ciphers, för kunder med säkerhetsnivån inställd på Hög. Den här åtgärden innebär att vissa äldre operativsystem inte längre kan skicka data till Analytics eftersom de inte har stöd för moderna krypteringsmetoder. Kunder som använder standardsäkerhetsinställningarna för chiffrering påverkas inte. Alla kunder som för närvarande använder inställningen &quot;Hög&quot; har redan kontaktats direkt. Här finns en detaljerad lista över de cifer som påverkas av denna ändring. |
| **Pausa äldre schemalagda rapporter** | 12 april 2022 | Effektivt **20 april 2022** kommer Adobe att pausa alla schemalagda rapporter som har ett skapandedatum som är större än två år (skapat före den 31 januari 2020). Inga rapporter eller data tas bort. Endast rapporter som identifieras som äldre än två år pausas och inga ytterligare schemalagda rapporter skickas. Läs mer |
| **2022 ISO-regionuppdateringar** | 11 mars 2021 | Adobe planerar att genomföra 2022 ISO-regionsuppdateringar på **10 juni 2022**. Efter den här versionen förväntas mindre uppdateringar av geoinformation visas. |
| **Pausa tidigare schemalagda Report Builder-aktiviteter** | 12 april 2022 | Effektivt **20 april 2022** kommer Adobe att göra uppehåll i alla schemalagda uppdrag i Report Builder som skapades för mer än två år sedan. Den här pausen gäller i synnerhet alla uppgifter som skapats före den 31 januari 2020. Inga uppgifter, arbetsböcker eller data tas bort. Uppgifter som identifieras som äldre än två år pausas dock och inga ytterligare schemalagda aktiviteter skickas. Läs mer |
| **Tillåtelselista EOL-tillägget för OAuth/JWT-integreringar med äldre Analytics upphör att gälla** | 14 januari 2022 | På **25 maj 2022**, [Analytics 1.3 API, 1.4 SOAP API och Legacy Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) Tillägget tillåtelselista upphör att gälla. Den har erbjudits kunder som använder äldre [!DNL Adobe Analytics] OAuth/JWT-autentiseringsuppgifter ger ytterligare tid att migrera sina klientintegreringar till [Adobe IMS-autentiseringsuppgifter](https://developer.adobe.com/console). Detta påverkar (men är inte begränsat till) [!DNL Adobe Analytics Livestream] och [!DNL Adobe Campaign] kunder som inte har slutfört sina nödvändiga IMS-migreringar. Kunder som för närvarande använder äldre [!DNL Analytics] OAuth/JWT-inloggningsuppgifter via tillägget tillåtelselista och som inte slutfört migreringen till IMS-inloggningsuppgifter senast den 25 maj 2022 förlorar åtkomst till Adobes tjänster. Privatpersoner kan referera till dessa [instruktioner](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) när deras klientprogram migreras till IMS-autentiseringsuppgifter. [!DNL Campaign] kan man kontakta Adobe för att uppgradera till den senaste versionen av [!DNL Campaign]. |
| **EOL för[!DNL Reports & Analytics]** | 4 januari 2022 | Effektivt **31 december 2023** kommer Adobe att upphöra med sin verksamhet [!DNL Reports & Analytics] och tillhörande rapporter och funktioner. Rapporterna, visualiseringarna och den underliggande tekniken som ligger till grund för [!DNL Reports & Analytics] inte längre uppfyller Adobe teknikstandarder. Mest [!DNL Reports & Analytics] funktioner finns i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Sedan Analysis Workspace släpptes 2015 har [!DNL Reports & Analytics] funktionaliteten och funktionerna har flyttats till Analysis Workspace och ett tröskelvärde för arbetsflödets paritet har uppnåtts. [Detta meddelande](https://spark.adobe.com/page/6WnF8JK6IRDhf/) förklarar processen för att avsluta livscykeln. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement {#appm}

De senaste uppdateringarna av AppMeasurement-versioner (version 2.2.4) finns i [Versionsinformation om AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=en).

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] versionsinformation](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)
