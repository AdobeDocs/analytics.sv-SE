---
description: Det nya systemet för intelligenta aviseringar ger mer exakt kontroll över aviseringar och integrerar avvikelseidentifiering med varningssystemet.
title: Översikt över intelligenta aviseringar
feature: Alerts
role: User, Admin
exl-id: 49d47896-bf93-4960-b647-2765c935eb25
source-git-commit: 373a1ecffafdcefe3c7b60954f14c2f3a5ca386d
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 0%

---

# Översikt över intelligenta aviseringar

Med intelligenta aviseringar (eller bara &quot;aviseringar&quot;) i Adobe Analytics kan du få meddelanden direkt när onormala händelser inträffar i dina data.

Du kan ange att aviseringar ska utlösas baserat på avvikelsetrösklar, ändrade procentsatser eller specifika datapunkter. Varningar innehåller detaljerade kontroller som integreras med [avvikelseidentifiering](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) och aktiveras när du behöver dem som mest.

Med intelligenta aviseringar kan du:

* Skapa aviseringar baserade på avvikelser (tröskelvärdena 90 %, 95 %, 99 %, 99,75 % och 99,9 %, % förändring i %, över/under)
* Förhandsgranska hur ofta en varning utlöses
* Skicka aviseringar via e-post eller SMS med länkar till autogenererade Analysis Workspace-projekt
* Skapa&quot;staplade&quot; aviseringar som fångar in flera mätvärden i en enda avisering

I följande videofilm visas en grundläggande översikt över aviseringar: [Intelligenta aviseringar](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html) (5:34)

## Anomalsökning efter aviseringar

Om en varning använder avvikelseidentifiering varierar utbildningsperioden beroende på den granularitet som valts för registreringen.

* Månatlig granularitet: 15 månader + samma intervall förra året
* Veckogranularitet: 15 veckor + samma intervall förra året
* Daglig kornighet: 35 dagar + samma intervall förra året
* Timgranularitet: 336 timmar

Mer information finns i [Statistiska tekniker som används vid avvikelseidentifiering](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

## Skapa aviseringar

Mer information om hur du skapar aviseringar i Adobe Analytics finns i [Skapa aviseringar](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-builder.md).

>[!IMPORTANT]
>
>Om du använder tidsstämplade data för att skapa varningar kan det leda till att varningar utlöses felaktigt. Adobe rekommenderar att man använder data som inte är tidsstämplade för intelligenta aviseringar.

## Hantera aviseringar

Du kan hantera befintliga aviseringar i Varningshanteraren. Du kan utföra olika hanteringsåtgärder för varningar, som taggning, namnbyte, borttagning med mera.

Mer information om hur du hanterar befintliga aviseringar i Adobe Analytics finns i [Hantera aviseringar](/help/components/c-alerts/alert-manager.md).
