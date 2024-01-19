---
title: Aktuella versionsinformation för Adobe Analytics
description: Visa den aktuella versionsinformationen för Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '1069'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Analytics (januari 2024)

**Senaste uppdatering**: 10 januari 2024

Versionsinformationen omfattar releaseperioden januari 2024-13 februari 2024. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Data Warehouse** | Följande förbättringar av Datan Warehouse är nu tillgängliga:<ul><li>När en begäran om Data Warehouse skapas kan användare nu göra begäranden tillgängliga för alla användare i organisationen genom att aktivera den nya växeln som kallas [!UICONTROL **Gör tillgänglig för användare i din organisation**].<p>Mer information finns i [Allmänna inställningar för begäran om Data Warehouse](/help/export/data-warehouse/create-request/dw-general-settings.md).</p></li><li>När systemadministratörer skapar eller hanterar destinationer för Data Warehouse-rapporter kan de nu visa konton och platser som har skapats av användare i organisationen genom att aktivera det anropade [!UICONTROL **Visa alla mål**].<p>Mer information finns i [Konfigurera ett rapportmål för en Data Warehouse-begäran](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).</p></li> | Ej tillämpligt | 10 januari 2024 |
| **Uppdateringar av visualisering av sammanfattning av nyckelmått** | När du använder visualisering av nyckelmätningssammanfattning kan datumintervallet för jämförelsen nu uppdateras automatiskt, beroende på om det alternativ för jämförelsedatumintervall du väljer är relativt till det primära datumintervallet eller fasta. [Läs mer](/help/analyze/analysis-workspace/visualizations/key-metric.md). | Ej tillämpligt | 17 januari 2024 |

{style="table-layout:auto"}

## Korrigeringar i Adobe Analytics

* Åtgärdade följande klassificeringsproblem: AN-314821; AN-326839; AN-332079; AN-332704; AN-332812; AN-332902; AN-332 975; AN-33300; AN-333023; AN-333033; AN-333174; AN-333910; AN-334097; AN-3342 08; AN-334373; AN-334439; AN-334698; AN-334838; AN-334848; AN-334987; AN-33504 6; AN-335082; AN-335202; AN-335203; AN-335254; AN-335322; AN-335552; AN-33591; AN-335603; AN-335610; AN-335617; AN-335699; AN-335891; AN-335901; AN-336063; AN-336072; AN-336193; AN-336479; AN-336684; AN-336801; AN-337370; AN-337398
* Åtgärdade följande fel i klassificeringsregelbyggaren: AN-332390; AN-332573; AN-332718; AN-332927; AN-333248; AN-333953; AN-33 4647; AN-334736; AN-334910; AN-335642; AN-335683; AN-335811; AN-336033; AN-336 569; AN-336852; AN-336875; AN-336902; AN-337190;
* Åtgärdade följande A4T-problem: AN-334564; AN-336178;
* Åtgärdade följande problem med användning av serveranrop: AN-332568; AN-333105; AN-333167; AN-333983; AN-334209; AN-334278
* Åtgärdade följande problem med Datan Warehouse: AN-333010; AN-333076; AN-330227; AN-331580; AN-333350; AN-334291; AN-344 283; AN-334287; AN-334301; AN-334385; AN-334453; AN-334977; AN-335079; AN-3351 71; AN-335245; AN-335426; AN-335680; AN-335818; AN-336087; AN-337308;
* Åtgärdade följande dataflödesproblem: AN-332241; AN-332366; AN-332617; AN-332654; AN-332702; AN-332723; AN-333 014; AN-333166; AN-334037; AN-334125; AN-334211; AN-334216; AN-334235; AN-3349 76; AN-335158; AN-335368; AN-335408; AN-335468; AN-335471; AN-335528; AN-33559 6; AN-335662; AN-335733; AN-335883; AN-335894; AN-335968; AN-336098; AN-336192; AN-336243; AN-336659; AN-336977; AN-337117; AN-337219; AN-337262; AN-337393; AN -337462; AN-337854
* Följande Report Builder-problem har korrigerats: AN-335246; AN-336311;
* Följande Analysis Workspace-problem har korrigerats: AN-323760; AN-324191; AN-324913; AN-330126; AN-332808; AN-333168; AN-3333 82; AN-334839; AN-336040; AN-337043;

### Andra korrigeringar

AN-323975; AN-325383; AN-325809; AN-326787; AN-331611; AN-331818; AN-332124; AN-3 332272; AN-332911; AN-333070; AN-33302; AN-333377; AN-333904; AN-333928; AN-33 33968; AN-334056; AN-334099; AN-334191; AN-334207; AN-334776; AN-335206; AN-333 5294; AN-335320; AN-335394; AN-335443; AN-335967; AN-336099; AN-337452; AN-377 463

## Viktiga meddelanden för Adobe Analytics-administratörer {#admin}

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| Tillägg för Adobe API-objektmedlemmar | 17 januari 2024 | Adobe kan lägga till valfria fråge- och svarsmedlemmar (namn/värde-par) i befintliga API-objekt utan föregående meddelande eller ändringar i versionshanteringen. Sådana tillägg bör vara fasta ändringar för implementeringen. Adobe rekommenderar att du läser API-dokumentationen för alla tredjepartsverktyg som du integrerar med våra API:er så att sådana tillägg ignoreras vid bearbetningen om de inte tolkas. Adobe tar inte bort parametrar eller lägger till obligatoriska parametrar utan att först skicka standardmeddelanden via versionsinformation. |
| `getPageLoadTime` insticksprogrammet är inaktuellt | 10 januari 2024 | Detta plugin-program stöds inte längre. I koden används metoden performance.timing som (enligt MDN) har [inaktuell](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming). Arbetet med ett uppdaterat plugin-program har startats. |

{style="table-layout:auto"}

## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **EOL för[!DNL Reports & Analytics]** | 10 januari 2024 | Effektivt **17 januari 2024**, Adobe upphör [!DNL Reports & Analytics] och tillhörande rapporter och funktioner. Rapporterna, visualiseringar och underliggande teknik som ger kraft åt [!DNL Reports & Analytics] inte längre uppfyller Adobe teknikstandarder. Mest [!DNL Reports & Analytics] funktioner finns i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Sedan Analysis Workspace släpptes 2015 har [!DNL Reports & Analytics] funktionaliteten och funktionerna har flyttats till Analysis Workspace och ett tröskelvärde för arbetsflödets paritet har uppnåtts. [Detta meddelande](https://spark.adobe.com/page/6WnF8JK6IRDhf/) förklarar processen för att avsluta livscykeln.<p>Den 17 januari 2024 avslutade vi många av de associerade funktionerna för rapporter och analys, inklusive, men inte begränsat till, schemalagda rapporter, dataextrakt och DL-rapporter. Efter den 17 januari 2024 skickades inga schemalagda rapporter längre. Dessutom kan du inte längre schemalägga framtida rapporter från och med den 17 januari 2024. |
| **EOL för [!UICONTROL Publishing Lists] funktion** | 10 januari 2024 | Som en del av ledningscentralen för rapporter och analyser [!UICONTROL Publishing Lists] nått slutet av livscykeln den **17 januari 2024**. Du kan inte längre skapa nya eller komma åt befintliga [!UICONTROL Publishing Lists] att skicka eller schemalägga [!UICONTROL Analysis Workspace] projekt. |
| **EOL för Data Workbench** | 2 januari 2024 | Adobe-Data Workbench som upphör att vara listat, effektiv **31 december 2023**. Se [Datans Workbench meddelande om att livscykeln upphör](https://express.adobe.com/page/GSu6oKOD88GAj/) för mer information. Kontakta din organisations kontoansvarige på Adobe om du har frågor. |
| **Migrering till autentiseringsuppgifter för Adobe I/O OAuth Server-till-Server** | 11 maj 2023 | Adobe Analytics API- och LiveStream-kunder som använder Adobe I/O JWT-autentiseringsuppgifter måste migrera till Adobe I/O OAuth Server-till-Server-autentiseringsuppgifter genom att **1 januari 2025**. Adobe I/O tillåter inte att nya JWT-autentiseringsuppgifter skapas från och med 1 maj 2024. Kunder som använder JWT måste skapa en ny OAuth Server-till-Server-autentiseringsuppgift eller migrera sina befintliga JWT-autentiseringsuppgifter till en OAuth Server-till-Server-autentiseringsuppgift. Kunderna måste även uppdatera sina klientprogram för att kunna använda de nya autentiseringsuppgifterna för OAuth Server-till-Server. <ul><li>[Migrerar från JWT-autentiseringsuppgifter (Service Account)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementeringsguide för nya och gamla program med OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Använda de nya autentiseringsuppgifterna för OAuth Server-till-Server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Vanliga frågor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

De senaste uppdateringarna av AppMeasurement (version 2.25.0) finns på [AppMeasurement för versionsinformation för JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Relaterade resurser

* [Information om föregående version för 2023](/help/release-notes/2023.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html)
