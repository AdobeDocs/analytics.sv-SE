---
title: Konfigurera Analytics för olika enheter
description: Konfigurera en virtuell rapportsvit för att aktivera CDA.
translation-type: tm+mt
source-git-commit: 2e7ec3b2e4401b02005b3099dae2bb34c64a6846
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 0%

---


# Konfigurera Analytics för olika enheter

När alla krav är uppfyllda gör du så här för att aktivera Analytics för olika enheter. Du måste tillhöra en produktprofiladministratörsgrupp eller ha administratörsbehörighet i Adobe Analytics för att kunna följa dessa steg.

>[!IMPORTANT] Alla förutsättningar måste vara uppfyllda innan du följer dessa steg. Om alla förutsättningar inte uppfylls är funktionen inte tillgänglig eller fungerar inte. Se [översiktssidan](overview.md) och önskad sammanfogningsmetod ([Fältbaserad sammanfogning](field-based-stitching.md) respektive [Enhetsdiagram](device-graph.md)) för krav och begränsningar.

## Välj den rapportsvit för olika enheter som ska aktiveras för CDA

När organisationen har etablerats för att använda CDA väljer du vilken rapporteringssvit som ska användas. Du kan kommunicera detta via din kontohanterare på Adobe. Adobe aktiverar sedan det rapporteringsprogram du valt för CDA-bearbetning.

## Skapa en virtuell rapportsvit för olika enheter för att se vyn över olika enheter

Administratörer med behörighet att skapa virtuella rapportsviter kan skapa virtuella CDA-rapportsviter enligt följande:

1. Navigera till [experienceCloud.adobe.com](https://experiencecloud.adobe.com) och logga in med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på 9-rutnätikonen överst och sedan på Analytics.
3. Håll muspekaren över komponenterna överst och klicka sedan på Virtuella rapportsviter.
4. Klicka på Lägg till.
5. Ange ett namn för den virtuella rapportsviten och kontrollera att den CDA-aktiverade rapportsviten är vald.
6. (Valfritt) Använd ett segment i den virtuella rapportsviten. Du kan till exempel använda ett segment som begränsar den virtuella rapportsviten till datum efter att CDA aktiverats och sammanfogningen påbörjats. Med det här segmentet kan användare endast se datumintervall i sammanslagna VRS.
7. Klicka på kryssrutan Aktivera rapporttidsbearbetning, som aktiverar flera alternativ, bland annat Analytics för olika enheter.
8. Klicka i kryssrutan &quot;Häfta användarbesök mellan enheter&quot;.
9. Klicka på Fortsätt, avsluta konfigurationen av den virtuella rapportsviten och klicka sedan på Spara.

![CDA-kryssruta](assets/cda-checkbox.png)

## Tillägg och ändringar i virtuella rapportsviter för olika enheter

När Enhetsövergripande Analytics är aktiverat på en virtuell rapportserie bör du tänka på följande ändringar:

* En ny ikon för olika enheter visas bredvid namnet på den virtuella rapportsviten. Den här ikonen är exklusiv för virtuella rapportsviter på olika enheter.
* Det finns en ny dimension med namnet Identifierad status. Det här måttet avgör om Experience Cloud-ID:t för träffen vid den tidpunkten är känt av enhetsdiagrammet.
* Det finns nya mätvärden som heter Personer och Unika enheter.
* Måttet Unika besökare är inte tillgängligt eftersom det ersätts med Personer och Unika enheter.
* När du skapar segment ersätts segmentbehållaren &quot;Visitor&quot; med en &quot;Person&quot;-behållare.
