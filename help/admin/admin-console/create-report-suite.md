---
title: Skapa en rapportsvit
description: Skapa en grundläggande behållare för datainsamling i Adobe Analytics.
translation-type: tm+mt
source-git-commit: 984d6034d14cc4256d93bd4f7d1a7f01b63b71e9

---


# Skapa en rapportsvit

En rapportsvit är en silo data som Adobe Analytics använder för att ta fram rapporter. En organisation kan ha många rapportsviter, som alla innehåller olika datauppsättningar. Även om separata rapportsviter var viktiga tidigare har det blivit mer fördelaktigt att ha en enda rapportserie. Tack vare introduktionen till virtuella rapportsviter och tidsbearbetning av rapporter kan användaren skapa egna underuppsättningar av data, vilket ger flexibilitet att hämta både globala och platsspecifika data.

Den här artikeln är avsedd för administratörer på systemnivå eller administratörer av analyser som förbereder datainsamling.

## Förutsättningar

[Adobe Analytics First Admin Guide](first-admin-guide.md): Se till att en administratör på systemnivå har gett dig åtkomst till Adobe Analytics via Experience Cloud Admin Console

## Skapa en rapportsvit

> [!NOTE] Det finns också ett sätt att skapa en rapportserie i Adobe Analytics med den äldre administratören. Adobe rekommenderar att du använder guiden för rapportsvitskonfiguration som beskrivs här.

1. Logga in på [experienceCloud.adobe.com](https://experiencecloud.adobe.com) med inloggningsuppgifterna för ditt Adobe ID.
1. Klicka på ikonen med nio kvadrater i det övre högra hörnet och klicka sedan på den färgade Analytics-logotypen.
1. Ett modalt fönster&quot;Välkommen till Adobe Analytics&quot; visas automatiskt. Om du inte gör det klickar du på hjälpikonen i det övre högra hörnet och väljer sedan Välkommen till Adobe Analytics.
1. Klicka på Starta inställning i det modala fönstret.
1. Följ varje uppmaning som visar grunderna som egenskapstyp, branscher och tidszon. Klicka på Nästa.
1. Rapportsviten har skapats. Adobe rekommenderar också att man har en utvecklingsrapportsserie så att testningen inte belastar kunddata. Klicka på hjälpikonen i det övre högra hörnet och välj sedan Välkommen till Adobe Analytics igen.
1. Klicka på Starta inställning i det modala fönstret.
Ge den här rapportsviten samma namn, förutom att lägga till &quot;- DEV&quot; i slutet. Eftersom den här rapportsviten endast tar emot intern trafik kan den uppskattade storleken vara den minsta.
1. Klicka på Nästa för att slutföra skapandet av utvecklingsrapportsviten.

Mer information om stegen i det här modala fönstret finns i [Implementeringsmodalt](/help/implement/prepare/implementation-modal.md) i Implementeringsanvändarhandboken.

## Felsökning

**När du har loggat in på Experience Cloud är Analytics-ikonen nedtonad.**

Det innebär att ditt konto inte har tilldelats rätt behörigheter till Analytics. Arbeta med en systemnivåadministratör i organisationen för att säkerställa att du tillhör en profil med tillräcklig behörighet för att få tillgång till Adobe Analytics.

**När du har loggat in på Adobe Analytics saknas popup-menyn Välkommen till Adobe Analytics.**

Se till att du har loggat in via Experience Cloud, och inte via my.omniture.com. Användare som loggar in via my.omniture.com har inte tillgång till installationsguiden för rapportsviten.

## Nästa steg

[Skapa och konfigurera en egenskap för Adobe Analytics i Launch](/help/implement/launch/create-analytics-property.md): Skapa ett område för att hantera er Analytics-implementering
