---
title: Skillnader i bearbetning och arkitektur mellan olika Analytics-plattformar
description: Lär dig hur vissa data samlas in och visas på olika sätt på olika plattformar som Adobe Analytics och Google Analytics.
feature: Third-party Integration
exl-id: 3e457915-3c2d-49f7-9b77-df18c04d49cd
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 0%

---

# Skillnader i bearbetning och arkitektur mellan olika Analytics-plattformar

Även om både Adobe Analytics och Google Analytics är Analytics-verktyg är det mycket annorlunda hur data samlas in och bearbetas mellan olika plattformar. Använd den här sidan om du vill förstå några av de viktigaste skillnaderna i hur vissa dimensioner och mått samlas in och varför de kan visa olika tal i liknande rapporter.

## [!UICONTROL Bounce Rate]

[!UICONTROL Bounce Rate] är en vanlig KPI som används för att mäta landningssidornas effektivitet och relevans i de flesta analysverktyg. Detta definieras vanligtvis som besök på webbplatsen, men där det inte finns något klick till en annan sida.

* I Adobe Analytics beräknas [!UICONTROL Bounce Rate] med formeln **studsar dividerat med poster**.
* I Google Analytics beräknas [!UICONTROL Bounce Rate] med formeln **Enkelsidiga sessioner dividerade med sessioner**.

Om flera träffar skickas vid samma besök eller session på båda plattformarna räknas det inte som ett studs. I Adobe Analytics finns det anpassade länkar som är mycket vanliga och som kan förhindra att ett besök räknas som ett studs. Google Analytics skickar vanligtvis inte mer än en databegäran på samma sida.

Om du vill få en bättre paritet mellan rapporteringsverktygen använder du [!UICONTROL Single Page Visits]-måttet i Adobe Analytics i stället för [!UICONTROL Bounces] som en del av ett beräknat mått. Måttet [!UICONTROL Single Page Visits] innehåller det totala antalet besök som endast inkluderade en sidvy, eller besök som kom in på webbplatsen men inte inkluderade ett klick till en annan sida.

Mer information finns i [Studsfrekvensen](/help/components/metrics/bounce-rate.md) i användarhandboken för komponenter.

## [!UICONTROL Visits] och sessioner

[!UICONTROL Visits] (kallas sessioner i Google Analytics) är en grupp sidvyer som har gjorts av samma användare på kort tid. [!UICONTROL Visits] på båda plattformarna upphör vanligtvis efter 30 minuters inaktivitet. Båda plattformarna tillåter anpassning när [!UICONTROL Visit] förfaller. Det finns flera scenarier som kan orsaka skillnader på olika plattformar.

* **Dagens slut:** Alla sessioner i Google Analytics går ut efter klockan 11:59 en viss dag. Om användaren fortfarande är aktiv på webbplatsen efter kl. 12.00 skapas en ny session. Adobe Analytics fortsätter att besöka följande dag som en del av samma besök.
* **Olika kampanjer:** En ny session i Google Analytics påbörjas om en användares kampanjkälla ändras. Om ett nytt [!UICONTROL Tracking Code]-värde visas i Adobe Analytics räknas det som en del av samma besök.
* **Åsidosättning av manuell session:** En ny session i Google Analytics startas om du använder `sessionControl` för att starta eller avsluta en session manuellt. [!UICONTROL Visits] kan inte avslutas manuellt i Adobe Analytics.
* **Identifiering av tidigare besök i Adobe Analytics:** En ny [!UICONTROL Visit] i Adobe Analytics startas automatiskt om en användare uppnår 12 timmars kontinuerlig aktivitet, 2 500 träffar eller 100 träffar inom 100 sekunder. Vart och ett av dessa detekteringskriterier aktiveras vanligtvis av båda aktiviteterna.

Mer information finns i måttet [Besök](/help/components/metrics/visits.md) i användarhandboken för komponenter.
