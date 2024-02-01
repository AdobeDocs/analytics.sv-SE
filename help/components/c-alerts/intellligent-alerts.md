---
description: Det intelligenta larmsystemet ger mer exakt kontroll över varningar och integrerar avvikelseidentifiering med varningssystemet.
title: Intelligenta aviseringar
feature: Alerts
exl-id: 1b23211e-7632-4b33-a27d-c58b3bbbbab1
source-git-commit: be5a73347d417c8dc6667d4059e7d46ef5f0f5cd
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 6%

---

# Intelligenta aviseringar

Det intelligenta larmsystemet ger mer exakt kontroll över varningar och integrerar avvikelseidentifiering med varningssystemet.

Här är en videoöversikt:

>[!VIDEO](https://video.tv.adobe.com/v/25446/?quality=12)

## Översikt {#section_6AC8CA81DEA94E99B0F192B60D0FDF03}

>[!IMPORTANT]
>
>Intelligenta aviseringar är tillgängliga för Adobe [!DNL Analytics] Prime och Adobe [!DNL Analytics] Endast de ultimata kunderna.

Med intelligenta aviseringar kan du

* Skapa aviseringar baserade på avvikelser (tröskelvärdena 90 %, 95 %, 99 %, 99,75 % och 99,9 %, % förändring i %, över/under).
* Förhandsgranska hur ofta en avisering utlöses.
* Skicka aviseringar via e-post eller SMS med länkar till automatiskt genererade Analysis Workspace-projekt.
* Skapa ”staplade” aviseringar som omfattar flera mätvärden i en enda avisering.

Varningssystemets komponenter är: Varningsbyggaren, Varningshanteraren, Förhandsgranska varning och bättre sammanhangsberoende åtkomst för att skapa varningar. Det gamla varningssystemgränssnittet kommer inte längre att vara tillgängligt, men aviseringarna kommer att migreras. Vissa äldre varningsfunktioner [är inte längre tillgängliga](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/alerts.html).

Det finns tre sätt att komma åt Varningsverktyget:

* Genom att använda följande kortkommando i Analysis Workspace:

  `ctrl (or cmd) + shift + a`
* Genom att gå direkt till Varningsverktyget:  **[!UICONTROL Workspace]** > **[!UICONTROL Components]** > **[!UICONTROL New Alert]** .
* Genom att markera ett eller flera objekt på en frihandsritabell högerklickar och väljer du **[!UICONTROL Create Alert from Selection]**. Detta öppnar varningsgeneratorn och fyller i byggaren i förväg med lämpliga mått och filter som tillämpas från tabellen. Du kan sedan redigera varningen vid behov.

  ![](assets/create-alert-from-selection.png)


## Vanliga frågor: Hur aviseringar beräknas och aktiveras {#trigger}

Tröskelvärdena i % är standardavvikelser. Exempel: 95 % = 2 standardavvikelser och 99 % = 3 standardavvikelser. Beroende på hur lång tid du väljer kan [olika modeller](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md) används för att beräkna hur långt bort (hur många standardavvikelser) varje datapunkt ligger från normen. Om du anger ett lägre tröskelvärde (till exempel 90 %) får du fler avvikelser än om du anger ett högre tröskelvärde (99 %). Tröskelvärdena 99,75 % och 99,99 % infördes specifikt för timgranulariteten så att den inte skulle utlösa så många avvikelser som möjligt.

+++ Hur långt tillbaka går avvikelseavkänningen för att fastställa dataavvikelser?

Utbildningsperioden varierar beroende på vald granularitet. Se Statistiska tekniker som används i <a href="/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md">Analysidentifiering</a> för mer information. Här är en sammanfattning:

* Månadsvis = 15 månader + samma intervall förra året
* Vecka = 15 veckor + samma intervall förra året
* Dagligen = 35 dagar + samma intervall förra året
* Varje timme = 336 timmar

+++

+++ Om jag vill bli varnad för att bara få ett beteende eller bara ett visst beteende att försvinna, kan jag då använda avvikelsefunktionen eller måste jag använda ett absolut värde?

Om du använder det absoluta värdet utlöses fortfarande varningar på dips och spikes. Du kan inte isolera varningar för enbart dips eller bara spikes.

+++

+++ Kan jag konfigurera aviseringar så att de endast utlöses under vissa timmar på dygnet (till exempel kontorstid jämfört med icke-arbetstid)?

Nej.

+++

+++ Kan jag få en tabell med de &quot;förväntade värdena&quot; som utgör den streckade linjen, eller någon typ av utdata av vad dessa värden är?

Inte i Workspace, men du kan i Report Builder. Se [den här videon](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/exporting/report-builder/anomaly-detection-in-report-builder.html) om avvikelseidentifiering i Report Builder.

Tänk på att Report Builder använder mindre sofistikerade avvikelsedetekteringsmetoder. Den använder en fast 30-dagars utbildningsperiod, fast med 95 % intervall.

+++
