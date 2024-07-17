---
title: Ställ in enhetsövergripande analys
description: Konfigurera en virtuell rapportsvit för att aktivera CDA.
exl-id: e6d4e0c2-6b85-4f89-b51f-c0eed7a4e3da
feature: CDA
role: Admin
source-git-commit: be5a73347d417c8dc6667d4059e7d46ef5f0f5cd
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 0%

---

# Ställ in enhetsövergripande analys

När alla förutsättningar är uppfyllda gör du följande för att aktivera enhetsövergripande analys. Du måste tillhöra en produktprofiladministratörsgrupp eller ha administratörsbehörighet i Adobe Analytics för att kunna följa dessa steg.

>[!IMPORTANT]
>
>Alla förutsättningar måste vara uppfyllda innan du följer dessa steg. Om alla förutsättningar inte uppfylls är funktionen inte tillgänglig eller fungerar inte. Se [översiktssidan](overview.md) och önskad sammanfogningsmetod ([Fältbaserad sammanfogning](field-based-stitching.md) respektive [Enhetsdiagram](device-graph.md)) för krav och begränsningar.

## 1. Öppna en biljett hos Kundtjänst om du vill att CDA ska vara etablerat på din enhetsövergripande rapportsvit.

CDA tillhandahålls av Adobe Engineering på ditt enhetsövergripande rapportpaket. Kontakta Kundtjänst och be om följande information för att starta processen:

* Ditt Adobe Experience Cloud org-ID (en alfanumerisk sträng som slutar med @AdobeOrg)
* Rapportsvitens-ID för det rapportpaket för olika enheter som du vill aktivera med CDA
* Vilken metod för CDA du vill använda (Fältbaserad Stitching eller Adobe Device Graph)
* Om du tänker använda fältbaserad sammanfogning är det utkast eller den eVar som innehåller användar-ID:t
* Din inställning för repetitionsfrekvens och uppslagslängd. Du kan välja att spela upp en gång i veckan med ett 7-dagars uppslag eller att spela upp varje dag med ett 1-dagars uppslag.
Standardinställningen är veckovis uppspelning med 7-dagars uppslagsfönster. I så fall kan data under den sista veckan ändras (eftersom de successivt sammanfogas och uppdateras).

När du har försett kundtjänst med den här informationen arbetar de tillsammans med Adobe Engineering för att aktivera den rapportserie du valt för CDA-bearbetning.

## 2. Skapa en virtuell rapportserie för olika enheter för att se vyn över olika enheter.

Administratörer med behörighet att skapa virtuella rapportsviter kan skapa virtuella CDA-rapportsviter enligt följande:

1. Navigera till [ExperienceCloud.adobe.com](https://experiencecloud.adobe.com) och logga in med dina inloggningsuppgifter för AdobeID.
2. Klicka på ikonen med nio rutnät längst upp och klicka sedan på Analytics (Analyser).
3. Håll pekaren över **[!UICONTROL Components]** överst och klicka sedan på **[!UICONTROL Virtual report suites]**.
4. Klicka på Lägg till.
5. Ange ett namn för den virtuella rapportsviten och kontrollera att den CDA-aktiverade rapportsviten är vald.
6. (Valfritt) Använd ett segment i den virtuella rapportsviten. Du kan till exempel använda ett segment som begränsar den virtuella rapportsviten till datum efter att CDA aktiverats och sammanfogningen påbörjats. Med det här segmentet kan användare bara se sammanslagna datumintervall i den virtuella rapportsviten.
7. Klicka på kryssrutan Aktivera rapporttidsbearbetning, som aktiverar flera fler alternativ, bland annat Enhetsövergripande analys.
8. Klicka i kryssrutan &quot;Häfta användarbesök mellan enheter&quot;.
9. Klicka på Fortsätt, avsluta konfigurationen av den virtuella rapportsviten och klicka sedan på Spara.

![CDA-kryssruta](assets/cda-checkbox.png)

## Tillägg och ändringar i virtuella rapportsviter för olika enheter

När Enhetsövergripande analys är aktiverat på en virtuell rapportserie bör du tänka på följande ändringar:

* En ny enhetsikon visas bredvid namnet på den virtuella rapportsviten. Den här ikonen är exklusiv för virtuella rapportsviter på olika enheter.
* En ny dimension med namnet [Identifierat läge](../dimensions/identified-state.md) är tillgänglig.
* Det finns nya mätvärden med etiketterna [Personer](../metrics/people.md), [Unika enheter](../metrics/unique-devices.md), [Identifierade personer](../metrics/identified-people.md), [Identifierade personer](../metrics/unidentified-people.md) och [Personer med Experience Cloud-ID](../metrics/people-with-exp-cloud-id.md).
* Måttet [Unika besökare](../metrics/unique-visitors.md) är inte tillgängligt eftersom det ersätts med Personer och Unika enheter.
* När du skapar segment ersätts segmentbehållaren &quot;Visitor&quot; med en &quot;Person&quot;-behållare.
