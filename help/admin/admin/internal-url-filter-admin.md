---
description: Interna URL-filter identifierar de referenser som du anser vara interna för din webbplats. De hjälper trafikkällor att fylla i data och hjälper till att filtrera intern trafik.
title: Interna URL-filter
topic: Admin tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
translation-type: tm+mt
source-git-commit: 9237315927b769aaf454a7e81932fdf63572295f
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 2%

---


# Interna URL-filter

**[!UICONTROL Admin > Report Suites > Edit Settings > General > Internal URL Filters > Add Filter]**

Interna URL-filter identifierar de referenser som du anser vara interna för din webbplats. De hjälper trafikkällor att fylla i data och hjälper till att filtrera intern trafik.

En hänvisare, eller hänvisande sida, är vanligtvis den sida från vilken en besökare har angett webbplatsen. För att undvika att skevas kan du filtrera bort interna referenser. Rapporterna exkluderar filtrerade referenser från [referensdimensionen](/help/components/dimensions/referrer.md) , dimensionen för [referensdomäner](/help/components/dimensions/referring-domain.md) och andra dimensioner för trafikkällan.

Den vanligaste orsaken till att trafikkällorna inte fyller i data är att Intern URL-filterlista inte har definierats. Följ de här stegen för att kontrollera vilka interna URL-filter som har konfigurerats för en rapportsvit. Du undviker detta genom att ta bort regeln med en punkt (.) som ett filter och lägg till en egen webbplats.

Orsaken till att en punkt är standardfiltret för intern URL är att data kan samlas in i sidrapporten. Om träffar inte matchar interna URL-filter visas alla sidor som Annan. En punkt finns alltid någonstans i URL:en, vilket garanterar att sidrapporten är ifylld.
