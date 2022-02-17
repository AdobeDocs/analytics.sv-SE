---
title: Minut
description: Den minut som mätvärdet inträffade.
feature: Dimensions
exl-id: 63f13083-321f-4fd8-9352-e413e1ebf168
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 0%

---

# Minut

Dimensionen Minute rapporterar den minut som ett givet mätvärde inträffade (avrundat nedåt). Den första dimensionsposten är den första minuten i datumintervallet och den sista dimensionsposten är den sista minuten i datumintervallet. Denna dimension är värdefull för trendrapporter eftersom den gör att du kan se mätvärden över tid. Med tanke på hur detaljerad denna dimension är rekommenderar Adobe att rapporteringsdatumintervallet begränsas till en eller två dagar.

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensioner

Dimensionen innehåller en viss minut inom rapportens datumintervall tillsammans med dess datum. Det är formaterat som `HH:MM YYYY-MM-DD`. Dimensioner som börjar med `00:00` motsvarar midnatt den dagen, medan värden börjar med `23:59` motsvarar 11:59 PM för den dagen.
