---
title: Visa den aktuella versionsinformationen för Adobe Analytics
description: Versionsinformation om den senaste analysen
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 16e74d5374fd761af973ca7af9dd1c4022010911
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 7%

---

# Senaste versionsinformation för Adobe Analytics

>[!IMPORTANT]
>
>Versionsinformationen innehåller information om förhandsversioner som kan ändras.

**16 februari 2022**

Läs om de senaste versionsuppdateringarna för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html). Få den senaste självhjälpsdokumentationen, självstudiekurserna och kurserna om Experience League.

## Nya funktioner i Adobe Analytics {#aa-features}

| Funktion | Beskrivning | Måldatum |
| ----------- | ---------- | ------- |
| Inga nya funktioner den här månaden | Ej tillämpligt | Se [Allmän tillgänglighet](https://experienceleague.adobe.com/docs/analytics/technotes/releases.html?lang=en) |

{style=&quot;table-layout:auto&quot;}

## Korrigeringar i Adobe Analytics

* Ett antal problem med [!UICONTROL Server call usage]. (AN-279134, AN-279878, AN-280802, AN-279097, AN-191284, AN-269720)
* Korrigerade ett problem som medförde att Data warehouse exporterade tomma CSV-filer. (AN-280291)
* Korrigerade ett problem som gjorde att målgruppsnamn inte fylldes i för nyligen använda segment. (AN-279715)
* Ett problem med långsamma rapporteringstider har korrigerats. (AN-280055)
* Problem med klassificeringar som inte klassificerar alla dimensionsobjekt har korrigerats. (AN-280031)


### Ytterligare korrigeringar i Adobe Analytics

AN-268093, AN-273820, AN-274435, AN-274904, AN-275356, AN-275947, AN-276160, AN-0 276258, AN-276705, AN-277051, AN-277957, AN-278693, AN-278882, AN-279000, AN-2 79046, AN-279362, AN-279460, AN-279488, AN-279554, AN-279572, AN-279663, AN-27 9755, AN-279825, AN-280002, AN-280013, AN-280019, AN-280033, AN-280086, AN-280 232, AN-280264, AN-280288, AN-280342, AN-280347, AN-280360, AN-280370, AN-2807 24, AN-280830, AN-280941, AN-281353, AN-281424, AN-281533


## Viktiga meddelanden för [!DNL Analytics]-administratörer

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| Tillåtelselista EOL-tillägget för OAuth/JWT-integreringar med äldre Analytics upphör att gälla | 14 januari 2022 | På **25 maj 2022**, [Analytics 1.3 API, 1.4 SOAP API och Legacy Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) Tillägget tillåtelselista upphör att gälla. Den har erbjudits kunder som använder äldre [!DNL Adobe Analytics] OAuth/JWT-autentiseringsuppgifter ger ytterligare tid att migrera sina klientintegreringar till [Adobe IMS-autentiseringsuppgifter](https://developer.adobe.com/console). Detta påverkar (men är inte begränsat till) [!DNL Adobe Analytics Livestream] och [!DNL Adobe Campaign] kunder som inte har slutfört sina nödvändiga IMS-migreringar. Kunder som för närvarande använder äldre [!DNL Analytics] OAuth/JWT-autentiseringsuppgifter via tillägget tillåtelselista och som inte slutfört migreringen till IMS-autentiseringsuppgifter senast den 25 maj 2022 förlorar åtkomsten till Adobes tjänster. Privatpersoner kan referera till dessa [instruktioner](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) när deras klientprogram migreras till IMS-autentiseringsuppgifter. [!DNL Campaign] kan man kontakta Adobe för att uppgradera till den senaste versionen av [!DNL Campaign]. |
| EOL för [!DNL Reports & Analytics] | 4 januari 2022 | Effektivt **31 december 2023** kommer Adobe att upphöra med sin verksamhet [!DNL Reports & Analytics] och tillhörande rapporter och funktioner. Rapporterna, visualiseringarna och den underliggande tekniken som ligger till grund för [!DNL Reports & Analytics] inte längre uppfyller Adobe teknikstandarder. Mest [!DNL Reports & Analytics] funktioner finns i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Sedan Analysis Workspace släpptes 2015 har [!DNL Reports & Analytics] funktionaliteten och funktionerna har flyttats till Analysis Workspace och ett tröskelvärde för arbetsflödets paritet har uppnåtts. [Detta meddelande](https://spark.adobe.com/page/6WnF8JK6IRDhf/) förklarar processen för att avsluta livscykeln. |
| SFTP-uppgradering (Secure File Transfer Protocol) | 13 januari 2022 | På **2 maj 2022**, [!DNL Adobe Analytics] kommer att uppgradera sina SFTP-tjänster (Secure File Transfer Protocol) för att ge bättre säkerhet för filöverföringar. Den här ändringen innebär att vissa SFTP-klientkonfigurationer inte längre stöds. Vi kommer även att lägga till några anslutningsalternativ som är tillgängliga via **1 mars 2022**. Detta påverkar endast data som skickas till eller hämtas från Adobe Analytics med SFTP. FTP-protokollet påverkas inte. För att undvika avbrott i tjänsten bör du se till att dina SFTP-klienter (kod, verktyg, tjänster) följer de detaljerade ändringarna [här](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html). |

## AppMeasurement {#appm}

De senaste uppdateringarna av AppMeasurement-versioner (version 2.2.4) finns i [Versionsinformation om AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=en).

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] versionsinformation](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)

