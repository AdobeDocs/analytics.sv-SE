---
title: Enhetsdiagram
description: Förstå förutsättningarna och begränsningarna med att sammanfoga data med enhetsdiagrammet.
exl-id: b8408a7d-6aff-4fff-b535-f10d422bcf0d
feature: CDA
role: Admin
source-git-commit: 6c74f4d4c14765742a2aafdfff2a083c6b0a7183
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---


# Enhetsdiagram

{{available-existing-customers}}

>[!WARNING]
>
>Enhetsdiagram inom enhetsövergripande analys är inte längre tillgängligt den **31 december 2025**. Växla en eventuell aktiverad virtuell rapportsvit för enhetsdiagram till den [fältbaserade metoden](/help/components/cda/field-based-stitching.md).
>

Enhetsövergripande analyser kan använda det privata diagrammet för att sammanfoga data. Det privata diagrammet är en databas med hash-kodade enhets-ID:n som är specifika för din organisation. CDA kommunicerar regelbundet med enhetsdiagrammet för att länka samman enheter.

## Förutsättningar som är specifika för enhetsdiagrammet

Om du tänker implementera korsenhetsanalys med enhetens diagrammetod krävs följande. Samarbeta med team i er organisation och i er kontogrupp på Adobe för att säkerställa att ni uppfyller alla följande krav.

>[!WARNING]
>
>Om du inte uppfyller alla krav kan det leda till att det inte går att aktivera enhetsövergripande analys eller dåliga resultat när du sammanfogar data.
>

* Alla krav som anges på [översiktssidan](overview.md).
* Din organisation måste använda [Adobe Experience Platform Identity Service Private Graph](https://business.adobe.com/products/experience-platform/identity-service.html). Se även [hemsidan](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=sv) i användarhandboken för identitetstjänsten.
* Implementeringen måste använda den senaste versionen av Experience Cloud ID Service (ECID). Se [hemsidan](https://experienceleague.adobe.com/docs/id-service/using/home.html) i användarhandboken för ID-tjänsten. I de flesta implementeringar som använder [taggar](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) i Adobe Experience Platform har ID-tjänsten antagligen redan distribuerats.
* Implementeringen måste anropa funktionen `setCustomerIDs` (eller motsvarande för SDK) när en individ kan identifieras, till exempel när en användare loggar in eller öppnar ett e-postmeddelande. Detta krav gäller alla plattformar, inklusive mobilappar om de används. Se [`setCustomerIDs`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html) i användarhandboken för ID-tjänsten.

## Begränsningar som är specifika för enhetsdiagrammet

* Äldre analys-ID:n stöds inte. Det är bara besökare med Experience Cloud ID som sammanfogas.
* Om din organisation använder ett privat diagram tar det upp till 24 timmar för nya enheter att sy ihop.
* Enhetsdiagram från tredje part stöds inte.

## Nästa steg

När din organisation uppfyller alla krav och förstår begränsningarna kan du starta [Konfigurera korsanalys](setup.md).
