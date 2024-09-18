---
description: Med varningar får du detaljkontroll över meddelanden och integrering med avvikelseidentifiering.
title: Översikt över aviseringar
feature: Alerts
exl-id: 1b23211e-7632-4b33-a27d-c58b3bbbbab1
source-git-commit: 815e50e30fa6a0bce1bf78f33843070f96f52de8
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---

# Översikt över aviseringar

Med varningar i Adobe Analytics kan du meddelas baserat på ändrade procentsatser eller specifika datapunkter.

Beroende på ditt Adobe Analytics-paket kan du även använda varningar som utlöses baserat på avvikelsetrösklar. Dessa aviseringar (kallas även&quot;Intelligent Alerts&quot;) ger detaljerade kontroller som kan integreras med [avvikelseidentifiering](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) och aktiveras när du behöver dem som mest.

Med varningar kan du:

* Förhandsgranska hur ofta en varning utlöses
* Skicka aviseringar via e-post eller SMS med länkar till autogenererade Analysis Workspace-projekt
* Skapa&quot;staplade&quot; aviseringar som fångar in flera mätvärden i en enda avisering
* Bygg aviseringar baserade på avvikelser (tröskelvärdena 90 %, 95 %, 99 %, 99,75 % och 99,9 %, förändring i %, över/under) (endast tillgängligt för Adobe Analytics-kunder med något av paketen Select, Prime eller Ultimate)

I följande videofilm visas en grundläggande översikt över aviseringar: [Varningar](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html) (5:34)

## Anomalsökning efter aviseringar

>[!NOTE]
>
>Det går bara att använda aviseringar med avvikelseidentifiering (kallas även _Intelligent Alerts_) för organisationer med ett Adobe Analytics Select-, Prime- eller Ultimate-paket.

Om en varning använder avvikelseidentifiering varierar utbildningsperioden beroende på den granularitet som valts för registreringen.

* Månatlig granularitet: 15 månader + samma intervall förra året
* Veckogranularitet: 15 veckor + samma intervall förra året
* Daglig kornighet: 35 dagar + samma intervall förra året
* Timgranularitet: 336 timmar

Mer information finns i [Statistiska tekniker som används vid avvikelseidentifiering](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

## Skapa aviseringar

Mer information om hur du skapar aviseringar i Adobe Analytics finns i [Skapa aviseringar](/help/components/c-alerts/alert-builder.md).

>[!IMPORTANT]
>
>Om du använder tidsstämplade data för att skapa varningar kan det leda till att varningar utlöses felaktigt. Adobe rekommenderar att du använder data som inte är tidsstämplade för aviseringar.

## Hantera aviseringar

Du kan hantera befintliga aviseringar i Varningshanteraren. Du kan utföra olika hanteringsåtgärder för varningar, som taggning, namnbyte, borttagning med mera.

Mer information om hur du hanterar befintliga aviseringar i Adobe Analytics finns i [Hantera aviseringar](/help/components/c-alerts/alert-manager.md).
