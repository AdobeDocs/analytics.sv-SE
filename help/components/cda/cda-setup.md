---
title: Konfigurera enhetsövergripande analys
description: Lär dig hur du konfigurerar enhetsövergripande analys när du uppfyller kraven.
translation-type: tm+mt
source-git-commit: 2faec7513624be207a6cf01545702a977a84d5fc

---


# Konfigurera enhetsövergripande analys

> [!NOTE] Enhetsövergripande analysdokumentation kan komma att ändras i takt med att funktionen utvecklas ytterligare. Kontrollera regelbundet om det finns uppdateringar.

När alla förutsättningar är uppfyllda gör du följande för att aktivera enhetsövergripande analys. Du måste tillhöra en produktprofiladministratörsgrupp eller ha administratörsbehörighet i Adobe Analytics för att kunna följa dessa steg.

> [!IMPORTANT] Alla förutsättningar måste vara uppfyllda innan du följer dessa steg. Om alla förutsättningar inte uppfylls är funktionen inte tillgänglig eller fungerar inte. Se [Enhetsövergripande analys](cda-home.md) för krav och begränsningar.

## Välj den rapportsvit för olika enheter som ska aktiveras för CDA

När organisationen har etablerats för att använda CDA väljer du vilken rapporteringssvit som ska användas. Du kan kommunicera detta via din kontohanterare på Adobe. Adobe aktiverar sedan det rapporteringsprogram du valt för CDA-bearbetning.

## Skapa en virtuell rapportsvit för olika enheter för att se vyn över olika enheter

Administratörer med behörighet att skapa virtuella rapportsviter kan skapa virtuella CDA-rapportsviter enligt följande:

1. Navigera till [experienceCloud.adobe.com](https://experiencecloud.adobe.com) och logga in med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på ikonen med nio rutnät längst upp och klicka sedan på Analytics (Analyser).
3. Håll muspekaren över komponenterna överst och klicka sedan på Virtuella rapportsviter.
4. Klicka på Lägg till.
5. Ange ett namn för den virtuella rapportsviten och kontrollera att den CDA-aktiverade rapportsviten är vald.
6. (Valfritt) Använd ett segment i den virtuella rapportsviten. Du kan till exempel använda ett segment som begränsar den virtuella rapportsviten till datum efter att CDA aktiverats och sammanfogningen påbörjats. Med det här segmentet kan användare endast se datumintervall i sammanslagna VRS.
7. Klicka på kryssrutan Aktivera rapporttidsbearbetning, som aktiverar flera fler alternativ, bland annat Enhetsövergripande analys.
8. Klicka i kryssrutan &quot;Häfta användarbesök mellan enheter&quot;.
9. Klicka på Fortsätt, avsluta konfigurationen av den virtuella rapportsviten och klicka sedan på Spara.

![CDA-kryssruta](assets/cda-checkbox.png)

## Tillägg och ändringar i virtuella rapportsviter för olika enheter

När Enhetsövergripande analys är aktiverat på en virtuell rapportserie bör du tänka på följande ändringar:

* En ny ikon för olika enheter visas bredvid namnet på den virtuella rapportsviten. Den här ikonen är exklusiv för virtuella rapportsviter på olika enheter.
* Det finns en ny dimension med namnet Identifierad status. Den här dimensionen avgör om Experience Cloud ID för den träffen vid den tidpunkten är känt av enhetsdiagrammet.
* Det finns nya mätvärden som heter Personer och Unika enheter.
* Måttet Unika besökare är inte tillgängligt eftersom det ersätts med Personer och Unika enheter.
* När du skapar segment ersätts segmentbehållaren &quot;Visitor&quot; med en &quot;Person&quot;-behållare.

## CDA Workspace-mall

Adobe erbjuder en mall för att se viktiga prestandadata för olika enheter.

1. Navigera till [experienceCloud.adobe.com](https://experiencecloud.adobe.com) och logga in med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på ikonen med nio rutnät längst upp och klicka sedan på Analytics (Analyser).
1. Klicka [!UICONTROL Workspace] överst och sedan på [!UICONTROL Create New Project].
1. Gå till&quot;Journey IQ: Mallen för enhetsanalys&quot; och klicka sedan på [!UICONTROL Create].
1. Ändra rapportsviten till en som stöder CDA om du uppmanas till detta.

Ett Analysis Workspace-projekt skapas som innehåller flera paneler. Överst visas en innehållsförteckning och en introduktion som gör det möjligt att komma åt rapporten och navigera till enskilda rapporter. Klicka på en länk i innehållsförteckningen eller expandera en panels dragspelspanel för att visa dessa rapporter.

<!-->The content below is mirrored in /help/analyze/analysis-workspace/build-workspace-project/starter-projects.md<-->

* **Specialanteckning för medlemmarna i Co-op Graph**: Visar vilken del av rapportsviten som innehåller besökare i regioner där koordinatdiagrammet stöds och regioner där det inte stöds.
* **Identifiering av användare**: Visar hur ofta besökare på er webbplats identifieras med hjälp av metoder som baseras på enhetsövergripande analys.
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
