---
description: Testa opublicerade regler från konsolen om du använder Akamai-värdtjänster.
keywords: Dynamic Tag Management;rule;switcher plug-in;akamai;test akamai;unpublished rules;test unpublished rules;debug rule
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Testa opublicerade regler för Akamai-värdtjänster
uuid: 979e3d74-8d96-47d0-b581-cf5371248434
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Testa opublicerade regler för Akamai-värdtjänster

Testa opublicerade regler från konsolen om du använder Akamai-värdtjänster.

Switcher är ofta det enklaste sättet att testa. Mer information finns i [Search Discovery-plugin-program](https://docs.adobe.com/content/help/en/dtm/using/resources/plugins/search-discovery-plugins.html) i produktdokumentationen för Dynamic Tag Management.

I följande steg visas hur du testar utan att använda plugin-programmet Switcher:

1. Gå till din webbkonsol på din webbplats och skriv `localStorage.setItem('sdsat_stagingLibrary', true)`.
1. Tryck **[!UICONTROL Enter]**.
1. Skriv `_satellite.setDebug(true)`och tryck sedan på **[!UICONTROL Enter]**.
1. Uppdatera sidan.

   Den här åtgärden läser in mellanlagringsbiblioteket och ställer in felsökaren så att du kan se information om alla tillgängliga (publicerade/opublicerade) regler som aktiveras på sidan.
1. När du är klar kör du `localStorage.setItem('sdsat_stagingLibrary', false)`och trycker sedan på **[!UICONTROL Enter]**.

   Stegresultat
