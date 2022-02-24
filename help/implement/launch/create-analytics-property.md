---
title: Skapa en Analytics-egenskap i taggar
description: Skapa ett utrymme för att anpassa hur data samlas in med hjälp av taggar.
feature: Launch Implementation
exl-id: ffcd8e97-4d29-489e-bc2b-88805400dad5
source-git-commit: 0763f2624d46eb282b7b4c94f7d103d8e9ad8095
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 1%

---

# Skapa en Adobe Analytics-taggegenskap

Taggar i Adobe Experience Platform gör att du kan integrera Experience Cloud-lösningar på din webbplats (inklusive Analytics). På den här sidan beskrivs särskilt hur en tagghanterare kan få en grundläggande Adobe Analytics-implementering korrekt konfigurerad.

>[!NOTE]
>Adobe Experience Platform Launch har omklassificerats som en serie datainsamlingstekniker i Experience Platform. Som ett resultat av detta har flera terminologiska förändringar införts i produktdokumentationen. Se följande [dokument](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) för en konsoliderad hänvisning till terminologiska förändringar.

## Förutsättningar

[Skapa en rapportsvit](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md): Skapa en silo för att samla in analysdata.

## Skapa en taggegenskap och installera viktiga tillägg

Egenskaper är överliggande behållare som du använder för att hantera taggar. Med tillägg kan du installera produktspecifika taggar och konfigurera dem.

1. Logga in på [Användargränssnitt för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på **[!UICONTROL New Property]**.
1. Ge din egenskap ett namn, till exempel webbplatsens titel, och ange den domän som du tänker implementera Analytics på. Klicka på **[!UICONTROL Save]**.
1. Klicka på den nyligen skapade taggegenskapen för att ange dess inställningar.
1. Klicka på **[!UICONTROL Extensions]** tabbtangenten och sedan klicka **[!UICONTROL Catalog]**.
1. Sök efter tjänsten Experience Cloud ID och klicka sedan på **[!UICONTROL Install]**.
1. Alla inställningar, inklusive Experience Cloud organisations-ID, ska redan vara ifyllda. Klicka på **[!UICONTROL Save]**.
1. Gå tillbaka till tilläggskatalogen, leta upp Adobe Analytics och klicka på **[!UICONTROL Install]**.

## Skapa dataelement för Adobe Analytics

Dataelement är referenser till specifika delar av webbplatsen för att samla in variabelvärden.

1. Logga in på [Användargränssnitt för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den taggegenskap som du tänker implementera på webbplatsen.
1. Klicka på **[!UICONTROL Data Elements]** tabbtangenten och sedan klicka **[!UICONTROL Create New Data Element]**.
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

1. Logga in på [Användargränssnitt för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den taggegenskap som du tänker implementera på webbplatsen.
1. Klicka **[!UICONTROL Create New Rule]** och namnge `Global Rule`.
1. Klicka **[!UICONTROL Add]** bredvid händelser och ange följande inställningar:
   * Tillägg: Core
   * Händelsetyp: Bibliotek inläst (sidan ovanpå)
   * Namn: Kärna - Bibliotek inläst (sidan ovanpå)
   * Ordning: 50
1. Klicka på **[!UICONTROL Keep Changes]**.
1. Under **[!UICONTROL Actions]**, klicka **[!UICONTROL Add]** och ange följande inställningar:
   * Tillägg: Adobe Analytics
   * Åtgärdstyp: Ange variabler
   * Sidnamn: klicka på behållarikonen och välj `Page Name` dataelement.
   * Campaign: Frågeparameter med värdet `cid`
1. Klicka på **[!UICONTROL Keep Changes]**.
1. Klicka på plustecknet bredvid åtgärder för att lägga till en annan åtgärd och ange följande inställningar:
   * Tillägg: Adobe Analytics
   * Åtgärdstyp: Skicka Beacon
   * Namn: Adobe Analytics - skicka Beacon
   * Spårning: s.t()
1. Klicka på **[!UICONTROL Keep Changes]**.
1. Kontrollera att du har en händelse och två åtgärder angivna och klicka sedan på **[!UICONTROL Save]**.

## Dokumentation och ytterligare resurser

* [Dokumentation för Adobe Analytics-tillägg](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=en): Fullständig dokumentation som är specifik för tillägget Adobe Analytics i taggar.
* [Komma igång med taggar](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=en): Fullständig dokumentation för taggar, inklusive en mer ingående guide för hur du kommer igång
* [Adobe Experience Platform Launch](https://experienceleague.adobe.com/?tag=Launch#recommended/solutions/experience-platform): Lär dig använda taggar via videor

## Nästa steg

[Distribuera er Analytics-implementering i er utvecklingsmiljö](deploy-dev.md): Få Analytics-koden att fungera i en testmiljö.
