---
title: Implementera med taggar i Adobe Experience Platform
description: Lär dig implementera Adobe Analytics med hjälp av taggar
feature: Launch Implementation
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
source-git-commit: f4b495b11bcbd55bc8448f2c9c09268547fb9750
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 0%

---

# Implementera med taggar i Adobe Experience Platform

Under Adobe Analytics livstid har Adobe erbjudit flera olika metoder för att implementera kod på er webbplats för datainsamling. Adobe nuvarande rekommenderade metod är via taggar i Adobe Experience Platform.

Taggar i Adobe Experience Platform är en tagghanteringslösning som gör att ni kan driftsätta Analytics-kod tillsammans med andra taggningskrav. Adobe erbjuder integreringar med andra lösningar och produkter och låter er driftsätta anpassad kod. Alla dessa uppgifter kan utföras utan att någon utvecklingsteam i organisationen behöver uppdatera koden på er webbplats.

Alla kunder som har ett aktivt Adobe Experience Cloud-kontrakt kan använda taggar. Om du är osäker på om du har åtkomst kan du kontakta någon av Experience Cloud systemadministratörerna i din organisation.

## Allmänt arbetsflöde

Så här hämtar du en implementering som körs med taggar:

1. **Få åtkomst till taggar**: Du kan få åtkomst till plattformstaggar via en systemadministratör i din organisation.
2. **Skapa en taggegenskap**: Egenskaper är överliggande behållare som används för att referera till tagghanteringsdata.
3. **Distribuera till en utvecklingsmiljö**: Ha en miljö där du kan iterera om taggutveckling.
4. **Validera och publicera i produktion**: Se till att allt fungerar och publicera det sedan live.

Se [Skapa en Analytics-taggegenskap](create-analytics-property.md) för att komma igång.

## Ytterligare resurser

Taggar kan anpassas mycket. Läs mer om hur du får ut mesta möjliga av Adobe Analytics genom att inkludera rätt data i implementeringen.

* [Dokumentation för taggar](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en#): Lär dig hur gränssnittet fungerar och vilka tillägg som är tillgängliga.
* [Adobe Analytics-tillägg](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=en): Använd Analytics-tillägget för att skicka data till Adobe Analytics.
* [Implementeringsvariabler](../vars/overview.md): Avgör vilka variabler du vill skicka till datainsamlingsservrar.
