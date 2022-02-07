---
title: Visa den aktuella versionsinformationen för Adobe Analytics
description: Versionsinformation om den senaste analysen
source-git-commit: e19299820a03783215d8425b937a0935311d9e7b
workflow-type: tm+mt
source-wordcount: '861'
ht-degree: 5%

---


# Senaste versionsinformation för Adobe Analytics

**Januari 2022**

Läs om de senaste versionsuppdateringarna för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html). Få den senaste självhjälpsdokumentationen, självstudiekurserna och kurserna om Experience League.

## Nya funktioner i Adobe Analytics {#aa-features}

| Funktion | Beskrivning | Måldatum |
| ----------- | ---------- | ------- |
| Ej tillämpligt |  | Se [Allmän tillgänglighet](https://experienceleague.adobe.com/docs/analytics/technotes/releases.html?lang=en) |

{style=&quot;table-layout:auto&quot;}

## Korrigeringar i Adobe Analytics och Customer Journey Analytics {#aa-fixes}

* Korrigerade ett Analysis Workspace-problem där publikens ID saknades i dimensionsobjekt. (AN-262038) AN-279315)
* Ett problem som gjorde att användare inte kunde läsa in en sparad fil har åtgärdats [!DNL Target] projekt i Workspace. (AN-277461) AN-275825; AN-266397)
* Ett problem där icke-aktiverade funktioner visas i användargränssnittet har korrigerats. (AN-262006)
* Ett problem som uppstod när datumet ändrades med datumfältet i arbetsytan har korrigerats. Detta resulterade i [!UICONTROL End Time] ändras från 11.59 till 12.00. (AN-277269; AN-277481)
* Korrigerade ett problem som gjorde att segmentgränssnittet bröts när nya segment lades till i ett redan inläst segment. (AN-260827)
* Ett problem har korrigerats med att användare inte har åtkomst till delade arbetsyteprojekt. (AN-267529)
* Ett felmeddelande har lagts till som visar när ett rullande datumintervall har ett startdatum som är senare än slutdatumet. (AN-270488)
* Korrigerade olika datafeeds-problem. (AN-275876; AN-270512; AN-277284; AN-277290; AN-274893; AN-274606; AN-269651)
* Ett problem med datumintervall i diagram som ignorerar datumfilter i tabeller har korrigerats. (AN-263999)
* Korrigerade ett problem med att schemalagda rapporter skickades tidigt på grund av sommartid. (AN-276410) AN-276305)
* Ett problem med projektnedladdning till har korrigerats `.csv` filen misslyckades i arbetsytan. (AN-275834)

### Ytterligare korrigeringar i Adobe Analytics

AN-253294; AN-254976; AN-255377; AN-255561; AN-258550; AN-259336; AN-263935; AN-265094; AN-269441; AN-269486; AN-269855; AN-271166; AN-271588; AN-272088; AN-272249; AN-272859; AN-272873; AN-272885; AN-273229; AN-273913; AN-274237; AN-274472; AN-274491; AN-274619; AN-274766; AN-275248; AN-275259; AN-275271; AN-275315; AN-275388; AN-275418; AN-275597; AN-275643; AN-275650; AN-275651; AN-275675; AN-275682; AN-275704; AN-275711; AN-275796; AN-275834; AN-275923; AN-275941; AN-276044; AN-276125; AN-276157; AN-276397; AN-276597; AN-276789; AN-276834; AN-276861; AN-276870; AN-276963; AN-276975; AN-277000; AN-277044; AN-277093; AN-277200; AN-277215; AN-277271; AN-277281; AN-277362; AN-277419; AN-277492; AN-277498; AN-277533; AN-277619; AN-277675; AN-277681; AN-277767; AN-277805; AN-277810; AN-277818; AN-277875; AN-277933; AN-277988; AN-278105; AN-278115; AN-278122; AN-278192; AN-278407; AN-278437; AN-278559; AN-278604; AN-278610; AN-278709; AN-278835; AN-278849; AN-278881; AN-279067; AN-279103; AN-279111; AN-279219; AN-279237; AN-279312

## Viktiga meddelanden för [!DNL Analytics]-administratörer {#aa-notices}

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| Tillåtelselista EOL-tillägget för OAuth/JWT-integreringar med äldre Analytics upphör att gälla | 14 januari 2022 | På **25 maj 2022**, [Analytics 1.3 API, 1.4 SOAP API och Legacy Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) Tillägget tillåtelselista upphör att gälla. Den har erbjudits kunder som använder äldre [!DNL Adobe Analytics] OAuth/JWT-autentiseringsuppgifter ger ytterligare tid att migrera sina klientintegreringar till [Adobe IMS-autentiseringsuppgifter](https://developer.adobe.com/console). Detta påverkar (men är inte begränsat till) [!DNL Adobe Analytics Livestream] och [!DNL Adobe Campaign] kunder som inte har slutfört sina nödvändiga IMS-migreringar. Kunder som för närvarande använder äldre [!DNL Analytics] OAuth/JWT-autentiseringsuppgifter via tillägget tillåtelselista och som inte slutfört migreringen till IMS-autentiseringsuppgifter senast den 25 maj 2022 förlorar åtkomsten till Adobes tjänster. Privatpersoner kan referera till dessa [instruktioner](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) när deras klientprogram migreras till IMS-autentiseringsuppgifter. [!DNL Campaign] kan man kontakta Adobe för att uppgradera till den senaste versionen av [!DNL Campaign]. |
| EOL för [!DNL Reports & Analytics] | 4 januari 2022 | Effektivt **31 december 2023** kommer Adobe att upphöra med sin verksamhet [!DNL Reports & Analytics] och tillhörande rapporter och funktioner. Rapporterna, visualiseringarna och den underliggande tekniken som ligger till grund för [!DNL Reports & Analytics] inte längre uppfyller Adobe teknikstandarder. Mest [!DNL Reports & Analytics] funktioner finns i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Sedan Analysis Workspace släpptes 2015 har [!DNL Reports & Analytics] funktionaliteten och funktionerna har flyttats till Analysis Workspace och ett tröskelvärde för arbetsflödets paritet har uppnåtts. [Detta meddelande](https://spark.adobe.com/page/6WnF8JK6IRDhf/) förklarar processen för att avsluta livscykeln. |
| SFTP-uppgradering (Secure File Transfer Protocol) | 13 januari 2022 | På **2 maj 2022**, [!DNL Adobe Analytics] kommer att uppgradera sina SFTP-tjänster (Secure File Transfer Protocol) för att ge bättre säkerhet för filöverföringar. Den här ändringen innebär att vissa SFTP-klientkonfigurationer inte längre stöds. Vi kommer även att lägga till några anslutningsalternativ som är tillgängliga via **1 mars 2022**. Detta påverkar endast data som skickas till eller hämtas från Adobe Analytics med SFTP. FTP-protokollet påverkas inte. För att undvika avbrott i tjänsten bör du se till att dina SFTP-klienter (kod, verktyg, tjänster) följer de detaljerade ändringarna [här](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html). |
| _Global + Kina_ Typ av domänkontrollant | 22 november 2021 | _Global + Kina_ är en ny typ av regional datainsamling (RDC) som förenklar trafikflödet för globala kunder som använder [!UICONTROL China Performance Optimization Add-On Package]. Tidigare var du tvungen att bestämma om data skulle dirigeras till den kinesiska samlingens slutpunkt eller någon av de globala samlingens slutpunkter. Nu kan du välja den här domänkontrollanten *type* för att Adobe ska kunna fastställa den optimala samlingens slutpunkt baserat på användarens geolokalisering. |
| EOL för fullständig bearbetning i datakällor | 18 oktober 2021 | På **31 januari 2022** Adobe upphör med Hel bearbetning, vilket gör att användare kan importera träffdata offline till Analytics. Den här funktionen är tillgänglig via [API för massdatainmatning](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md). [Läs mer](https://experienceleague.adobe.com/docs/analytics/import/data-sources/data-types-and-categories/datasrc-fullproc-eol.html?lang=en) |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement {#appm}

De senaste uppdateringarna av AppMeasurement-versioner (version 2.2.4) finns i [Versionsinformation om AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=en).