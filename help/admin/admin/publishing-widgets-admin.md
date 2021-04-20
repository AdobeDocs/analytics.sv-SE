---
description: En publiceringswidget är en behållare där du kan bädda in marknadsföringsrapporter (bokmärken och instrumentpaneler) på en webbsida. Personer i organisationen som inte har tillgång till marknadsföringsrapporter kan visa relevanta data.
title: Publiceringswidget
feature: Admin Tools
uuid: 4ecf6a5a-8a4e-4707-b282-39890eba3c5d
exl-id: 97ec07d8-29ad-4ef3-9227-bfdc14a59b97
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 1%

---

# Publiceringswidget

En publiceringswidget är en behållare som gör att du kan bädda in analysrapporter (bokmärken och instrumentpaneler) på en webbsida. Personer i organisationen som inte har tillgång till analysrapporter kan visa relevanta data.

Du kan till exempel skapa en kontrollpanel så att företagsledningen kan se antalet besökare, antalet unika sidbesökare och så vidare.

>[!CAUTION]
>
>Ingen autentisering krävs för att visa data som publicerats via publiceringswidgeten. På grund av detta bör publicerade data inte anses vara säkrare än data som skickas till en e-postgrupp eller listserver. Använd widgeten endast i enlighet med organisationens säkerhetsstandarder, befintliga avtalskrav och tillämplig lag. Med publiceringswidgeten kan du begränsa, per IP-adress eller domänsökväg, var du kan publicera data. Dessa mekanismer är dock enbart avsedda att förhindra oavsiktlig datadistribution och är inte ett effektivt sätt att säkra åtkomst till data som distribueras via publiceringswidgeten.
>
> Adobe tar inget ansvar för data som exponeras via publiceringswidgeten.

Eftersom Publishing Widget kan generera stora trafikvolymer förbehåller sig Adobe rätten att, efter eget gottfinnande, inaktivera ett företags publiceringswidgetar för felaktig användning eller för stor trafik som påverkar den totala prestandan.

## Felsökning - publicera Widget Cache

Första gången någon ser den distribuerade publiceringswidgeten körs rapporten av widgeten. När rapporten har körts läggs resultaten till i ett cacheminne och är giltiga i 1 timme. Efterföljande användare som visar publiceringswidgeten inom en timme kommer att se den cachelagrade versionen (den returneras omedelbart). När en timme har gått tvingas alla efterföljande användare som visar publiceringswidgeten att köra rapporten igen, och sedan cachelagras dessa resultat och så vidare. På så sätt är uppgifterna garanterat högst en timme gamla.

Om du ser dataskillnader mellan publiceringswidgeten och rapportgränssnittet kan du behöva rensa publiceringswidgetens cache.

1. Klicka i publiceringswidgeten (så att widgeten har fokus).
1. Klicka på **[!UICONTROL Save]** i widgeten.
1. Kör widgeten igen. (Förhandsgranskningsläget använder inte widgetens cache.)

>[!NOTE]
>
>Publiceringswidgetar visar bara den första datakolumnen i en rapport.

## Beskrivning av publiceringswidgetar {#section_D67478AECCA946B19A3E4C7071EB4871}

| Element | Beskrivning |
|--- |--- |
| Namn | Widgetens namn. |
| Beskrivning | (Valfritt) Ange en beskrivning för widgeten. |
| Rapport | I den övre listrutan Rapport väljer du en mapp eller en kontrollpanel. Välj ett rapportmärke eller bokmärke i den nedre listrutan Rapport.  Dessa rapporter kräver ingen besöksautentisering. <br>När en besökare läser in en webbsida som innehåller en publiceringswidget visar widgeten automatiskt den associerade rapporten med aktuella rapportdata. Ändringar i en publiceringswidget, till exempel ändring av den associerade rapporten, uppdaterar automatiskt rapportutdata för alla webbsidor som använder den widgeten, utan att du behöver distribuera om webbsidorna.</br> |
| Mål | Ange widgetens mål.   Destinationerna måste ha ett giltigt URL-format, inklusive prefixet https:// eller https://. Publiceringswidgetens mål är inkluderade, vilket innebär att publiceringswidgeten fungerar på alla URL:er som innehåller det angivna målet. <br>Om du till exempel anger som mål för https://www.corp1.com/sales/ kan du publicera widgetar på alla webbsidor på eller under försäljningssidan på www.corp1.com webbplats.</br> |
