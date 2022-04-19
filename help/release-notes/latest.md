---
title: Versionsinformation om den senaste analysen
description: Se versionsinformationen för Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: c101a98e2d2d73fecc39054289f516411d7d529a
workflow-type: tm+mt
source-wordcount: '978'
ht-degree: 3%

---

# Aktuell versionsinformation för Adobe Analytics (april 2022)

**Senaste uppdatering**: 19 april 2022

* Versionsinformation om mars 2022 finns på [här](/help/release-notes/2022.md).

* För versionsinformation om Customer Journey Analytics går du till [här](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en).

* Versionsinformation om Media Analytics finns på [här](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=en).

* Läs om de senaste versionsuppdateringarna för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html). Få den senaste självhjälpsdokumentationen, självstudiekurserna och kurserna om Experience League.


| Funktion | Beskrivning | [Måldatum](releases.md) |
| ----------- | ---------- | ------- |
| Uppdateringar av Adobe Analytics landningssida | Uppdateringar till landningssidan för arbetsyta/rapporter och analyser som förbättrar användbarheten och underlättar navigeringen. [Läs mer](/help/analyze/landing.md) | 20 april 2022 |
| [!UICONTROL Next item] eller [!UICONTROL Previous item] Panelen Arbetsyta | The [!UICONTROL Next or Previous item] kan du utforska objekt som följer efter eller föregår ett önskat dimensionsobjekt. Använd den om du till exempel vill se nästa eller föregående sidor till en viss produktsida, marknadsföringskanal eller till och med enhetstyp. Den här panelen går längre än äldre rapportering nästa/föregående eftersom den gör att du kan titta på alla dimensioner och inte kräver någon ny implementering för att få insikter. | 20 april 2022 |
| [!UICONTROL Page Summary] Panelen Arbetsyta | The [!UICONTROL Page Summary] ger en djupgående analys av en sida du väljer. Det innehåller samma information som tidigare rapporter och analyser [!UICONTROL Page Summary] och mycket annat. | 20 april 2022 |

{style=&quot;table-layout:auto&quot;}

## Korrigeringar i Adobe Analytics

* Korrigerade ett fel i datafeeds, där start- och slutdatum ändrades automatiskt efter att datafeeden sparades när användargränssnittet för dataflöden skapades. Datumen uppdaterades automatiskt en dag. (AN-281262)

* Korrigerade ett problem som förhindrade förnyelse av schemalagda projekt via e-postlänk. (AN-283622)

### Ytterligare korrigeringar i Adobe Analytics

AN-274486; AN-279258; AN-279995; AN-280918; AN-281423; AN-282084; AN-282435; AN-283508; AN-283517; AN-283706; AN-283762; AN-283921; AN-284195; AN-284663; AN-284573; AN-284721; AN-284790; AN-284867; AN-284870; AN-284872; AN-284884; AN-284914; AN-284930; AN-284933; AN-284967; AN-284970; AN-285187; AN-285328; AN-285337; AN-285375; AN-285447; AN-285724; AN-285753; AN-285761;

## Viktiga meddelanden för Adobe Analytics-administratörer

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **CDA-berättigande (Cross-Device Analytics)** | 13 april 2022 | Effektivt **1 maj 2022**, ny implementering av [CDA](/help/components/cda/overview.md) begränsas till högst tre RSID:er (Report Suite ID) per kund. |
| **Ändra till hur Adobe Analytics hanterar A4T-data som samlats in via Experience Edge** | 31 mars 2022 | Den 7 mars 2022 ändrade vi hur vi hanterar vissa anrop från Experience Edge som innehåller målinnehåll som är avsett för A4T-rapportering (Analytics for Target). Från och med den 7 mars ändrades alla träffar med A4T-rapportinnehåll så att de inte behandlades som sidvy eller länkhändelser. Startar **31 mars 2022** har vi ändrat vår logik så att den är mer selektiv så att standardhändelserna för sidvisning och klickning inte ändras. Framöver kommer de enda händelser som kommer att ändras att vara personliga anrop som bara har A4T-innehåll. |
| **Uppdatering till webbläsarkrypteringsmetoder som stöds av vissa kunder** | 28 mars 2022 | Adobe erbjuder två krypteringsnivåer för att uppfylla olika kundbehov när det gäller säkerhet vid datainsamling från första part. På **23 juni 2022** vi kommer att ta bort stöd för vissa HTTPS-krypteringsalgoritmer, så kallade ciphers, för kunder med säkerhetsnivån inställd på&quot;Hög&quot;. Detta innebär att vissa äldre operativsystem inte längre kan skicka data till Analytics eftersom de inte har stöd för moderna krypteringsmetoder. Kunder som använder standardsäkerhetsinställningarna för chiffrering påverkas inte. Alla kunder som för närvarande använder inställningen &quot;Hög&quot; har redan kontaktats direkt. Här finns en detaljerad lista över de cifer som påverkas av denna ändring. |
| **Pausa äldre schemalagda rapporter** | 12 april 2022 | Effektivt **20 april 2022** kommer Adobe att pausa alla schemalagda rapporter som har ett skapandedatum som är större än två år (skapat före den 31 januari 2020). Inga rapporter eller data kommer att tas bort. Endast rapporter som identifieras som äldre än två år kommer att pausas och inga ytterligare schemalagda rapporter kommer att skickas. Läs mer |
| **2022 ISO-regionuppdateringar** | 11 mars 2021 | Adobe kommer att utföra 2022 ISO-regionsuppdateringar på **10 juni 2022**. Efter den här versionen förväntas mindre uppdateringar av geoinformation visas. |
| **Pausa tidigare schemalagda Report Builder-aktiviteter** | 12 april 2022 | Effektivt **20 april 2022** kommer Adobe att göra uppehåll i alla schemalagda uppdrag i Report Builder som skapades för mer än två år sedan. Den här pausen gäller i synnerhet alla uppgifter som skapats före den 31 januari 2020. Inga uppgifter, arbetsböcker eller data tas bort. Uppgifter som identifieras som äldre än två år kommer dock att pausas och inga ytterligare schemalagda aktiviteter kommer att skickas. Läs mer |
| **Tillåtelselista EOL-tillägget för OAuth/JWT-integreringar med äldre Analytics upphör att gälla** | 14 januari 2022 | På **25 maj 2022**, [Analytics 1.3 API, 1.4 SOAP API och Legacy Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) Tillägget tillåtelselista upphör att gälla. Den har erbjudits kunder som använder äldre [!DNL Adobe Analytics] OAuth/JWT-autentiseringsuppgifter ger ytterligare tid att migrera sina klientintegreringar till [Adobe IMS-autentiseringsuppgifter](https://developer.adobe.com/console). Detta påverkar (men är inte begränsat till) [!DNL Adobe Analytics Livestream] och [!DNL Adobe Campaign] kunder som inte har slutfört sina nödvändiga IMS-migreringar. Kunder som för närvarande använder äldre [!DNL Analytics] OAuth/JWT-autentiseringsuppgifter via tillägget tillåtelselista och som inte slutfört migreringen till IMS-autentiseringsuppgifter senast den 25 maj 2022 förlorar åtkomsten till Adobes tjänster. Privatpersoner kan referera till dessa [instruktioner](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) när deras klientprogram migreras till IMS-autentiseringsuppgifter. [!DNL Campaign] kan man kontakta Adobe för att uppgradera till den senaste versionen av [!DNL Campaign]. |
| **EOL för[!DNL Reports & Analytics]** | 4 januari 2022 | Effektivt **31 december 2023** kommer Adobe att upphöra med sin verksamhet [!DNL Reports & Analytics] och tillhörande rapporter och funktioner. Rapporterna, visualiseringarna och den underliggande tekniken som ligger till grund för [!DNL Reports & Analytics] inte längre uppfyller Adobe teknikstandarder. Mest [!DNL Reports & Analytics] funktioner finns i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Sedan Analysis Workspace släpptes 2015 har [!DNL Reports & Analytics] funktionaliteten och funktionerna har flyttats till Analysis Workspace och ett tröskelvärde för arbetsflödets paritet har uppnåtts. [Detta meddelande](https://spark.adobe.com/page/6WnF8JK6IRDhf/) förklarar processen för att avsluta livscykeln. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement {#appm}

De senaste uppdateringarna av AppMeasurement-versioner (version 2.2.4) finns i [Versionsinformation om AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=en).

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] versionsinformation](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)
