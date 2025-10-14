---
title: Ursprunglig hänvisande domän
description: Den första refererande domänen som en besökare var på innan han/hon klickade igenom till din webbplats.
feature: Dimensions
exl-id: 6b9ac662-a79a-477b-8612-7980da7cfadd
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 0%

---

# Ursprunglig hänvisande domän

Den ursprungliga refererande domänen [dimension](overview.md) rapporterar den första refererande domänen som en besökare klickade igenom för att nå din webbplats. När den är inställd innehåller den samma värde för hela besökar-ID:t. Denna dimension är användbar för att förstå vilka tredjepartswebbplatser som ursprungligen driver trafik till din webbplats.

>[!IMPORTANT]
>
>Du måste konfigurera rapportsvitens [interna URL-filter](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) för att kunna använda den här dimensionen. Om du inte konfigurerar interna URL-filter kan det antingen innehålla interna domäner eller förhindra att externa domäner visas.

## Fyll den här dimensionen med data

Den här dimensionen kräver konfiguration i både Analytics-gränssnittet och implementeringen.

* I implementeringen hämtar den här dimensionen data från [`r`-frågesträngen &#x200B;](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data med JavaScript-variabeln `document.referrer` i webbläsaren. Om du använder ett AppMeasurement-bibliotek (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen som standard. Om du använder en datainsamlingsmetod utanför AppMeasurement (till exempel via API:t) måste du ta med frågesträngsparametern `r` i bildbegäranden.
* I Analytics-gränssnittet måste du konfigurera rapportsvitens [interna URL-filter](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md). Om du inte konfigurerar interna URL-filter kan det antingen innehålla interna domäner eller förhindra att externa domäner visas.

Adobe behåller den ursprungliga referensdomänen för en besökares livstid. Om en besökare när som helst lämnar och klickar genom en länk på en annan domän registreras inte det nya värdet. Om du vill se nya värden läser du [Referensdomän](referring-domain.md).

## Dimension-objekt

Dimension-objekt innehåller domäner som besökare klickar igenom till din webbplats. Om en träff inte har några referensdata (antingen angivna eller beständiga) grupperas den under dimensionsobjektet `"None"`. Dimensionsobjektet betyder att det inte fanns något referensvärde, till exempel om besökaren skrev webbläsaradressen manuellt i adressfältet eller klickade på ett bokmärke.

## Jämför referensdomän med den ursprungliga refererande domänen

Den refererande domänen kan ändras mellan besök. En besökare kommer till din webbplats via `google.com`, och en vecka senare kommer till din webbplats via `twitter.com`. Till slut gör de ett köp på er webbplats. Om du använder Referensdomän som dimension med senaste beröringsattribuering får `twitter.com` kredit för köpet. Om den ursprungliga refererande domänen används som dimension får `google.com` kredit för köpet oavsett attribueringsmodell.

Ursprunglig hänvisande domän ändras aldrig under hela livstiden för ett visst besökar-ID.
