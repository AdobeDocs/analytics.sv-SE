---
title: Implementera modal
description: Lär dig mer om den första kundupplevelsen för implementering av Adobe Analytics.
translation-type: tm+mt
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# Implementera modal

<!-- https://activation.adobedtm.com/index.php?redirected=1 -->

Det modala fönstret&quot;Välkommen till Adobe Analytics&quot; ger ett förenklat arbetsflöde för att skapa en rapportserie. Adobe rekommenderar att du använder det här arbetsflödet när fler rapportsviter behövs i din organisation.

![Modal screenshot](assets/implementation-modal.png)

## Förutsättningar

Ditt Adobe-id måste ha tillgång till både Adobe Analytics och Adobe Experience Platform Launch. Om du inte har åtkomst till Launch kan du placeras i en autentiseringsslinga där du ombeds att bekräfta dina inloggningsuppgifter på obestämd tid. Tala med en systemadministratör i organisationen för att få åtkomst till Launch.

## Åtkomst till spärren

Använd spärren för att skapa en rapportserie med följande steg.

1. Logga in på [experienceCloud.adobe.com](https://experiencecloud.adobe.com) med inloggningsuppgifterna för ditt Adobe ID.
2. Klicka på ikonen med nio stödraster överst och klicka sedan på [!UICONTROL Adobe Analytics].
3. Om du ännu inte har skapat en rapportserie visas spärren automatiskt. Om det finns en rapportsvit för det här inloggningsföretaget klickar du på hjälpikonen i det övre högra hörnet och sedan på [!UICONTROL Welcome to Adobe Analytics].

> [!NOTE] Alternativet visas bara om du loggar in via Adobe Experience Cloud. [!UICONTROL Welcome to Adobe Analytics] Om du loggar in via äldre domäner är spärrkoden inte tillgänglig.

## Skapa en rapportsvit

Klicka på [!UICONTROL Start Setup] knappen när du vill börja skapa ett arbetsflöde för rapportsviten.

![RS-guide](assets/analytics-implementation-rs-wizard.png)

### Egenskapstyp

Egenskapstypen hjälper Adobe att fastställa vissa serverdelsinställningar baserat på var ni tänker implementera Analytics.

* **Webbplats**: Om ni tänker implementera Adobe Analytics bara för en webbplats.
* **Inbyggd mobilapp**: Om ni tänker implementera Adobe Analytics bara för en mobilapp.
* **Båda**: Om den här rapportsviten innehåller data för både en webbplats och en mobilapp.

### Branscher

Ange din primära affärsmodell. Den här inställningen hjälper Adobe att förkonfigurera vissa variabelnamn och inställningar baserat på din primära affärsmodell.

### Datalager

Ett [datalager](data-layer.md) är ett JavaScript-objekt som organiserar alla variabler som används i implementeringen till en enda användbar plats. Mer information finns i [Datalager](data-layer.md) .

### Datalager

Ge rapportsviten ett eget namn. Ditt rapportsvit-ID (RSID) genereras automatiskt baserat på det egna namnet och inloggningsföretaget.

### Tidszon

Kontrollera att Adobe har identifierat rätt tidszon för rapportsviten.

### Beräknade sidvisningar per dag

Uppskatta hur mycket trafik din webbplats eller app tar per dag. Med den här informationen kan Adobe allokera rätt mängd bearbetningsresurser till din rapportsvit.

### Basvaluta

Avgör vilken valuta som rapportsviten lagrar monetära värden i.

> [!IMPORTANT] Se till att du anger rätt valuta, särskilt om du har rapporteringskrav för intäkter. Det är svårt att ändra basvalutan när datainsamlingen har startat.

## Implementeringsresurser

När rapportsviten har skapats har du ett av två alternativ för att fortsätta implementeringen:

* **Gå till Adobe Experience Platform Launch**: Länkar dig till [launch.adobe.com](https://launch.adobe.com) för att konfigurera implementeringen och hämta distributionskoden. Se [Implementera med Launch](../launch/overview.md). Adobe rekommenderar att du använder Launch i de flesta fall.
* **Ladda ned implementeringskod**: Tillhandahåller en direktlänk för att hämta JavaScript-filer för manuell JavaScript-implementering. Se [AppMeasurement for JavaScript](../js/overview.md).
