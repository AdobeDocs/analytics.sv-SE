---
title: Aktuella versionsinformation för Adobe Analytics
description: Visa den aktuella versionsinformationen för Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7dd42948073b56a33c1d00f9b4292d1cc3416470
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Analytics (september 2024)


**Senast uppdaterad**: 11 september 2024

Versionsinformationen gäller från 11 september till början av oktober. Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya funktioner eller förbättringar {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
|--- | --- | --- | --- |
| **Ytterligare information i kolumnen Används i i den beräknade metriska hanteraren och segmenthanteraren** | Kolumnen &quot;Används i&quot; i den beräknade metriska hanteraren och segmenthanteraren innehåller följande nya rapporteringsområden:<ul><li>**Report Builder**: Visar antalet beräknade mått eller segment som används i Report Builder.</li><li>**Ad hoc-komponenter**: Visar antalet ad hoc-beräknade mått eller ad hoc-segment som används i projekt. Dessa ad hoc-beräknade värden och segment (kallas annars&quot;snabbberäknade mätvärden&quot; och&quot;snabbsegment&quot;) kan endast användas i det projekt där de skapades, så de rapporteras separat från rapportområdet&quot;Projekt&quot; i kolumnen&quot;Används i&quot;.</li></ul>Mer information finns i [Beräknad måtthanterare](https://experienceleague.adobe.com/en/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager) och [Segmenthanterare](https://experienceleague.adobe.com/en/docs/analytics/components/segmentation/segmentation-workflow/seg-manage). |  | 11 sept 2024 |
| **Activity Map v3-tillägg** | Tillägget Activity Map v3 är nu tillgängligt. Om du har v2-tillägget installerat avinstallerar du det innan du installerar v3-tillägget. Navigera till **[!UICONTROL Tools]** > **[!UICONTROL Activity Map]** för att hämta den senaste versionen av tillägget. |  | 3 sept 2024 |


## Korrigeringar i Adobe Analytics

A4T: AN-355736
Activity Map: AN-353779
Analysis Workspace: AN-348485; AN-349693; AN-357247
Mobilappen Analytics: AN-352645
Klassificeringar: AN-355636; AN-355651; AN-355753; AN-356005; AN-356439; AN-356540; AN-356577; AN-356622
Enhetsövergripande analys: AN-355138
Dataflöden: AN-356258; AN-357133
Data Warehouse: AN-339292; AN-353807
Exportplatser: AN-356912
Sekretess-API: AN-352420
Report Builder: AN-352555; AN-354316
Schemalagda projekt: AN-355971
Segmentering: AN-352095;
Målrapportering: AN-355748

Andra korrigeringar: AN-349698; AN-349880; AN-354860; AN-355355; AN-356289;

## Viktiga meddelanden för Adobe Analytics-administratörer {#admin}

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **13-månaders förfallodatum för sparad`cust_visids`** | 20 augusti 2024 | Den 20 augusti 2024 **-utgåvan av motorn för bearbetning av analysträffar tvingar fram ett 13-månaders förfallodatum för sparad `cust_visids`.** Om rapportsviten har Aktivera besökarinställning aktiverat, används den här inställningen för att hitta `cust_visid` för en `visid_high/visid_low value` utan `cust_visid` i träffen. Tidigare var mappningen av en `cust_visid` för en `visid_high/visid_low` inte giltig. Om 13 månader eller mer har gått sedan `visid_high/visid_low` fick en `cust_visid` för en träff i den här versionen upphör mappningen att gälla. |
| **Ytterligare implementeringsinformation i XDM-fält mappas automatiskt** | 11 september 2024 | När du använder Adobe Experience Platform Edge Network för att skicka data till Adobe Analytics mappas XDM-fälten `xdm.implementationdetails.name` och `xdm.implementationdetails.environment` nu alltid till kontextdatavariabler `c.a.x.implementationdetails.name` och `c.a.x.implementationdetails.environment`. Tidigare hindrade vissa scenarier dessa värden från att fyllas i. Justera eventuella relevanta bearbetningsregler för att passa tillgängligheten för dessa värden. |

{style="table-layout:auto"}

## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **EOL för Adobe Analytics API (version 1.4)** | 17 juli 2024 | Den **12 augusti 2026** kommer följande API-tjänster för Analytics Legacy att sluta fungera och de kommer att stängas, och aktuella integreringar som skapats med dessa tjänster kommer att sluta fungera:<ul><li>Adobe Analytics API (version 1.4)</li><li>Adobe Analytics WSSE-autentisering</li></ul><p>Integreringar som använder Adobe Analytics API (version 1.4) måste migrera till [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/) medan WSSE-integreringar måste migrera till ett OAuth-baserat autentiseringsprotokoll i [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Se [Vanliga frågor om Adobe Analytics 1.4 API EOL ](/help/admin/c-admin-api/c-admin-14-api-eol.md) för svar på vanliga frågor och ytterligare vägledning.</p> |
| **Migrering till autentiseringsuppgifter för Adobe I/O OAuth Server-till-Server** | 11 maj 2023 | Adobe Analytics API- och LiveStream-kunder som använder Adobe I/O JWT-autentiseringsuppgifter måste migrera till autentiseringsuppgifterna för Adobe I/O OAuth Server-till-Server senast **1 januari 2025**. Adobe I/O tillåter inte att nya JWT-autentiseringsuppgifter skapas från och med 1 maj 2024. Kunder som använder JWT måste skapa en ny OAuth Server-till-Server-autentiseringsuppgift eller migrera sina befintliga JWT-autentiseringsuppgifter till en OAuth Server-till-Server-autentiseringsuppgift. Kunderna måste även uppdatera sina klientprogram för att kunna använda de nya autentiseringsuppgifterna för OAuth Server-till-Server. <ul><li>[Migrerar från JWT-autentiseringsuppgifter ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementeringsguide för nya och gamla program med OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Använder de nya autentiseringsuppgifterna för OAuth Server-till-server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Vanliga frågor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

De senaste uppdateringarna av AppMeasurement (version 2.26.0) finns i [AppMeasurementet för JavaScript versionsinformation](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Relaterade resurser

* [Information om föregående version för 2024](/help/release-notes/2024.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation om tilläggsprogrammet för direktuppspelad mediasamling](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html)
