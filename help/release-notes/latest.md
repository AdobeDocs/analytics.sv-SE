---
title: Aktuella versionsinformation för Adobe Analytics
description: Visa den aktuella versionsinformationen för Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 627a813d0d5595521d72f0cf832b3a1ceb7655f8
workflow-type: tm+mt
source-wordcount: '1211'
ht-degree: 0%

---

# Aktuell versionsinformation för Adobe Analytics (april 2024)

**Senaste uppdatering**: 17 april 2024

Versionsanteckningarna gäller den 17 april 2024 till maj. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Direktuppspelningsmedia: Skicka Roku-data till Adobe Experience Platform Edge Network** | Nu när [installera Media Analytics med Experience Platform Edge](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge)kan du använda Adobe Experience Platform Roku SDK för att skicka direktuppspelningsmediedata till Adobe Experience Platform. |  | 12 april 2024 |
| **Förbättrat arbetsflöde för Web SDK-migrering** | Adobe Experience Platform Data Collection mappar nu automatiskt många fält från dataobjektet direkt till Adobe Analytics. Det förbättrade arbetsflödet ger följande fördelar:<ul><li>Det gör att din organisation kan migrera till Web SDK utan att behöva bekymra sig om att skapa eller följa en [!UICONTROL XDM schema]. Se [Variabelmappning för dataobjekt](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping) för mer information. (Fler dokumentationslänkar att följa)</li><li>När du har migrerat till Web SDK kan din organisation bättre migrera från Adobe Analytics till Customer Journey Analytics. Detta beror på att Web SDK möjliggör en smidigare migrering till Customer Journey Analytics.</li></ul> (Mer information om detta och andra migreringsalternativ kommer snart.) |  | April 2024 |
| **Förbättrade behörigheter för projekt [!UICONTROL Workspace] komponenter** | Tidigare kunde användare B redigera projektet om de delade ett projekt med en annan användare (Användare B) och gav användare B redigeringsåtkomst till projektet. Användare B kan dock inte redigera [!UICONTROL Quick Segments] inbäddad i projektet. Begränsningen har nu tagits bort - Användare B kan redigera [!UICONTROL Quick Segments] och andra komponenter som bara är för projekt och som är inbäddade i det delade projektet. |  | 17 april 2024 |
| **Använd samma molnkonton för [!UICONTROL Data Feeds], [!UICONTROL Data Warehouse]och[!UICONTROL Classification sets]** | Molnkonton och platser som du skapar kan nu användas för att exportera data (med [!UICONTROL Data Feeds] och [!UICONTROL Data Warehouse]) och importera data (med [!UICONTROL Classification sets]).<p> **Ändringar när konton konfigureras:** Användarna kan [Konfigurera molnimport- och exportkonton](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts) och [Konfigurera platser för molnimport och -export](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-locations) som kan användas för något av följande ändamål:<ul><li>Importera data med [!UICONTROL Classification sets]</li><li>Exportera data med [!UICONTROL Data Feeds]</li><li>Exportera data med [!UICONTROL Data Warehouse].</li></ul><p>**Ändringar när konton hanteras**: Användare kan använda [Platser](https://experienceleague.adobe.com/en/docs/analytics/components/locations/locations-manager) sida (under [!UICONTROL Components] > Locåtgärder) för att visa och hantera alla konton och platser som de skapar, oavsett var de skapades. <p>Tidigare [!UICONTROL Locations] sidan används bara på konton som skapats för import av data med [!UICONTROL Classification sets].</p> | | 17 april 2024 |
| **Administratörer kan hantera alla platser och konton i sin organisation** | Ett nytt alternativ på fliken Platser (på sidan Komponenter > Platser) gör att administratörer kan visa och hantera alla platser i organisationen.<p>Ett nytt alternativ på [Plats](https://experienceleague.adobe.com/en/docs/analytics/components/locations/locations-manager) På fliken Konton (på sidan Komponenter > Platser) kan administratörer visa och hantera alla konton i organisationen.</p> <p>Tidigare kunde administratörer bara visa och hantera de platser och konton som de skapade.</p> |  | 17 april 2024 |
| **Ökning av standardtröskelvärden för låg trafik** | I **mitten av april 2024** kommer Adobe att börja öka standardrapporteringsprogrammets lågtrafiktrösklar enligt följande: ![lågtrafiktrösklar](assets/thresholds.png) Detta påverkar endast variabler som för närvarande ligger under de nya tröskelvärdena. Dessa ändringar kommer att göras stegvis, och vi förväntar oss att arbetet ska vara slutfört av **slutet av maj**. När dessa ökningar introduceras kan du märka förändringar för variabler med hög kardinalitet:<ul><li>Fler dimensionsvärden kan vara tillgängliga för rapportering.</li><li>Segment och beräknade värden kan innehålla mer data.</li><li>Virtuella rapportsviter baserade på segment kan innehålla mer data.</li><li>Export av klassificeringar kan innehålla mer data.</li></ul> | Mid April, 2024 | 31 maj 2024 |
| **Activity Map använder färre serveranrop till Web SDK** | För närvarande räknas länkarhändelser i Activity Map som sina egna händelser och medför extra kostnader. <p>Den här förbättringen tar några länkhändelser och paketerar dem i nästa träff, ungefär som hur händelser hanteras av AppMeasurementet.</p> |  | 1 maj 2024 |

{style="table-layout:auto"}

## Korrigeringar i Adobe Analytics

* Åtgärdade följande klassificeringsproblem: AN-343439; AN-343503; AN-343504; AN-343986; AN-344262; AN-344564; AN-345 204; AN-345234
* Åtgärdade följande fel i klassificeringsregelbyggaren: AN-341488; AN-342501; AN-345751
* Åtgärdade följande problem med intelligenta aviseringar: AN-343466;
* Åtgärdade följande segmenteringsproblem: AN-342313
* Åtgärdade följande problem med Data Warehouse: AN-344292
* Åtgärdade följande dataflödesproblem: AN-339545; AN-340092; AN-342124; AN-342862; AN-343737; AN-344035; AN-344 329; AN-344703; AN-344721; AN-344940; AN-345180; AN-345196; AN-345225; AN-3452 36; AN-345326; AN-345631; AN-345659
* Åtgärdade följande problem med datakällor: AN-343541
* Följande Analysis Workspace-problem har korrigerats: AN-336303; AN-336472; AN-338422; AN-338556; AN-339718; AN-340147; AN-3403 01; AN-340421; AN-340951; AN-341172; AN-342905; AN-342909; AN-343448; AN-34357 0; AN-344050; AN-344182; AN-344763; AN-344768;
* Åtgärdade följande problem med Analytics Admin: AN-342519; AN-342523; AN-343623; AN-343882; AN-344237; AN-344829; AN-34 5235;
* Åtgärdade följande A4T-problem: AN-341619; AN-344402
* Åtgärdade följande problem med mobilappar: AN-342010

### Korrigeringar för andra analyser

AN-336099; AN-337474; AN-337993; AN-339718; AN-339901; AN-340014; AN-341356; AN-4 343021; AN-343102; AN-343353; AN-343416; AN-340014; AN-344037; AN-344525; AN-3 45737

## Viktiga meddelanden för Adobe Analytics-administratörer {#admin}

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **13 månaders förfallodatum för sparat`cust_visids`** | 20 mars 2024 | En kommande version av motorn för Analytics Hit processing, som är avsedd för april eller maj, kommer att börja tillämpa en 13-månaders förfallotid för sparade `cust_visids`. Om rapportsviten har Aktivera besökarinställning aktiverat, används den här inställningen för att hitta `cust_visid` för `visid_high/visid_low value` med nej `cust_visid` på träffen. Mappningen av en `cust_visid` för `visid_high/visid_low`. I den här versionen, om minst 13 månader har gått sedan `visid_high/visid_low` har haft en `cust_visid` vid en träff förfaller mappningen. |
| **Tillägg för Adobe API-objektmedlemmar** | 17 januari 2024 | Adobe kan när som helst och utan föregående meddelande eller ändringar i versionshanteringen lägga till medlemmar för begäran och svar (namn/värde-par) i befintliga API-objekt. Adobe rekommenderar att du läser API-dokumentationen för alla tredjepartsverktyg som du integrerar med våra API:er så att sådana tillägg ignoreras vid bearbetningen, om de inte tolkas. Om de implementeras på rätt sätt är sådana tillägg fasta ändringar för implementeringen. Adobe tar inte bort parametrar eller lägger till obligatoriska parametrar utan att först skicka standardmeddelanden via versionsinformation. |

{style="table-layout:auto"}

## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Migrering till autentiseringsuppgifter för Adobe I/O OAuth Server-till-Server** | 11 maj 2023 | Adobe Analytics API- och LiveStream-kunder som använder Adobe I/O JWT-autentiseringsuppgifter måste migrera till Adobe I/O OAuth Server-till-Server-autentiseringsuppgifter genom att **1 januari 2025**. Adobe I/O tillåter inte att nya JWT-autentiseringsuppgifter skapas från och med 1 maj 2024. Kunder som använder JWT måste skapa en ny OAuth Server-till-Server-autentiseringsuppgift eller migrera sina befintliga JWT-autentiseringsuppgifter till en OAuth Server-till-Server-autentiseringsuppgift. Kunderna måste även uppdatera sina klientprogram för att kunna använda de nya autentiseringsuppgifterna för OAuth Server-till-Server. <ul><li>[Migrerar från JWT-autentiseringsuppgifter (Service Account)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementeringsguide för nya och gamla program med OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Använda de nya autentiseringsuppgifterna för OAuth Server-till-Server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Vanliga frågor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

De senaste uppdateringarna av AppMeasurement (version 2.26.0) finns på [AppMeasurement för versionsinformation för JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Relaterade resurser

* [Information om föregående version för 2023](/help/release-notes/2023.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html)
