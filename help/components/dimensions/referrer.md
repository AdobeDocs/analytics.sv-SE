---
title: Referent
description: Den URL som en besökare var på innan han klickade igenom till din webbplats.
feature: Dimensions
exl-id: 146f0327-c73c-40f5-8cc1-584e31d163a2
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# Referent

Referenten [dimension](overview.md) rapporterar vilka URL:er besökarna var på när de klickade igenom för att nå din webbplats. Den här dimensionen är användbar för att förstå vilka specifika URL:er som genererar mest trafik till din webbplats. Det måste finnas en länk på den externa URL:en och en besökare måste klicka på den för att dimensionsobjektet ska kunna visas.

>[!IMPORTANT]
>
>Du måste konfigurera rapportsvitens [interna URL-filter](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) för att kunna använda den här dimensionen. Om du inte konfigurerar interna URL-filter kan det antingen innehålla interna URL:er eller förhindra att externa URL:er visas.

Samma rapport kan visa olika resultat mellan Analysis Workspace och Data Warehouse. Analysis Workspace rapporterar referenten för varje enskild sida, exklusive värden som matchar interna URL-filter. Data Warehouse rapporterar bara den första referenten av besöket och ignorerar interna URL-filter.

## Fyll den här dimensionen med data

Den här dimensionen kräver konfiguration i analysgränssnittet och data i bildbegäranden.

* I implementeringen hämtar den här dimensionen data från [`r`-frågesträngen ](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data med JavaScript-variabeln `document.referrer` i webbläsaren. Du kan använda variabelåsidosättningen [`referrer`](/help/implement/vars/page-vars/referrer.md) om du vill ange den manuellt. Om du använder ett AppMeasurement-bibliotek (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen som standard. Om du använder en datainsamlingsmetod utanför AppMeasurement (till exempel via API:t) måste du ta med frågesträngsparametern `r` i bildbegäranden.
* I Analytics-gränssnittet måste du konfigurera rapportsvitens [interna URL-filter](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md). Om du inte konfigurerar interna URL-filter kan det antingen innehålla interna URL:er eller förhindra att externa URL:er visas.

## Dimension-objekt

Dimension-objekten innehåller URL:er som besökarna klickar igenom till webbplatsen. Om en träff inte har några referensdata grupperas den under dimensionsobjektet `"Typed/Bookmarked"`. Dimensionsobjektet betyder att det inte fanns något referensvärde, till exempel om besökaren skrev webbläsaradressen manuellt i adressfältet eller klickade på ett bokmärke. Dimensionsobjektet `"Typed/Bookmarked"` visas också för omdirigeringar som inte stöder Analytics. Se [Omdirigeringar och alias](/help/technotes/redirects.md) i användarhandboken för Technotes.

### Dimension-objekt som innehåller `googleusercontent.com`

Användare kan se dimensionsobjekt med domänen `googleusercontent.com`.

* **Cachelagrade sidor**: Google spindel crawlar hela tiden webben och lagrar kopior av sidor om de är offline. De här cachelagrade sidorna är tillgängliga bredvid de flesta sökresultaten genom att klicka på länken &quot;Cached&quot;. När en användare klickar på den här länken och visar innehållet som Google cachade är `webcache.googleusercontent.com` ett vanligt dimensionsobjekt.
* **Översatta sidor**: Google erbjuder en robust och bekväm översättningstjänst. När du visar en webbplats med den här tjänsten kommer den från `translate.googleusercontent.com`. Dimensionsobjektet visas om användaren klickar på en länk för att återgå till det ursprungliga innehållet.
