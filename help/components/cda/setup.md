---
title: Ställ in enhetsövergripande analys
description: Konfigurera en virtuell rapportsvit för att aktivera CDA.
translation-type: tm+mt
source-git-commit: 60fe85adaebee8ca390e59727dda949c12c1ee26
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 0%

---


# Ställ in enhetsövergripande analys

När alla förutsättningar är uppfyllda gör du följande för att aktivera enhetsövergripande analys. Du måste tillhöra en produktprofiladministratörsgrupp eller ha administratörsbehörighet i Adobe Analytics för att kunna följa dessa steg.

>[!IMPORTANT]
>
>Alla förutsättningar måste vara uppfyllda innan du följer dessa steg. Om alla förutsättningar inte uppfylls är funktionen inte tillgänglig eller fungerar inte. Se [översiktssidan](overview.md) och önskad sammanfogningsmetod ([Fältbaserad sammanfogning](field-based-stitching.md) respektive [Enhetsdiagram](device-graph.md)) för krav och begränsningar.

## Välj den rapportsvit för olika enheter som ska aktiveras för CDA

När organisationen har etablerats för att använda CDA väljer du vilken rapporteringssvit som ska användas. Det här alternativet kan kommuniceras via din kontohanterare på Adobe. Adobe aktiverar sedan det rapporteringsprogram du valt för CDA-bearbetning.

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
* Det finns en ny dimension med namnet [Identifierad](../dimensions/identified-state.md) . Det här måttet avgör om Experience Cloud-ID:t för träffen vid den tidpunkten är känt av enhetsdiagrammet.
* Det finns nya mätvärden med etiketten [Personer](../metrics/people.md) och [Unika enheter](../metrics/unique-devices.md) .
* Mätvärdena för [unika besökare](../metrics/unique-visitors.md) är inte tillgängliga eftersom de ersätts med Personer och Unika enheter.
* När du skapar segment ersätts segmentbehållaren &quot;Visitor&quot; med en &quot;Person&quot;-behållare.
