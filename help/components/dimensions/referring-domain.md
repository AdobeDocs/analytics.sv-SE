---
title: Refererande domän
description: Den överordnade domänen som en besökare var på innan han/hon klickade igenom till din plats.
feature: Dimensions
exl-id: 9e04cb62-6526-4d84-aff7-c962c0ce42b5
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 0%

---

# Refererande domän

Referensdomänen [dimension](overview.md) rapporterar vilka domäner besökarna klickar igenom för att nå din webbplats. Den här dimensionen är användbar för att förstå vilka tredjepartswebbplatser som genererar mest trafik till din. Det måste finnas en länk på den externa platsen och en besökare måste klicka på den för att dimensionsobjektet ska kunna visas.

>[!IMPORTANT]
>
>Du måste konfigurera rapportsvitens [interna URL-filter](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md) för att kunna använda den här dimensionen. Om du inte konfigurerar interna URL-filter kan det antingen innehålla interna domäner eller förhindra att externa domäner visas.

Samma rapport kan visa olika resultat mellan Analysis Workspace och Data Warehouse. Analysis Workspace rapporterar referensdomänen för varje enskild sida, exklusive värden som matchar interna URL-filter. Datan Warehouse rapporterar endast den första refererande domänen för besöket och ignorerar interna URL-filter.

## Fyll den här dimensionen med data

Den här dimensionen kräver konfiguration i analysgränssnittet och data i bildbegäranden.

* I implementeringen hämtar den här dimensionen data från [`r`-frågesträngen ](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurementet samlar in dessa data med JavaScript-variabeln `document.referrer` i webbläsaren. Om du använder ett AppMeasurementen bibliotek (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen automatiskt. Om du använder en datainsamlingsmetod utanför AppMeasurementet (till exempel via API:t), måste du ta med frågesträngsparametern `r` i bildbegäranden.
* I Analytics-gränssnittet måste du konfigurera rapportsvitens [interna URL-filter](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md). Om du inte konfigurerar interna URL-filter kan det antingen innehålla interna domäner eller förhindra att externa domäner visas.

Adobe fortsätter att referera till en domän för ett besök. Om en besökare lämnar och klickar via en länk på en annan domän inom ett enda besök uppdateras det nya värdet och kvarstår under resten av besöket. Om du bara vill se det ursprungliga värdet läser du [Ursprunglig hänvisande domän](original-referring-domain.md).

## Dimensioner

Bland Dimensionerna finns domäner som besökarna klickar igenom till webbplatsen. Om en träff inte har några referensdata (antingen angivna eller beständiga) grupperas den under dimensionsobjektet `"Typed/Bookmarked"`. Dimensionsobjektet betyder att det inte fanns något referensvärde, till exempel om besökaren skrev webbläsaradressen manuellt i adressfältet eller klickade på ett bokmärke. Dimensionsobjektet `"Typed/Bookmarked"` visas också för omdirigeringar som inte stöder Analytics. Se [Omdirigeringar och alias](/help/technotes/redirects.md) i användarhandboken för Technotes.

### Dimension som innehåller `googleusercontent.com`

Användare kan se dimensionsobjekt med domänen `googleusercontent.com`.

* **Cachelagrade sidor**: Google spindel crawlar hela tiden webben och lagrar kopior av sidor om de är offline. De här cachelagrade sidorna är tillgängliga bredvid de flesta sökresultaten genom att klicka på länken &quot;Cached&quot;. När en användare klickar på den här länken och visar innehållet som Google cachelagrade är `googleusercontent.com` dimensionsobjektet.
* **Översatta sidor**: Google erbjuder en robust och bekväm översättningstjänst. När du visar en webbplats med den här tjänsten kommer den från `googleusercontent.com`. Dimensionsobjektet visas om användaren klickar på en länk för att återgå till det ursprungliga innehållet.
