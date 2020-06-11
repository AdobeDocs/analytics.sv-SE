---
title: Spårningskod
description: Namnet på spårningskoden eller kampanjen.
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 0%

---


# Spårningskod

Dimensionen Spårningskod visar namnen på spårningskoderna på din webbplats. Den här dimensionen samlas vanligtvis in med frågesträngsparametrar. Du kan placera länkar med olika parametervärden för frågesträngar på olika platser på Internet. Denna dimension rapporterar vilka länkar som var mest framgångsrika när det gäller att köra trafik till din plats.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [`v0` frågesträngen](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data med hjälp av [`campaign`](/help/implement/vars/page-vars/campaign.md) variabeln.

## Dimensionsvärden

Dimensionsvärdena innehåller namnen på spårningskoderna på din webbplats. Din organisation avgör vilka specifika dimensionsvärden du vill använda.
