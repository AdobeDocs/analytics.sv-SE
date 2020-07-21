---
title: CDA Workspace-mall
description: Beskriver varje fält i CDA-mallen i Analysis Workspace.
translation-type: tm+mt
source-git-commit: 2e7ec3b2e4401b02005b3099dae2bb34c64a6846
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 0%

---


# CDA Workspace-mall

Adobe erbjuder en mall för att se viktiga prestandadata för olika enheter.

1. Navigera till [experienceCloud.adobe.com](https://experiencecloud.adobe.com) och logga in med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på 9-rutnätikonen överst och sedan på Analytics.
1. Klicka [!UICONTROL Workspace] överst och sedan på [!UICONTROL Create New Project].
1. Gå till&quot;Journey IQ: Analytics-mall för olika enheter och klicka sedan på [!UICONTROL Create].
1. Ändra rapportsviten till en som stöder CDA om du uppmanas till detta.

Ett Analysis Workspace-projekt skapas som innehåller flera paneler. Överst visas en innehållsförteckning och en introduktion som gör det möjligt att komma åt rapporten och navigera till enskilda rapporter. Klicka på en länk i innehållsförteckningen eller expandera en panels dragspelspanel för att visa dessa rapporter.

<!-->The content below is mirrored in /help/analyze/analysis-workspace/build-workspace-project/starter-projects.md<-->

* **Specialanteckning för medlemmarna i Co-op Graph**: Visar vilken del av rapportsviten som innehåller besökare i regioner där koordinatdiagrammet stöds och regioner där det inte stöds.
* **Identifiering av användare**: Visar hur ofta besökare på din webbplats identifieras med hjälp av metoder som baseras på Analytics för olika enheter.
* **Mäta målgruppens storlek**: Visar en jämförelse mellan Unika enheter och Personer. Andelen av dessa två tal kallas för komprimering mellan enheter, ett beräknat mått som visas på den här panelen. Detta komprimeringsmått är beroende av ett stort antal faktorer:
   * Använda Co-op-diagrammet eller det privata diagrammet: I allmänhet tenderar organisationer som använder enhetskoordinaterna att se bättre komprimeringsgrader än organisationer som använder det privata diagrammet.
   * Inloggningshastighet: Ju fler användare som loggar in på er webbplats, desto mer kan Adobe identifiera och sätta ihop besökare på olika enheter. Platser med låg inloggningshastighet har också låg komprimeringshastighet.
   * Experience Cloud ID-täckning: Endast besökare med ett ECID kan sammanfogas. En lägre andel besökare på er webbplats som använder ett ECID-kort motsvarar lägre komprimeringsgrader.
   * Användning av flera enheter: Om besökarna på webbplatsen inte använder flera enheter kan du se lägre komprimeringsgrader.
   * Rapportgranularitet: Komprimering per dag är vanligtvis mindre än komprimering per månad eller år. Risken för att en individ ska använda flera enheter blir mindre inom en dag än under en hel månad. Segmentering, filtrering eller användning av nedbrytningsdimensioner kan också ge en lägre komprimeringsgrad.
* **Personbaserade segment**: Innehåller en segmentlistruta där du kan visa enhetsspecifika data. Den här panelen uppmuntrar till experimenterande med segment för att se hur rapporter påverkas om du inkluderar eller utesluter enhetstyper.
* **Analysera resan** mellan olika enheter: Tillhandahåller flödes- och utfallsrapporter baserat på enhetstyp.
* **Tilldelning** mellan enheter: Kombinera Journey IQ och Attribution IQ tillsammans.
* **Andra tips och tricks**: Hjälpsamma ämnen kring CDA som gör att du kan få ut mer av att använda det.
