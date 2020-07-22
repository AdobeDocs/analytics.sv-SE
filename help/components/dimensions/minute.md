---
title: Minut
description: Den minut som mätvärdet inträffade.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 0%

---


# Minut

Dimensionen Minute rapporterar den minut som ett givet mätvärde inträffade (avrundat nedåt). Den första dimensionsposten är den första minuten i datumintervallet och den sista dimensionsposten är den sista minuten i datumintervallet. Denna dimension är värdefull för trendrapporter eftersom den gör att du kan se mätvärden över tid. Med tanke på hur detaljerad dimensionen är rekommenderar Adobe att du begränsar rapporteringsdatumintervallet till en eller två dagar.

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensionsobjekt

Dimensionsobjekten innehåller en viss minut inom rapportens datumintervall tillsammans med datumet. Den är formaterad som `HH:MM YYYY-MM-DD`. Dimensionsobjekt som börjar med `00:00` motsvarar midnatt den dagen, medan värden som börjar med `23:59` är lika med 11:59 PM för den dagen.
