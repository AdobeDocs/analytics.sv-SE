---
description: Interna URL-filter identifierar de referenser som du anser vara interna för din webbplats. De hjälper trafikkällor att fylla i data och hjälper till att filtrera intern trafik.
title: Interna URL-filter
feature: Administratörsverktyg
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 3%

---

# Interna URL-filter

**[!UICONTROL Admin > Report Suites > Edit Settings > General > Internal URL Filters > Add Filter]**

Interna URL-filter identifierar de referenser som du anser vara interna för din webbplats. De hjälper trafikkällor att fylla i data och hjälper till att filtrera intern trafik.

En hänvisare, eller hänvisande sida, är vanligtvis den sida från vilken en besökare har angett webbplatsen. För att undvika att skevas kan du filtrera bort interna referenser. Rapporterna exkluderar filtrerade referenser från dimensionen [Referenter](/help/components/dimensions/referrer.md), dimensionen [Refererande domäner](/help/components/dimensions/referring-domain.md) och andra mått för trafikkällor.

Den vanligaste orsaken till att trafikkällorna inte fyller i data är att Intern URL-filterlista inte har definierats. Följ de här stegen för att kontrollera vilka interna URL-filter som har konfigurerats för en rapportsvit. Du undviker detta genom att ta bort regeln med en punkt (.) som ett filter och lägg till en egen webbplats.

Orsaken till att en punkt är standardfiltret för intern URL är att data kan samlas in i sidrapporten. Om träffar inte matchar interna URL-filter visas alla sidor som Annan. En punkt finns alltid någonstans i URL:en, vilket garanterar att sidrapporten är ifylld.
