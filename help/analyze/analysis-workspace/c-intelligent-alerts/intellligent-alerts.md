---
description: Det nya systemet för intelligenta aviseringar ger mer exakt kontroll över aviseringar och integrerar avvikelseidentifiering med varningssystemet.
title: Översikt över intelligenta aviseringar
uuid: b9bf75ad-bb6f-49fe-8c55-355ea3c50a71
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Översikt över intelligenta aviseringar

Intelligenta aviseringar ger mer exakt kontroll över aviseringar och integrerar avvikelseidentifiering med varningssystemet.

[Intelligent Alerts på YouTube](https://www.youtube.com/watch?v=UVH9xr_2REA) (5:34)

## Översikt

Den nya varningsfunktionen och varningsfunktionen i Analysis Workspace ersätter den befintliga varningsfunktionen i Rapporter och analyser. Med intelligenta aviseringar kan du:

* Skapa aviseringar baserade på avvikelser (tröskelvärdena 90 %, 95 %, 99 %, 99,75 % och 99,9 %), % förändring, ovanför/nedanför)
* Förhandsgranska hur ofta en varning utlöses
* Skicka aviseringar via e-post eller SMS med länkar till automatiskt genererade Analysis Workspace-projekt
* Skapa&quot;staplade&quot; aviseringar som fångar in flera mätvärden i en enda avisering

Det finns fyra sätt att komma åt Varningsverktyget:

* Gå direkt till Varningsverktyget:  **[!UICONTROL Components]** > **[!UICONTROL Alerts]**
* Använda kortkommandot i Workspace: `Ctrl + Shift + A` (Windows) eller `Cmd + Shift + A` (Mac)
* Markera ett eller flera frihandsritabellobjekt, högerklicka och markera **[!UICONTROL Create Alert from Selection]**. Detta öppnar varningsverktyget och fyller i relevanta mått och filter från tabellen i förväg. Du kan redigera varningen vid behov.

   ![Skapa avisering från markering](assets/create-alert-from-selection.png)

* I en rapport från Rapporter och analyser går du till **[!UICONTROL More]** > **[!UICONTROL Add Alert]** . Detta öppnar varningsverktyget och fyller i relevanta mått och filter som tillämpas från rapporten. Du kan redigera varningen vid behov.

   ![Lägg till avisering](assets/add-alert.png)

Procenttröskelvärdena är standardavvikelser. Exempel: 95 % = 2 standardavvikelser och 99 % = 3 standardavvikelser. Beroende på hur lång tid du väljer används [olika modeller](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md) för att beräkna hur långt bort (hur många standardavvikelser) varje datapunkt ligger från normen. Om du anger ett lägre tröskelvärde (till exempel 90 %) får du fler avvikelser än om du anger ett högre tröskelvärde (99,75 %).

> [!IMPORTANT] Om du använder tidsstämplade data för att skapa varningar kan det leda till att varningar utlöses felaktigt. Adobe rekommenderar att man använder data som inte är tidsstämplade för intelligenta aviseringar.

## Analys av varningar

Om en varning använder avvikelseidentifiering varierar utbildningsperioden beroende på den granularitet som valts för registreringen.

* Månatlig granularitet: 15 månader + samma intervall förra året
* Kornighet varje vecka: 15 veckor + samma intervall förra året
* Daglig granularitet: 35 dagar + samma intervall förra året
* Timgranularitet: 336 timmar

Mer information finns i [Statistiska tekniker som används vid avvikelseidentifiering](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md) .
