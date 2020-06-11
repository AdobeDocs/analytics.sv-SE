---
title: Minut
description: Den minut som mätvärdet inträffade.
translation-type: tm+mt
source-git-commit: 2c262e5345c39a71a6a54062c607273528294b24
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 0%

---


# Minut

Dimensionen Minute rapporterar den minut som ett givet mätvärde inträffade (avrundat nedåt). Det första dimensionsvärdet är den första minuten i datumintervallet och det sista dimensionsvärdet är den sista minuten i datumintervallet. Denna dimension är värdefull för trendrapporter eftersom den gör att du kan se mätvärden över tid. Med tanke på hur detaljerad dimensionen är rekommenderar Adobe att du begränsar rapporteringsdatumintervallet till en eller två dagar.

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensionsvärden

Dimensionsvärden inkluderar en viss minut inom rapportens datumintervall tillsammans med datumet. Den är formaterad som `HH:MM YYYY-MM-DD`. Dimensionsvärden som börjar med `00:00` motsvarar midnatt den dagen, medan värden som börjar med `23:59` är lika med 11:59 PM för den dagen.
