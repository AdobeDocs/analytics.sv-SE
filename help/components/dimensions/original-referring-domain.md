---
title: Ursprunglig hänvisande domän
description: Den första refererande domänen som en besökare var på innan han/hon klickade igenom till din webbplats.
translation-type: tm+mt
source-git-commit: ad206649488a1a2dead717cdfe53f4c630ba3f3b
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 0%

---


# Ursprunglig hänvisande domän

Dimensionen Ursprunglig hänvisande domän rapporterar den första refererande domänen som en besökare klickade igenom för att nå din webbplats. När den är inställd innehåller den samma värde för hela besökar-ID:t. Denna dimension är användbar för att förstå vilka tredjepartswebbplatser som ursprungligen driver trafik till din webbplats.

## Fyll den här dimensionen med data

Den här dimensionen kräver konfiguration i både Analytics-gränssnittet och implementeringen.

* I implementeringen hämtar den här dimensionen data från [`r` frågesträngen](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data med JavaScript-variabeln `document.referrer` i webbläsaren. Om du använder ett AppMeasurement-bibliotek (till exempel via Adobe Experience Platform Launch) fungerar den här dimensionen som den ska. Om du använder en datainsamlingsmetod utanför AppMeasurement (till exempel via API:t), måste du ta med frågesträngsparametern i bildbegäranden. `r`
* I Analytics-gränssnittet måste du konfigurera rapportsvitens [interna URL-filter](/help/admin/admin/internal-url-filter-admin.md). Om du inte konfigurerar interna URL-filter kan det antingen innehålla interna domäner eller förhindra att externa domäner visas.

Adobe behåller den ursprungliga referensdomänen för en besökares livstid. Om en besökare när som helst lämnar och klickar genom en länk på en annan domän registreras inte det nya värdet. Om du vill se nya värden läser du i [Referensdomän](referring-domain.md).

## Dimensionsvärden

Dimensionsvärdena inkluderar domäner som besökarna klickar igenom till din webbplats. Om en träff inte har några referensdata (antingen angivna eller beständiga) grupperas den under dimensionsvärdet `"None"`. Dimensionsvärdet innebär att det inte fanns något referensvärde, till exempel om besökaren skrev webbläsaradressen manuellt i adressfältet eller klickade på ett bokmärke.
