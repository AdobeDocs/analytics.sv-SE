---
title: Skapa en Analytics-egenskap i taggar
description: Skapa ett utrymme för att anpassa hur data samlas in med hjälp av taggar.
feature: Tags
exl-id: ffcd8e97-4d29-489e-bc2b-88805400dad5
role: Admin, Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 2%

---

# Skapa en Adobe Analytics-taggegenskap

Taggar i Adobe Experience Platform gör att du kan integrera Experience Cloud-lösningar på din webbplats (inklusive Analytics). På den här sidan beskrivs särskilt hur en tagghanterare kan få en grundläggande Adobe Analytics-implementering korrekt konfigurerad.

## Förutsättningar

[Skapa en rapportserie](/help/admin/tools/manage-rs/new-rs/t-create-a-report-suite.md): Skapa en silo för analysdata som ska samlas in.

## Skapa en taggegenskap och installera viktiga tillägg

Egenskaper är överliggande behållare som du använder för att hantera taggar. Med tillägg kan du installera produktspecifika taggar och konfigurera dem.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på **[!UICONTROL New Property]**.
1. Ge din egenskap ett namn, till exempel webbplatsens titel, och ange den domän som du tänker implementera Analytics på. Klicka på **[!UICONTROL Save]**.
1. Klicka på den nyligen skapade taggegenskapen för att ange dess inställningar.
1. Klicka på fliken **[!UICONTROL Extensions]** och sedan på **[!UICONTROL Catalog]**.
1. Leta reda på Experience Cloud ID-tjänsten och klicka sedan på **[!UICONTROL Install]**.
1. Alla inställningar, inklusive Experience Cloud organisations-ID, ska redan vara ifyllda. Klicka på **[!UICONTROL Save]**.
1. Gå tillbaka till tilläggskatalogen, leta upp Adobe Analytics och klicka på **[!UICONTROL Install]**.

Mer information finns i den fullständiga dokumentationen för [Adobe Analytics-tillägget](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=sv-SE).

## Skapa dataelement för Adobe Analytics

Dataelement är referenser till specifika delar av webbplatsen för att samla in variabelvärden.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den taggegenskap som du tänker implementera på webbplatsen.
1. Klicka på fliken **[!UICONTROL Data Elements]** och sedan på **[!UICONTROL Add Data Element]**.
1. Ge dataelementet följande inställningar:

   * Namn: Sidnamn
   * Tillägg: Kärna
   * Dataelementtyp: JavaScript-variabel
   * JavaScript-variabelnamn: `window.document.title`

     >[!NOTE]
     >
     >Det här värdet är ett exempel som hjälper dig att komma igång. Om din organisation definierar ett bättre värde för sidnamn, till exempel ett datalagervärde, kan du ange det här.
   * Rensa text
   * Lagringstid: Ingen
1. Klicka på **[!UICONTROL Save]**.

## Skapa regler för Adobe Analytics

Reglerna mappar dataelement till variabelvärden för Analytics och avgör när dessa värden skickas till Adobe-servrar.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den taggegenskap som du tänker implementera på webbplatsen.
1. Klicka på fliken **[!UICONTROL Rules]** och sedan på **[!UICONTROL Add Rule]**. Ge den namnet `Global Rule`.
1. Klicka på **[!UICONTROL Add]** bredvid händelser och ange följande inställningar:
   * Tillägg: Kärna
   * Händelsetyp: Bibliotek inläst (sidan ovanpå)
   * Namn: Kärna - Bibliotek inläst (sidan överst)
1. Klicka på **[!UICONTROL Keep Changes]**.
1. Klicka på **[!UICONTROL Actions]** under **[!UICONTROL Add]** och ange följande inställningar:
   * Tillägg: Adobe Analytics
   * Åtgärdstyp: Ange variabler
   * Sidnamn: klicka på behållarikonen och markera dataelementet `Page Name`.
   * Campaign: Frågeparameter med värdet `cid`
1. Klicka på **[!UICONTROL Keep Changes]**.
1. Klicka på plustecknet bredvid åtgärder för att lägga till en annan åtgärd och ange följande inställningar:
   * Tillägg: Adobe Analytics
   * Åtgärdstyp: Skicka signal
   * Namn: Adobe Analytics - Skicka Beacon
   * Spårning: s.t()
1. Klicka på **[!UICONTROL Keep Changes]**.
1. Kontrollera att du har angett händelsen och två åtgärder och klicka sedan på **[!UICONTROL Save]**.

## Nästa steg

[Distribuera din Analytics-implementering till din utvecklingsmiljö](deploy-dev.md): Få Analytics-koden att fungera i en testmiljö.
