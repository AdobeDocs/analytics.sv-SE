---
title: Enhetsdiagram
description: Förstå förutsättningarna och begränsningarna med att sammanfoga data med enhetsdiagrammet.
exl-id: b8408a7d-6aff-4fff-b535-f10d422bcf0d
feature: CDA
role: Admin
source-git-commit: cc0b8703d6b6488adf9a2ea41a51001538d1cbee
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 1%

---


# Enhetsdiagram

{{available-existing-customers}}

Enhetsövergripande analyser kan använda det privata diagrammet för att sammanfoga data. Det privata diagrammet är en databas med hash-kodade enhets-ID:n som är specifika för din organisation. CDA kommunicerar regelbundet med enhetsdiagrammet för att länka samman enheter.

## Förutsättningar som är specifika för enhetsdiagrammet

Om du tänker implementera korsenhetsanalys med enhetens diagrammetod krävs följande. Arbeta med team inom organisationen och kontoteamet på Adobe för att säkerställa att ni uppfyller alla följande.

>[!WARNING]
>
>Om du inte uppfyller alla krav kan det leda till att det inte går att aktivera enhetsövergripande analys eller dåliga resultat när du sammanfogar data.
>

* Alla krav som anges på [översiktssidan](overview.md).
* Din organisation måste använda [Adobe Experience Platform Identity Service Private Graph](https://business.adobe.com/se/products/experience-platform/identity-service.html). Se även [hemsidan](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=sv) i användarhandboken för identitetstjänsten.
* Implementeringen måste använda den senaste versionen av Experience Cloud ID Service (ECID). Se [hemsidan](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=sv-SE) i användarhandboken för ID-tjänsten. I de flesta implementeringar som använder [taggar](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=sv-SE) i Adobe Experience Platform har ID-tjänsten antagligen redan distribuerats.
* Implementeringen måste anropa funktionen `setCustomerIDs` (eller motsvarande SDK) när en individ kan identifieras, till exempel när en användare loggar in eller öppnar ett e-postmeddelande. Detta krav gäller alla plattformar, inklusive mobilappar om de används. Se [`setCustomerIDs`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html?lang=sv-SE) i användarhandboken för ID-tjänsten.

## Begränsningar som är specifika för enhetsdiagrammet

* Äldre analys-ID:n stöds inte. Endast besökare med Experience Cloud ID sammanfogas.
* Om din organisation använder ett privat diagram tar det upp till 24 timmar för nya enheter att sy ihop.
* Enhetsdiagram från tredje part stöds inte.

## Nästa steg

När din organisation uppfyller alla krav och förstår begränsningarna kan du starta [Konfigurera korsanalys](setup.md).
