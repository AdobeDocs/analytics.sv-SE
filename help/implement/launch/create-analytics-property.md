---
title: Skapa en Analytics-egenskap i Launch
description: Skapa ett utrymme för att anpassa hur data samlas in med Adobe Experience Platform Launch.
translation-type: tm+mt
source-git-commit: 763c1b7405c1a1b3d6dbd685ce796911dd4ce78b
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 1%

---


# Skapa en Analytics-egenskap i Adobe Experience Platform Launch

Adobe Experience Platform Launch är det verktyg du kan använda för att integrera Experience Cloud-lösningar på din webbplats (inklusive Analytics). På den här sidan beskrivs särskilt hur en Launch-administratör kan konfigurera en grundläggande Adobe Analytics-implementering korrekt.

## Förutsättningar

[Skapa en rapportsvit](/help/admin/admin-console/create-report-suite.md): Skapa en silo för att samla in analysdata

## Skapa en egenskap och installera viktiga tillägg

Egenskaper är överliggande behållare som du använder för att hantera taggar. Med tillägg kan du installera produktspecifika taggar och konfigurera dem.

1. Gå till [launch.adobe.com](https://launch.adobe.com) och logga in om du uppmanas till det.
1. Klicka på Ny egenskap.
1. Ge din egenskap ett namn, till exempel webbplatsens titel, och ange den domän som du tänker implementera Analytics på. Klicka på Spara.
1. Klicka på den nyligen skapade egenskapen för att ange dess inställningar.
1. Klicka på fliken Tillägg och sedan på Katalog.
1. Leta reda på identitetstjänsten och klicka sedan på Installera.
1. Alla inställningar, inklusive Experience Cloud organisations-ID, ska redan vara ifyllda. Klicka på Spara.
1. Gå tillbaka till tilläggskatalogen, leta upp Adobe Analytics och klicka på Installera.

## Skapa dataelement för Adobe Analytics

Dataelement är referenser till specifika delar av webbplatsen för att samla in variabelvärden.

1. Gå till [launch.adobe.com](https://launch.adobe.com) och logga in om du uppmanas till det.
1. Klicka på den Launch-egenskap som du vill implementera på webbplatsen.
1. Klicka på fliken Dataelement och sedan på Skapa nytt dataelement.
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
1. Klicka på Spara.

## Skapa regler för Adobe Analytics

Regler mappar dataelement till Analytics-variabelvärden och avgör när dessa värden skickas till Adobe-servrar.

1. Gå till [launch.adobe.com](https://launch.adobe.com) och logga in om du uppmanas till det.
1. Klicka på den Launch-egenskap som du vill implementera på webbplatsen.
1. Klicka på Skapa ny regel och ge den ett namn `Global Rule`.
1. Klicka på Lägg till bredvid händelser och ange följande inställningar:
   * Tillägg: Core
   * Händelsetyp: Bibliotek inläst (sidan ovanpå)
   * Namn: Kärna - Bibliotek inläst (sidan ovanpå)
   * Ordning: 50
1. Klicka på Behåll ändringar.
1. Klicka på Lägg till under Åtgärder och ange följande inställningar:
   * Tillägg: Adobe Analytics
   * Åtgärdstyp: Ange variabler
   * Sidnamn: klicka på behållarikonen och markera dataelementet `Page Name` .
   * Campaign: Frågeparameter med värdet `cid`
1. Klicka på Behåll ändringar.
1. Klicka på plustecknet bredvid åtgärder för att lägga till en annan åtgärd och ange följande inställningar:
   * Tillägg: Adobe Analytics
   * Åtgärdstyp: Skicka Beacon
   * Namn: Adobe Analytics - skicka Beacon
   * Spårning: s.t()
1. Klicka på Behåll ändringar.
1. Kontrollera att händelsen och två åtgärder är angivna och klicka sedan på Spara.

## Dokumentation och ytterligare resurser

* [Adobe Analytics-tilläggsdokumentation](https://docs.adobelaunch.com/extension-reference/web/adobe-analytics-extension): Fullständig dokumentation som är specifik för Adobe Analytics-tillägget i Adobe Experience Platform Launch.
* [Komma igång med Launch](https://docs.adobelaunch.com/getting-started): Fullständig dokumentation för Launch, inklusive en mer ingående guide för att komma igång
* [Adobe Experience Platform Launch YouTube-kanal](https://www.youtube.com/channel/UCa84ntcvYhPArOBsZIRE2Jw/videos?view=0&amp;shelf_id=0&amp;sort=dd): Lär dig använda Launch via videor

## Nästa steg

[Distribuera er Analytics-implementering i er utvecklingsmiljö](deploy-dev.md): Få Analytics-koden att fungera i en testmiljö.
