---
title: Skillnader i bearbetning och arkitektur mellan olika Analytics-plattformar
description: Lär dig hur vissa data samlas in och visas på olika sätt på olika plattformar som Adobe Analytics och Google Analytics.
translation-type: tm+mt
source-git-commit: 3211598c2ff43493b329a9be4fb6877ae29cf08b
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 0%

---


# Skillnader i bearbetning och arkitektur mellan olika Analytics-plattformar

Även om både Adobe Analytics och Google Analytics är analysverktyg skiljer sig det sätt på vilket data samlas in och bearbetas mellan olika plattformar mycket åt. Använd den här sidan om du vill förstå några av de viktigaste skillnaderna i hur vissa dimensioner och mått samlas in och varför de kan visa olika tal i liknande rapporter.

## [!UICONTROL Bounce Rate]

[!UICONTROL Bounce Rate] är en gemensam KPI som används för att mäta landningssidornas effektivitet och relevans i de flesta analysverktyg. Detta definieras vanligtvis som besök på webbplatsen, men där det inte finns något klick till en annan sida.

* I Adobe Analytics [!UICONTROL Bounce Rate] beräknas med formeln **Bounces dividerat med Poster**.
* I Google Analytics [!UICONTROL Bounce Rate] beräknas med hjälp av formeln **Enkelsidiga sessioner som delas av sessioner**.

Om flera träffar skickas vid samma besök eller session på båda plattformarna räknas det inte som ett studs. I Adobe Analytics finns det anpassade länkar som är tillgängliga och ganska vanliga, vilket kan förhindra att ett besök räknas som ett studs. Google Analytics skickar vanligtvis inte mer än en databegäran på samma sida.

Om du vill få en bättre överensstämmelse mellan rapporteringsverktygen använder du måtten i Adobe Analytics i stället för [!UICONTROL Single Page Visits] [!UICONTROL Bounces] som en del av ett beräknat mätresultat. Mätvärdet [!UICONTROL Single Page Visits] omfattar det totala antalet besök som endast inkluderade en sida, eller besök som kom in på webbplatsen men inte inkluderade ett klick till en annan sida.

Mer information finns i [Studsfrekvens](/help/components/c-variables/c-metrics/metrics-bounce-rate.md) -måttet i användarhandboken för komponenter.

## [!UICONTROL Visits] och sessioner

[!UICONTROL Visits] (kallas sessioner i Google Analytics) är en grupp sidvisningar som görs av samma användare på kort tid. [!UICONTROL Visits] på båda plattformarna går vanligtvis ut efter 30 minuters inaktivitet. Båda plattformarna tillåter anpassning när en [!UICONTROL Visit] förfaller. Det finns flera scenarier som kan orsaka skillnader på olika plattformar.

* **Dagens slut:** Alla sessioner i Google Analytics går ut efter klockan 11.59 på en viss dag. Om användaren fortfarande är aktiv på webbplatsen efter kl. 12.00 skapas en ny session. Adobe Analytics fortsätter att besöka följande dag som en del av samma besök.
* **Olika kampanjer:** En ny session i Google Analytics startar om en användares kampanjkälla ändras. Om Adobe Analytics ger ett nytt [!UICONTROL Tracking Code] värde räknas det som en del av samma besök.
* **Åsidosättning av manuell session:** En ny session i Google Analytics startar om du använder `sessionControl` för att starta eller avsluta en session manuellt. [!UICONTROL Visits] kan inte avslutas manuellt i Adobe Analytics.
* **Avancerad besöksidentifiering i Adobe Analytics:** En ny funktion [!UICONTROL Visit] i Adobe Analytics startas automatiskt om en användare uppnår 12 timmars kontinuerlig aktivitet, 2 500 träffar eller 100 träffar inom 100 sekunder. Vart och ett av dessa detekteringskriterier aktiveras vanligtvis av båda aktiviteterna.

Mer information finns i [Besök](/help/components/c-variables/c-metrics/metrics-visit.md) -måttet i användarhandboken för komponenter.
