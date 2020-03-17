---
title: Skillnader i bearbetning och arkitektur mellan olika Analytics-plattformar
description: Lär dig hur vissa data samlas in och visas på olika sätt på olika plattformar som Adobe Analytics och Google Analytics.
translation-type: tm+mt
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# Skillnader i bearbetning och arkitektur mellan olika Analytics-plattformar

Även om både Adobe Analytics och Google Analytics är analysverktyg skiljer sig det sätt på vilket data samlas in och bearbetas mellan olika plattformar mycket åt. Använd den här sidan om du vill förstå några av de viktigaste skillnaderna i hur vissa dimensioner och mått samlas in och varför de kan visa olika tal i liknande rapporter.

## Studsfrekvens

Studsfrekvens är en vanlig KPI som används för att mäta landningssidornas effektivitet och relevans i de flesta analysverktyg. Detta definieras vanligtvis som besök på webbplatsen, men där det inte finns något klick till en annan sida.

* I Adobe Analytics beräknas studsfrekvensen med formeln **Bounces dividerat med Poster**.
* I Google Analytics beräknas studsfrekvensen med hjälp av formeln **Enkelsidiga sessioner delat med sessioner**.

Om flera träffar skickas vid samma besök eller session på båda plattformarna räknas det inte som ett studs. I Adobe Analytics finns det anpassade länkar som är tillgängliga och ganska vanliga, vilket kan förhindra att ett besök räknas som ett studs. Google Analytics skickar vanligtvis inte mer än en databegäran på samma sida.

Om du vill få en bättre överensstämmelse mellan rapporteringsverktygen använder du Enkelsidesbesök i Adobe Analytics i stället för Gränser som en del av ett beräknat mått. Måttet för enkelsidiga besök innehåller det totala antalet besök som endast inkluderade en sida, eller besök som kom in på webbplatsen men inte inkluderade ett klick till en annan sida.

Mer information finns i [Studsfrekvens](/help/components/c-variables/c-metrics/metrics-bounce-rate.md) -måttet i användarhandboken för komponenter.

## Besök och sessioner

Besök (som kallas sessioner i Google Analytics) är en grupp sidvisningar som görs av samma användare på kort tid. Besök på båda plattformarna upphör vanligtvis efter 30 minuters inaktivitet. Båda plattformarna tillåter anpassning när ett besök upphör. Det finns flera scenarier som kan orsaka skillnader på olika plattformar.

* **Dagens slut:** Alla sessioner i Google Analytics går ut efter klockan 11.59 på en viss dag. Om användaren fortfarande är aktiv på webbplatsen efter kl. 12.00 skapas en ny session. Adobe Analytics fortsätter att besöka följande dag som en del av samma besök.
* **Olika kampanjer:** En ny session i Google Analytics startar om en användares kampanjkälla ändras. Om ett nytt Tracking Code-värde visas i Adobe Analytics räknas det som en del av samma besök.
* **Åsidosättning av manuell session:** En ny session i Google Analytics startar om du använder `sessionControl` för att starta eller avsluta en session manuellt. Besök kan inte avslutas manuellt i Adobe Analytics.
* **Avancerad besöksidentifiering i Adobe Analytics:** Ett nytt besök i Adobe Analytics startar automatiskt om en användare når 12 timmars kontinuerlig aktivitet, 2 500 träffar eller 100 träffar inom 100 sekunder. Vart och ett av dessa detekteringskriterier aktiveras vanligtvis av båda aktiviteterna.

Mer information finns i [Besök](/help/components/c-variables/c-metrics/metrics-visit.md) -måttet i användarhandboken för komponenter.
