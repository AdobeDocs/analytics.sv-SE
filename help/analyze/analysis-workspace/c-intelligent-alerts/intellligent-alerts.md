---
description: Det nya systemet för intelligenta aviseringar ger mer exakt kontroll över aviseringar och integrerar avvikelseidentifiering med varningssystemet.
title: Översikt över intelligenta aviseringar
feature: Alerts
role: User, Admin
exl-id: 49d47896-bf93-4960-b647-2765c935eb25
source-git-commit: 2eff7656741bdba3d5d7d1f33e9261b59f8e6083
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 11%

---

# Översikt över intelligenta aviseringar

Intelligenta aviseringar ger mer exakt kontroll över aviseringar och integrerar avvikelseidentifiering med varningssystemet.

Här är en självstudiekurs om [Intelligenta aviseringar](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html) (5:34)

## Översikt

Den nya varningsfunktionen i Analysis Workspace ersätter den befintliga varningsfunktionen i Rapporter och analyser. Med intelligenta aviseringar kan du:

* Skapa aviseringar baserade på avvikelser (tröskelvärdena 90 %, 95 %, 99 %, 99,75 % och 99,9 %, % förändring i %, över/under)
* Förhandsgranska hur ofta en avisering utlöses
* Skicka aviseringar via e-post eller SMS med länkar till automatiskt genererade Analysis Workspace-projekt
* Skapa ”staplade” aviseringar som omfattar flera mätvärden i en enda avisering

Det finns fyra sätt att komma åt Varningsverktyget:

| Metod | Information |
| --- | --- |
| Gå direkt till Varningsverktyget | **[!UICONTROL Components]** > **[!UICONTROL Alerts]** |
| Använda kortkommandot i arbetsytan | `Ctrl + Shift + A` (Windows) eller `Cmd + Shift + A` (Mac) |
| Markera ett eller flera frihandsritningsobjekt | Högerklicka och välj **[!UICONTROL Create Alert from Selection]**. Då öppnas [!UICONTROL Alert Builder] och fyller i de värden och filter som används från tabellen i förväg. Du kan redigera varningen om det behövs. ![Skapa avisering från markering](assets/create-alert-from-selection.png) |
| Från en rapport från rapporter och analyser | Gå till  **[!UICONTROL More]** > **[!UICONTROL Add Alert]** . Detta öppnar varningsverktyget och fyller i relevanta mätvärden och filter från rapporten i förväg. Du kan redigera varningen om det behövs. ![Lägg till avisering](assets/add-alert.png) |

Procenttröskelvärdena är standardavvikelser. Exempel: 95 % = 2 standardavvikelser och 99 % = 3 standardavvikelser. Beroende på hur lång tid du väljer kan [olika modeller](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md) används för att beräkna hur långt bort (hur många standardavvikelser) varje datapunkt ligger från normen. Om du anger ett lägre tröskelvärde (till exempel 90 %) får du fler avvikelser än om du anger ett högre tröskelvärde (99,75 %).

>[!IMPORTANT]
>
>Om du använder tidsstämplade data för att skapa varningar kan det leda till att varningar utlöses felaktigt. Adobe rekommenderar att man använder data som inte är tidsstämplade för intelligenta aviseringar.

## Anomalsökning efter aviseringar

Om en varning använder avvikelseidentifiering varierar utbildningsperioden beroende på den granularitet som valts för registreringen.

* Månatlig granularitet: 15 månader + samma intervall förra året
* Veckogranularitet: 15 veckor + samma intervall förra året
* Daglig kornighet: 35 dagar + samma intervall förra året
* Timgranularitet: 336 timmar

Se [Statistiska tekniker som används vid avvikelseidentifiering](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md) för mer information.
