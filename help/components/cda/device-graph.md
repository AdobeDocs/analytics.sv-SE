---
title: Enhetsdiagram
description: Förstå förutsättningarna och begränsningarna med att sammanfoga data med hjälp av enhetsdiagrammet.
exl-id: b8408a7d-6aff-4fff-b535-f10d422bcf0d
source-git-commit: f7106ca52447988c90a3ccac6a1e1cc7514f1fc9
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 0%

---

# Enhetsdiagram

Enhetsövergripande analyser kan använda det privata diagrammet för att sammanfoga data. Det privata diagrammet är en databas med hash-kodade enhets-ID:n som är specifika för din organisation. CDA kommunicerar regelbundet med enhetsdiagrammet för att länka samman enheter.

## Förutsättningar som är specifika för enhetsdiagrammet

Om du tänker implementera korsenhetsanalys med enhetens diagrammetod krävs följande. Samarbeta med team inom organisationen och kontohanteraren för Adobe för att säkerställa att ni uppfyller alla följande:

>[!WARNING]
>
>Om du inte uppfyller alla krav kan det leda till att det inte går att aktivera enhetsövergripande analys eller dåliga resultat när data sammanfogas.

* Alla krav som anges på [översiktssida](overview.md).
* Din organisation måste använda [Privat Adobe Experience Platform Identity Service Graph](https://business.adobe.com/products/experience-platform/identity-service.html). Se även [Hemsida](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en) i användarhandboken för identitetstjänsten.
* Implementeringen måste använda den senaste versionen av Experience Cloud ID Service (ECID). Se [Hemsida](https://experienceleague.adobe.com/docs/id-service/using/home.html) i användarhandboken för ID-tjänsten. De flesta implementeringar som använder [Taggar](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) i Adobe Experience Platform har förmodligen redan en ID-tjänst distribuerad.
* Implementeringen måste anropa `setCustomerIDs` -funktion (eller SDK-motsvarighet) när en individ kan identifieras, till exempel när en användare loggar in eller öppnar ett e-postmeddelande. Detta krav gäller alla plattformar, inklusive mobilappar om de används. Se [`setCustomerIDs`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html) i användarhandboken för ID-tjänsten.

## Begränsningar som är specifika för enhetsdiagrammet

* Äldre analys-ID:n stöds inte. Endast besökare med Experience Cloud ID sammanfogas.
* Om din organisation använder ett privat diagram tar det upp till 24 timmar för nya enheter att sy ihop.
* Enhetsdiagram från tredje part stöds inte.

## Nästa steg

När organisationen uppfyller alla krav och förstår begränsningarna kan du börja [Konfigurera enhetsövergripande analys](setup.md).
