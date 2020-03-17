---
title: Implementera med Launch-översikt
description: Lär dig implementera Adobe Analytics med Adobe Experience Platform Launch
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# Implementera med Launch-översikt

Under Adobe Analytics livstid har Adobe erbjudit flera olika metoder för att implementera kod på er webbplats för datainsamling. Adobes nuvarande rekommendationsmetod är Adobe Experience Platform Launch.

Launch är en tagghanteringslösning som gör att ni kan driftsätta Analytics-kod tillsammans med andra taggningskrav. Adobe erbjuder integreringar med andra lösningar och produkter och låter er driftsätta anpassad kod. Alla dessa uppgifter kan utföras utan att någon utvecklingsteam i organisationen behöver uppdatera koden på er webbplats.

Alla kunder med ett aktivt Adobe Experience Cloud-avtal kan använda Launch. Om du är osäker på om du har åtkomst kontaktar du en av organisationens Experience Cloud-systemadministratörer.

## Allmänt arbetsflöde

Så här hämtar du en implementering som körs med Launch:

1. **Få åtkomst till Launch**: Du kan få åtkomst till Launch via en systemadministratör i din organisation.
2. **Skapa en egenskap**: Egenskaper är överliggande behållare som används för att referera till tagghanteringsdata.
3. **Driftsätt i en utvecklingsmiljö**: Ha en miljö där du kan iterera om taggutveckling.
4. **Validera och publicera i produktion**: Se till att allt fungerar och publicera det sedan live.

Se [Skapa en Analytics-egenskap i Adobe Experience Platform Launch](create-analytics-property.md) för att komma igång.

## Ytterligare resurser

Launch kan anpassas mycket. Läs mer om hur ni får ut mesta möjliga av Adobe Analytics genom att inkludera rätt data i er implementering.

* [Startdokumentation](https://docs.adobe.com/content/help/en/launch/using/overview.html): Lär dig hur gränssnittet fungerar och vilka tillägg som är tillgängliga.
* [Adobe Analytics-tillägg](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html): Använd Analytics-tillägget för att skicka data till Adobe Analytics.
* [Implementeringsvariabler](../vars/overview.md): Avgör vilka variabler du vill skicka till datainsamlingsservrar.
