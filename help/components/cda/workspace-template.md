---
title: CDA Workspace-mall
description: Beskriver varje fält i CDA-mallen i Analysis Workspace.
exl-id: 293001ff-bf7b-4de8-b175-7c2c17d1794d
feature: CDA
role: Admin
source-git-commit: d37fa0aff0b1bbe196b943bc26e86b1e79936184
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 0%

---

# CDA Workspace-mall

{{available-existing-customers}}

Adobe erbjuder en mall för att se viktiga prestandadata för olika enheter.

1. Navigera till [ExperienceCloud.adobe.com](https://experiencecloud.adobe.com) och logga in med dina inloggningsuppgifter för AdobeID.
1. Klicka på ikonen med nio rutnät längst upp och klicka sedan på Analytics (Analyser).
1. Klicka på [!UICONTROL Workspace] överst och sedan på [!UICONTROL Create New Project].
1. Leta reda på mallen för enhetsövergripande analys och klicka sedan på [!UICONTROL Create].
1. Ändra rapportsviten till en som stöder CDA om du uppmanas till detta.

Ett Analysis Workspace-projekt som innehåller flera paneler skapas. Överst visas en innehållsförteckning och en introduktion som gör det möjligt att komma åt rapporten och navigera till enskilda rapporter. Klicka på en länk i innehållsförteckningen eller expandera en panels dragspelspanel för att visa dessa rapporter.

<!--The content below is mirrored in /help/analyze/analysis-workspace/build-workspace-project/starter-projects.md-->

* **Identifiering av användare**: Visar hur ofta besökare på din webbplats identifieras med metoder som baseras på enhetsövergripande analys.
* **Mäta målgruppsstorlek**: Visar en jämförelse mellan Unika enheter och Personer. Andelen av dessa två tal kallas för komprimering mellan enheter, ett beräknat mått som visas på den här panelen. Detta komprimeringsmått är beroende av ett stort antal faktorer:
   * Inloggningsfrekvens: Ju fler användare loggar in på er webbplats, desto mer kan Adobe identifiera och sätta ihop besökare på olika enheter. Platser med låg inloggningshastighet har också låg komprimeringshastighet.
   * Experience Cloud ID-täckning: Endast besökare med ett ECID kan sammanfogas. En lägre andel besökare på er webbplats som använder ett ECID-kort motsvarar lägre komprimeringsgrader.
   * Användning av flera enheter: Om besökare på platsen inte använder flera enheter kan du se lägre komprimeringsgrader.
   * Rapporteringsnoggrannhet: Komprimering per dag är vanligtvis mindre än komprimering per månad eller år. Risken för att en individ ska använda flera enheter blir mindre inom en dag än under en hel månad. Segmentering, filtrering eller användning av nedbrytningsdimensioner kan också ge en lägre komprimeringsgrad.
* **Personbaserade segment**: Innehåller en segmentlistruta där du kan visa enhetsspecifika data. Den här panelen uppmuntrar till experimenterande med segment för att se hur rapporter påverkas om du inkluderar eller utesluter enhetstyper.
* **Analyserar enhetsövergripande resa**: Tillhandahåller flödes- och utfallsrapporter baserat på enhetstyp.
* **Attribuering över flera enheter**: Kombinera funktionerna för analys och attribuering mellan olika enheter.
* **Andra tips och tricks**: Användbara ämnen om CDA som gör att du kan få ut mer av att använda det.
