---
title: Refererande domän
description: Den överordnade domänen som en besökare var på innan han/hon klickade igenom till din plats.
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 0%

---


# Refererande domän

Dimensionen Refererande domän visar vilka domäner besökarna klickar igenom för att nå din webbplats. Den här dimensionen är användbar för att förstå vilka tredjepartswebbplatser som genererar mest trafik till din. Det måste finnas en länk på den externa platsen och en besökare måste klicka på den för att dimensionsvärdet ska kunna visas.

>[!IMPORTANT] Du måste konfigurera rapportsvitens [interna URL-filter](/help/admin/admin/internal-url-filter-admin.md) för att kunna använda den här dimensionen. Om du inte konfigurerar interna URL-filter kan det antingen innehålla interna domäner eller förhindra att externa domäner visas.

## Fyll den här dimensionen med data

Den här dimensionen kräver konfiguration i analysgränssnittet och data i bildbegäranden.

* I implementeringen hämtar den här dimensionen data från [`r` frågesträngen](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data med JavaScript-variabeln `document.referrer` i webbläsaren. Om du använder ett AppMeasurement-bibliotek (till exempel via Adobe Experience Platform Launch) fungerar den här dimensionen som den ska. Om du använder en datainsamlingsmetod utanför AppMeasurement (till exempel via API:t), måste du ta med frågesträngsparametern i bildbegäranden. `r`
* I Analytics-gränssnittet måste du konfigurera rapportsvitens [interna URL-filter](/help/admin/admin/internal-url-filter-admin.md). Om du inte konfigurerar interna URL-filter kan det antingen innehålla interna domäner eller förhindra att externa domäner visas.

Adobe fortsätter att referera till en domän för ett besök. Om en besökare lämnar och klickar via en länk på en annan domän inom ett enda besök uppdateras det nya värdet och kvarstår under resten av besöket. Om du bara vill se det ursprungliga värdet läser du i [Ursprunglig hänvisande domän](original-referring-domain.md).

## Dimensionsvärden

Dimensionsvärdena inkluderar domäner som besökarna klickar igenom till din webbplats. Om en träff inte har några referensdata (antingen angivna eller beständiga) grupperas den under dimensionsvärdet `"Typed/Bookmarked"`. Dimensionsvärdet innebär att det inte fanns något referensvärde, till exempel om besökaren skrev webbläsaradressen manuellt i adressfältet eller klickade på ett bokmärke.
