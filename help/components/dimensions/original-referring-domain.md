---
title: Ursprunglig hänvisande domän
description: Den första refererande domänen som en besökare var på innan han/hon klickade igenom till din webbplats.
translation-type: tm+mt
source-git-commit: 7c722e361978a3d7517e95c23442b703e7e25270
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 0%

---


# Ursprunglig hänvisande domän

Dimensionen Ursprunglig hänvisande domän rapporterar den första refererande domänen som en besökare klickade igenom för att nå din webbplats. När den är inställd innehåller den samma värde för hela besökar-ID:t. Denna dimension är användbar för att förstå vilka tredjepartswebbplatser som ursprungligen driver trafik till din webbplats.

>[!IMPORTANT]
>
>Du måste konfigurera rapportsvitens [interna URL-filter](/help/admin/admin/internal-url-filter-admin.md) för att kunna använda den här dimensionen. Om du inte konfigurerar interna URL-filter kan det antingen innehålla interna domäner eller förhindra att externa domäner visas.

## Fyll den här dimensionen med data

Denna dimension kräver konfiguration både i Analytics gränssnitt och i implementeringen.

* I implementeringen hämtar den här dimensionen data från [`r` frågesträngen](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data med JavaScript-variabeln `document.referrer` i webbläsaren. Om du använder ett AppMeasurement-bibliotek (till exempel via Adobe Experience Platform Launch) fungerar den här dimensionen som standard. Om du använder en datainsamlingsmetod utanför AppMeasurement (till exempel via API:t), måste du ta med frågesträngsparametern i bildbegäranden. `r`
* I Analytics-gränssnittet måste du konfigurera rapportsvitens [interna URL-filter](/help/admin/admin/internal-url-filter-admin.md). Om du inte konfigurerar interna URL-filter kan det antingen innehålla interna domäner eller förhindra att externa domäner visas.

Adobe behåller den ursprungliga referensdomänen för en besökares livstid. Om en besökare när som helst lämnar och klickar genom en länk på en annan domän registreras inte det nya värdet. Om du vill se nya värden läser du i [Referensdomän](referring-domain.md).

## Dimensioner

Bland Dimensionerna finns domäner som besökarna klickar igenom till webbplatsen. Om en träff inte har några referensdata (antingen angivna eller beständiga) grupperas den under dimensionsobjektet `"None"`. Dimensionsobjektet betyder att det inte fanns något referensvärde, till exempel om besökaren skrev webbläsaradressen manuellt i adressfältet eller klickade på ett bokmärke.

## Jämför referensdomän med den ursprungliga refererande domänen

Referensdomänen kan ändras mellan besök. En besökare kommer till exempel till din webbplats via `google.com`och en vecka senare kommer till din webbplats via `twitter.com`. Till slut gör de ett köp på er webbplats. Om du använder Referensdomän som dimension med senaste beröringsattribuering, `twitter.com` får kunden ett erkännande för köpet. Om du använder den ursprungliga refererande domänen som dimension, `google.com` får inköpet krediter oavsett attribueringsmodell.

Ursprunglig hänvisande domän ändras aldrig under hela livstiden för ett visst besökar-ID.
