---
title: Referent
description: Den URL som besökaren var på innan han klickade igenom till din webbplats.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 0%

---


# Referent

Dimensionen Referent visar vilka URL:er besökarna var på när de klickade igenom för att nå din webbplats. Den här dimensionen är användbar för att förstå vilka specifika URL:er som genererar mest trafik till din webbplats. Det måste finnas en länk på den externa URL:en och besökaren måste klicka på den för att dimensionsvärdet ska kunna visas.

>[!IMPORTANT]
>
>Du måste konfigurera rapportsvitens [interna URL-filter](/help/admin/admin/internal-url-filter-admin.md) för att kunna använda den här dimensionen. Om du inte konfigurerar interna URL-filter kan det antingen innehålla interna URL:er eller förhindra att externa URL:er visas.

## Fyll den här dimensionen med data

Den här dimensionen kräver konfiguration i Analytics gränssnitt och data i bildbegäranden.

* I implementeringen hämtar den här dimensionen data från [`r` frågesträngen](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data med JavaScript-variabeln `document.referrer` i webbläsaren. Om du använder ett AppMeasurement-bibliotek (till exempel via Adobe Experience Platform Launch) fungerar den här dimensionen direkt. Om du använder en datainsamlingsmetod utanför AppMeasurement (till exempel via API:t), måste du ta med frågesträngsparametern i bildbegäranden. `r`
* I Analytics-gränssnittet måste du konfigurera rapportsvitens [interna URL-filter](/help/admin/admin/internal-url-filter-admin.md). Om du inte konfigurerar interna URL-filter kan det antingen innehålla interna URL:er eller förhindra att externa URL:er visas.

## Dimensionsvärden

Dimensionsvärdena inkluderar URL:er som besökarna klickar igenom till webbplatsen. Om en träff inte har några referensdata grupperas den under dimensionsvärdet `"Typed/Bookmarked"`. Dimensionsvärdet innebär att det inte fanns något referensvärde, till exempel om besökaren skrev webbläsaradressen manuellt i adressfältet eller klickade på ett bokmärke.
