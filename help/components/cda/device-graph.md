---
title: Enhetsdiagram
description: Förstå förutsättningarna och begränsningarna med att sammanfoga data med hjälp av enhetsdiagrammet.
exl-id: b8408a7d-6aff-4fff-b535-f10d422bcf0d
source-git-commit: 3f4d8df911c076a5ea41e7295038c0625a4d7c85
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# Enhetsdiagram

Enhetsövergripande analys erbjuder två olika metoder för att sammanfoga data. Den här metoden använder Adobe Experience Platform Identity Service Co-op Graph eller Private Graph för att knyta ihop data. CDA kommunicerar regelbundet med enhetsdiagrammet för att länka samman enheter.

## Skillnader mellan foto-diagram och privat diagram

Adobe erbjuder två typer av enhetsdiagram som en del av ID-tjänsten:

* **Samredigeringsdiagram**: En databas med hash-kodade enhets-ID:n som alla kunder kan bidra till och referera till. Eftersom den här typen av enhetsdiagram fungerar tillsammans matchar det vanligtvis fler enheter än ett privat diagram.
* **Privat diagram**: En databas med hashas-enhets-ID:n som bara din organisation refererar till.

## Förutsättningar som är specifika för enhetsdiagrammet

Om du tänker implementera korsenhetsanalys med enhetens diagrammetod krävs följande. Samarbeta med team inom organisationen och kontohanteraren för Adobe för att säkerställa att ni uppfyller alla följande:

>[!WARNING]
>
>Om du inte uppfyller alla krav kan det leda till att det inte går att aktivera enhetsövergripande analys eller dåliga resultat när data sammanfogas.

* Alla krav som anges på [översiktssida](overview.md).
* Din organisation måste använda Adobe Experience Platform Identity Service Co-op Graph eller Private Graph. Se [Hemsida](https://experienceleague.adobe.com/docs/device-co-op/using/home.html) i användarhandboken för Device Co-op.
* Implementeringen måste använda den senaste versionen av Experience Cloud ID-tjänsten. Se [Hemsida](https://experienceleague.adobe.com/docs/id-service/using/home.html) i användarhandboken för Experience Cloud Identity Service. De flesta implementeringar som använder taggar i Adobe Experience Platform har troligen redan ECID.
* Implementeringen måste anropa `setCustomerIDs` -funktion (eller SDK-motsvarighet) när en individ kan identifieras, till exempel när en användare loggar in eller öppnar ett e-postmeddelande. Detta krav gäller alla plattformar, inklusive mobilappar om de används. Se [`setCustomerIDs`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html) i användarhandboken för Experience Cloud Identity Service.

## Begränsningar som är specifika för enhetsdiagrammet

* Äldre analys-ID:n stöds inte. Endast besökare med Experience Cloud ID sammanfogas.
* Om din organisation använder ett privat diagram tar det upp till 24 timmar för nya enheter att sy ihop.
* Om din organisation använder Co-op Graph kan det ta upp till två veckor för nya enheter som besöker din webbplats att sammanfogas. Symbolnivån i CDA under de senaste två veckorna är vanligtvis lägre än för datumintervall som är äldre än två veckor.
* Enhetsdiagram från tredje part stöds inte.

## Nästa steg

När organisationen uppfyller alla krav och förstår begränsningarna kan du börja [Konfigurera enhetsövergripande analys](setup.md).
