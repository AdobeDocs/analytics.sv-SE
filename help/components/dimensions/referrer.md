---
title: Referent
description: Den URL som besökaren var på innan han klickade igenom till din webbplats.
feature: Dimensions
exl-id: 146f0327-c73c-40f5-8cc1-584e31d163a2
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# Referent

Dimensionen Referent visar vilka URL:er besökarna var på när de klickade igenom för att nå din webbplats. Den här dimensionen är användbar för att förstå vilka specifika URL:er som genererar mest trafik till din webbplats. Det måste finnas en länk på den externa URL:en och en besökare måste klicka på den för att dimensionsobjektet ska kunna visas.

>[!IMPORTANT]
>
>Du måste konfigurera rapportsvitens [Interna URL-filter](/help/admin/admin/internal-url-filter-admin.md) om du vill använda den här dimensionen. Om du inte konfigurerar interna URL-filter kan det antingen innehålla interna URL:er eller förhindra att externa URL:er visas.

Samma rapport kan visa olika resultat mellan Analysis Workspace och Data warehouse. Analysis Workspace rapporterar referenten för varje enskild sida, exklusive värden som matchar interna URL-filter. data warehouse rapporterar bara den första referenten av besöket och ignorerar interna URL-filter.

## Fyll den här dimensionen med data

Den här dimensionen kräver konfiguration i analysgränssnittet och data i bildbegäranden.

* I implementeringen hämtar den här dimensionen data från [`r` frågesträng](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data med JavaScript-variabeln `document.referrer` i webbläsaren. Du kan använda [`referrer`](/help/implement/vars/page-vars/referrer.md) variabelåsidosättning för att manuellt ange den. Om du använder ett AppMeasurement-bibliotek (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen direkt. Om du använder en datainsamlingsmetod utanför AppMeasurement (till exempel via API:t) måste du ta med `r` frågesträngsparameter i bildbegäranden.
* I Analytics-gränssnittet måste du konfigurera rapportsvitens [Interna URL-filter](/help/admin/admin/internal-url-filter-admin.md). Om du inte konfigurerar interna URL-filter kan det antingen innehålla interna URL:er eller förhindra att externa URL:er visas.

## Dimensioner

Dimensionen innehåller URL:er som besökarna klickar igenom till webbplatsen. Om en träff inte har några referensdata grupperas den under dimensionsobjektet `"Typed/Bookmarked"`. Dimensionsobjektet betyder att det inte fanns något referensvärde, till exempel om besökaren skrev webbläsaradressen manuellt i adressfältet eller klickade på ett bokmärke. The `"Typed/Bookmarked"` Dimensionsobjekt visas också för omdirigeringar som inte stöder Analytics. Se [Omdirigering och alias](/help/technotes/redirects.md) i Technotes-handboken.

### Dimensioner som innehåller `googleusercontent.com`

Användare kan se dimensionsobjekt med domänen `googleusercontent.com`.

* **Cachelagrade sidor**: Google spindel krymper ständigt webben och lagrar kopior av webbsidor om de tas offline. De här cachelagrade sidorna är tillgängliga bredvid de flesta sökresultaten genom att klicka på länken &quot;Cached&quot;. När en användare klickar på den här länken och visar det innehåll som Google har cachelagrat, `webcache.googleusercontent.com` är en vanlig dimensionsobjekt.
* **Översatta sidor**: Google erbjuder en robust och smidig översättningstjänst. När du visar en webbplats med den här tjänsten kommer den från `translate.googleusercontent.com`. Dimensionsobjektet visas om användaren klickar på en länk för att återgå till det ursprungliga innehållet.
