---
title: Referent
description: Den URL som besökaren var på innan han klickade igenom till din webbplats.
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%

---


# Referent

Dimensionen Referent visar vilka URL:er besökarna var på när de klickade igenom för att nå din webbplats. Den här dimensionen är användbar för att förstå vilka specifika URL:er som genererar mest trafik till din webbplats. Det måste finnas en länk på den externa URL:en och en besökare måste klicka på den för att dimensionsobjektet ska kunna visas.

>[!IMPORTANT]
>
>Du måste konfigurera rapportsvitens [interna URL-filter](/help/admin/admin/internal-url-filter-admin.md) för att kunna använda den här dimensionen. Om du inte konfigurerar interna URL-filter kan det antingen innehålla interna URL:er eller förhindra att externa URL:er visas.

Samma rapport kan visa olika resultat mellan Analysis Workspace och Data warehouse. Analysis Workspace rapporterar referenten för varje enskild sida, exklusive värden som matchar interna URL-filter. data warehouse rapporterar bara den första referenten av besöket och ignorerar interna URL-filter.

## Fyll den här dimensionen med data

Den här dimensionen kräver konfiguration i analysgränssnittet och data i bildbegäranden.

* I implementeringen hämtar den här dimensionen data från [`r` frågesträngen](/help/implement/validate/query-parameters.md) i bildbegäranden. AppMeasurement samlar in dessa data med JavaScript-variabeln `document.referrer` i webbläsaren. Du kan använda variabelåsidosättningen om du vill ange den manuellt. [`referrer`](/help/implement/vars/page-vars/referrer.md) Om du använder ett AppMeasurement-bibliotek (till exempel via Adobe Experience Platform Launch) fungerar den här dimensionen som standard. Om du använder en datainsamlingsmetod utanför AppMeasurement (till exempel via API:t), måste du ta med frågesträngsparametern i bildbegäranden. `r`
* I Analytics-gränssnittet måste du konfigurera rapportsvitens [interna URL-filter](/help/admin/admin/internal-url-filter-admin.md). Om du inte konfigurerar interna URL-filter kan det antingen innehålla interna URL:er eller förhindra att externa URL:er visas.

## Dimensioner

Dimensionen innehåller URL:er som besökarna klickar igenom till webbplatsen. Om en träff inte har några referensdata grupperas den under dimensionsobjektet `"Typed/Bookmarked"`. Dimensionsobjektet betyder att det inte fanns något referensvärde, till exempel om besökaren skrev webbläsaradressen manuellt i adressfältet eller klickade på ett bokmärke. Dimensionsobjektet visas också för omdirigeringar som inte stöder Analytics. `"Typed/Bookmarked"` Se [Omdirigeringar och alias](/help/technotes/redirects.md) i användarhandboken för Technotes.

### Dimensioner som innehåller `googleusercontent.com`

Användare kan se dimensionsobjekt med domänen `googleusercontent.com`.

* **Cachelagrade sidor**: Googles spindlar crawlar hela tiden webben och lagrar kopior av sidor om de tas offline. De här cachelagrade sidorna är tillgängliga bredvid de flesta sökresultaten genom att klicka på länken &quot;Cached&quot;. När en användare klickar på den här länken och visar innehållet som Google cache-lagrade är `webcache.googleusercontent.com` det en vanlig dimensionspost.
* **Översatta sidor**: Google erbjuder en robust och bekväm översättningstjänst. När du visar en webbplats med den här tjänsten kommer den från `translate.googleusercontent.com`. Dimensionsobjektet visas om användaren klickar på en länk för att återgå till det ursprungliga innehållet.
