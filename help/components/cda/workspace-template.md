---
title: CDA Workspace-mall
description: Beskriver varje fält i CDA-mallen i Analysis Workspace.
exl-id: 293001ff-bf7b-4de8-b175-7c2c17d1794d
feature: CDA
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 0%

---

# CDA Workspace-mall

Adobe erbjuder en mall för att se viktiga prestandadata för olika enheter.

1. Navigera till [experience.loud.adobe.com](https://experiencecloud.adobe.com) och logga in med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på ikonen med nio rutnät längst upp och klicka sedan på Analytics (Analyser).
1. Klicka [!UICONTROL Workspace] överst och sedan klickar du på [!UICONTROL Create New Project].
1. Leta reda på mallen för enhetsövergripande analys och klicka sedan på [!UICONTROL Create].
1. Ändra rapportsviten till en som stöder CDA om du uppmanas till detta.

Ett Analysis Workspace-projekt som innehåller flera paneler skapas. Överst visas en innehållsförteckning och en introduktion som gör det möjligt att komma åt rapporten och navigera till enskilda rapporter. Klicka på en länk i innehållsförteckningen eller expandera en panels dragspelspanel för att visa dessa rapporter.

<!--The content below is mirrored in /help/analyze/analysis-workspace/build-workspace-project/starter-projects.md-->

* **Identifiering av användare**: Visar hur ofta besökare på er webbplats identifieras med hjälp av metoder som baseras på enhetsövergripande analys.
* **Mäta målgruppens storlek**: Visar en jämförelse mellan Unika enheter och Personer. Andelen av dessa två tal kallas för komprimering mellan enheter, ett beräknat mått som visas på den här panelen. Detta komprimeringsmått är beroende av ett stort antal faktorer:
   * Inloggningshastighet: Ju fler användare som loggar in på er webbplats, desto mer kan Adobe identifiera och sätta ihop besökare på olika enheter. Platser med låg inloggningshastighet har också låg komprimeringshastighet.
   * Experience Cloud ID-täckning: Endast besökare med ett ECID kan sammanfogas. En lägre andel besökare på er webbplats som använder ett ECID-kort motsvarar lägre komprimeringsgrader.
   * Användning av flera enheter: Om besökarna på webbplatsen inte använder flera enheter kan du se lägre komprimeringsgrader.
   * Rapportgranularitet: Komprimering per dag är vanligtvis mindre än komprimering per månad eller år. Risken för att en individ ska använda flera enheter blir mindre inom en dag än under en hel månad. Segmentering, filtrering eller användning av nedbrytningsdimensioner kan också ge en lägre komprimeringsgrad.
* **Personbaserade segment**: Innehåller en segmentlistruta där du kan visa enhetsspecifika data. Den här panelen uppmuntrar till experimenterande med segment för att se hur rapporter påverkas om du inkluderar eller utesluter enhetstyper.
* **Analysera resan mellan olika enheter**: Tillhandahåller flödes- och utfallsrapporter baserat på enhetstyp.
* **Tilldelning över olika enheter**: Kombinera funktionerna i Journey IQ och Attribution IQ.
* **Andra tips och tricks**: Hjälpsamma ämnen kring CDA som gör att du kan få ut mer av att använda det.
