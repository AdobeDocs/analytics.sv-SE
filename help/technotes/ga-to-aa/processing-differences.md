---
title: Skillnader i bearbetning och arkitektur mellan olika Analytics-plattformar
description: Lär dig hur vissa data samlas in och visas på olika sätt på olika plattformar som Adobe Analytics och Google Analytics.
feature: Third-party Integration
exl-id: 3e457915-3c2d-49f7-9b77-df18c04d49cd
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 0%

---

# Skillnader i bearbetning och arkitektur mellan olika Analytics-plattformar

Även om både Adobe Analytics och Google Analytics är Analytics-verktyg är det mycket annorlunda hur data samlas in och bearbetas mellan olika plattformar. Använd den här sidan om du vill förstå några av de viktigaste skillnaderna i hur vissa dimensioner och mått samlas in och varför de kan visa olika tal i liknande rapporter.

## [!UICONTROL Bounce Rate]

[!UICONTROL Bounce Rate] är en gemensam KPI som används för att mäta landningssidornas effektivitet och relevans i de flesta analysverktyg. Detta definieras vanligtvis som besök på webbplatsen, men där det inte finns något klick till en annan sida.

* I Adobe Analytics [!UICONTROL Bounce Rate] beräknas med hjälp av formeln **Kurser dividerade med poster**.
* I Google Analytics [!UICONTROL Bounce Rate] beräknas med hjälp av formeln **Enkelsidiga sessioner delade av sessioner**.

Om flera träffar skickas vid samma besök eller session på båda plattformarna räknas det inte som ett studs. I Adobe Analytics finns det anpassade länkar som är mycket vanliga och som kan förhindra att ett besök räknas som ett studs. Google Analytics skickar vanligtvis inte mer än en databegäran på samma sida.

Använd [!UICONTROL Single Page Visits] i Adobe Analytics istället för [!UICONTROL Bounces] som en del av ett beräknat mätvärde. The [!UICONTROL Single Page Visits] Mätvärdet omfattar det totala antalet besök som endast innehöll en sida, eller besök som kom in på webbplatsen men inte innehöll ett klick till en annan sida.

Se [Studsfrekvens](/help/components/metrics/bounce-rate.md) i användarhandboken för komponenter finns mer information.

## [!UICONTROL Visits] och sessioner

[!UICONTROL Visits] (kallas sessioner i Google Analytics) är en grupp sidvisningar som görs av samma användare på kort tid. [!UICONTROL Visits] på båda plattformarna går vanligtvis ut efter 30 minuters inaktivitet. Båda plattformarna tillåter anpassning när [!UICONTROL Visit] förfaller. Det finns flera scenarier som kan orsaka skillnader på olika plattformar.

* **Dagens slut:** Alla sessioner i Google Analytics går ut efter klockan 11.59 på en viss dag. Om användaren fortfarande är aktiv på webbplatsen efter kl. 12.00 skapas en ny session. Adobe Analytics fortsätter att besöka följande dag som en del av samma besök.
* **Olika kampanjer:** En ny session i Google Analytics börjar om en användares kampanjkälla ändras. Om en ny [!UICONTROL Tracking Code] värdet ses i Adobe Analytics och anses vara en del av samma besök.
* **Åsidosättning av manuell session:** En ny session i Google Analytics påbörjas om du använder `sessionControl` om du vill starta eller avsluta en session manuellt. [!UICONTROL Visits] kan inte avslutas manuellt i Adobe Analytics.
* **Avancerad besöksidentifiering i Adobe Analytics:** En ny [!UICONTROL Visit] i Adobe Analytics startar automatiskt om en användare når 12 timmars kontinuerlig aktivitet, 2 500 träffar eller 100 träffar inom 100 sekunder. Vart och ett av dessa detekteringskriterier aktiveras vanligtvis av båda aktiviteterna.

Se [Besök](/help/components/metrics/visits.md) i användarhandboken för komponenter finns mer information.
