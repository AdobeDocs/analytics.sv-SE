---
title: Identifiering av besökare med hjälp av taggtillägget Adobe Analytics
description: Identifiera besökare korrekt när du implementerar Adobe Analytics-taggtillägget.
source-git-commit: 98e9dc4932bd23d3e0b632705945f56c243750c5
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 0%

---

# Identifiering av besökare med hjälp av taggtillägget Adobe Analytics

Med taggtillägget Adobe Analytics kan du implementera AppMeasurement med hjälp av ett tagghanteringsgränssnitt. Eftersom det här taggtillägget i stort sett är AppMeasurement under huven, finns det liknande metoder för att identifiera besökare och det krävs ett separat taggtillägg för Visitor ID-tjänsten.

## Identifiera besökare med hjälp av besökar-ID-tjänsten (rekommenderas)

Om du vill använda besökar-ID-tjänsten med hjälp av taggtillägget för Adobe Analytics ska du inkludera taggtillägget för Experience Cloud ID-tjänsten i taggegenskapen.

1. Logga in på [experience.adobe.com](https://experience.adobe.com) med dina Adobe ID-inloggningsuppgifter.
1. Navigera till **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]**.
1. Leta reda på den önskade taggegenskapen.
1. Navigera till **[!UICONTROL Extensions]** och markera sedan fliken **[!UICONTROL Catalog]**.
1. Leta reda på tillägget **[!UICONTROL Experience Cloud ID Service]** och välj sedan **[!UICONTROL Install]**.

Taggtillägget hämtar automatiskt ditt IMS-org-ID, så ingen ytterligare konfiguration behövs.

## Identifiera besökare med hjälp av cookien `s_vi` (rekommenderas inte)

>[!IMPORTANT]
>
>Adobe rekommenderar att du inte använder den här metoden för att identifiera besökare.

Om din organisation inte använder tillägget Service Tag-nummer för Visitor ID använder Adobe Analytics-taggtillägget sin egen form av besökaridentifiering. När en besökare kommer till din webbplats för första gången söker tillägget efter en [`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics)-cookie. Den här cookie-filen anges till den domän som matchar **[!UICONTROL SSL Tracking Server]** (för HTTPS) eller **[!UICONTROL Tracking Server]** (för HTTP) när [taggtillägget &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/analytics/overview) konfigureras.

* Om du deltar i det [hanterade certifikatprogrammet](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/adobe-managed-cert) är din spårningsserver vanligtvis en förstapartsdomän, vilket gör `s_vi` cookies från första part.
* Om du inte deltar i det hanterade certifikatprogrammet är spårningsservern vanligtvis en underdomän till `adobedc.net`, `omtrdc.net` eller `2o7.net`, vilket gör `s_vi`-cookien till en cookie från tredje part. På grund av moderna webbläsarsekretessstandarder avvisas cookies från tredje part av de flesta webbläsare. När den har avvisats försöker AppMeasurement ange en cookie för återfall (`fid`) för första part i stället.

Om du har angett [!UICONTROL SSL Tracking Server] korrekt krävs inga ytterligare åtgärder för besöksidentifiering.

## Identifiera besökare med `visitorID` (rekommenderas inte)

>[!IMPORTANT]
>
>Adobe rekommenderar att du inte använder den här metoden för att identifiera besökare.

Om du använder variabeln **[!UICONTROL Visitor ID]** kan din organisation utföra oberoende kontroll för att identifiera besökare. Om du anger [!UICONTROL Visitor ID] med ett dataelement bör du tänka på följande begränsningar:

* Varje träff måste innehålla samma [!UICONTROL Visitor ID]-värde för att räknas som en enskild besökare.
   * Alla träffar som utelämnar dataelementet [!UICONTROL Visitor ID] försöker automatiskt att använda en annan metod för identifiering av besökare, och behandlar dem som separata besökare.
   * Alla träffar som innehåller ett annat [!UICONTROL Visitor ID]-värde än en tidigare träff behandlas som separata besökare.
   * Adobe erbjuder inget sätt att sy ihop träffar med olika besökar-ID:n i Adobe Analytics.
* Delade målgrupper, Analytics for Target och Customer-attribut stöds inte för besökare som identifieras med [!UICONTROL Visitor ID].

Se [`visitorID`](/help/implement/vars/config-vars/visitorid.md) för implementeringsinstruktioner med den här variabeln.
