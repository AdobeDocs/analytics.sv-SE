---
title: Skapa en Analytics-egenskap i Launch
description: Skapa ett utrymme för att anpassa hur data samlas in med Adobe Experience Platform Launch.
exl-id: ffcd8e97-4d29-489e-bc2b-88805400dad5
source-git-commit: c46feec3f08b78ca7882193ab86914db49617c1c
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 3%

---

# Skapa en Analytics-egenskap i Adobe Experience Platform Launch

Adobe Experience Platform Launch är det verktyg du kan använda för att integrera Experience Cloud-lösningar på din webbplats (inklusive Analytics). På den här sidan beskrivs särskilt hur en Launch-administratör kan konfigurera en grundläggande Adobe Analytics-implementering korrekt.

## Förutsättningar

[Skapa en rapportsvit](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md): Skapa en silo för att samla in analysdata

## Skapa en egenskap och installera viktiga tillägg

Egenskaper är överliggande behållare som du använder för att hantera taggar. Med tillägg kan du installera produktspecifika taggar och konfigurera dem.

1. Gå till [launch.adobe.com](https://launch.adobe.com) och logga in om du uppmanas till det.
1. Klicka på **[!UICONTROL New Property]**.
1. Ge din egenskap ett namn, till exempel webbplatsens titel, och ange den domän som du tänker implementera Analytics på. Klicka på **[!UICONTROL Save]**.
1. Klicka på den nyligen skapade egenskapen för att ange dess inställningar.
1. Klicka på fliken **[!UICONTROL Extensions]** och sedan på **[!UICONTROL Catalog]**.
1. Leta reda på identitetstjänsten och klicka sedan på **[!UICONTROL Install]**.
1. Alla inställningar, inklusive Experience Cloud organisations-ID, ska redan vara ifyllda. Klicka på **[!UICONTROL Save]**.
1. Gå tillbaka till tilläggskatalogen, leta upp Adobe Analytics och klicka på **[!UICONTROL Install]**.

## Skapa dataelement för Adobe Analytics

Dataelement är referenser till specifika delar av webbplatsen för att samla in variabelvärden.

1. Gå till [launch.adobe.com](https://launch.adobe.com) och logga in om du uppmanas till det.
1. Klicka på den Launch-egenskap som du vill implementera på webbplatsen.
1. Klicka på fliken **[!UICONTROL Data Elements]** och sedan på **[!UICONTROL Create New Data Element]**.
1. Ge dataelementet följande inställningar:

   * Namn: Sidnamn
   * Tillägg: Core
   * Dataelementtyp: JavaScript-variabel
   * Sökväg till variabel: `window.document.title`

      >[!NOTE]
      >
      >Detta är ett exempelvärde som hjälper dig att komma igång. Om din organisation definierar ett bättre värde för sidnamn, till exempel ett datalagervärde, kan du ange det här.
   * Rensa text
   * Varaktighet: Sidvy
1. Klicka på **[!UICONTROL Save]**.

## Skapa regler för Adobe Analytics

Regler mappar dataelement till Analytics-variabelvärden och avgör när dessa värden skickas till Adobe-servrar.

1. Gå till [launch.adobe.com](https://launch.adobe.com) och logga in om du uppmanas till det.
1. Klicka på den Launch-egenskap som du vill implementera på webbplatsen.
1. Klicka på **[!UICONTROL Create New Rule]** och ge den namnet `Global Rule`.
1. Klicka på **[!UICONTROL Add]** bredvid händelser och ange följande inställningar:
   * Tillägg: Core
   * Händelsetyp: Bibliotek inläst (sidan ovanpå)
   * Namn: Kärna - Bibliotek inläst (sidan ovanpå)
   * Ordning: 50
1. Klicka på **[!UICONTROL Keep Changes]**.
1. Klicka på **[!UICONTROL Add]** under **[!UICONTROL Actions]** och ange följande inställningar:
   * Tillägg: Adobe Analytics
   * Åtgärdstyp: Ange variabler
   * Sidnamn: klicka på behållarikonen och välj dataelementet `Page Name`.
   * Campaign: Frågeparameter med värdet `cid`
1. Klicka på **[!UICONTROL Keep Changes]**.
1. Klicka på plustecknet bredvid åtgärder för att lägga till en annan åtgärd och ange följande inställningar:
   * Tillägg: Adobe Analytics
   * Åtgärdstyp: Skicka Beacon
   * Namn: Adobe Analytics - skicka Beacon
   * Spårning: s.t()
1. Klicka på **[!UICONTROL Keep Changes]**.
1. Kontrollera att du har angett händelsen och två åtgärder och klicka sedan på **[!UICONTROL Save]**.

## Dokumentation och ytterligare resurser

* [Adobe Analytics-tilläggsdokumentation](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html?lang=en#extensions-ref): Fullständig dokumentation som är specifik för Adobe Analytics-tillägget i Adobe Experience Platform Launch.
* [Komma igång med Launch](https://experienceleague.adobe.com/docs/launch/using/get-started/quick-start.html?lang=en#get-started): Fullständig dokumentation för Launch, inklusive en mer ingående guide för att komma igång
* [Adobe Experience Platform Launch-kanal](https://experienceleague.adobe.com/?tag=Launch#recommended/solutions/experience-platform): Lär dig använda Launch via videor

## Nästa steg

[Distribuera er Analytics-implementering i er utvecklingsmiljö](deploy-dev.md): Få Analytics-koden att fungera i en testmiljö.
