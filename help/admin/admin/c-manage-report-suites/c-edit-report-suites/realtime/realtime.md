---
description: Visar webbsidans trafik och rangordnar sidvyerna i realtid. Tillhandahåller användbara data som underlag för era affärsbeslut.
title: Realtidsrapporter
feature: Real-time
exl-id: 267246ba-617f-4284-aaad-d0ace0f6a8cf
source-git-commit: def7d071de1765acf524a638a8f8d13ae69e1a1f
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 0%

---

# Realtidsrapporter

Visar webbsidans trafik och rangordnar sidvyerna i realtid. Tillhandahåller användbara data som underlag för era affärsbeslut.



>[!NOTE]
>
>Realtidsrapporten kräver ingen ytterligare implementering eller taggning. Det utnyttjar er befintliga implementering av Adobe Analytics. Information om hur du konfigurerar realtidsrapporter finns i [Konfiguration av realtidsrapporter](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/t-realtime-admin.md).

Här är en videoöversikt:

>[!VIDEO](https://video.tv.adobe.com/v/25454/?quality=12)

**[!UICONTROL Site Metrics]** > **[!UICONTROL Real-Time]**

Realtidsfrågor besvarar följande frågor: Vad är trender på min webbplats och varför? Som marknadsförare kan ni snabbt reagera på och aktivt hantera resultatet av ert marknadsföringsinnehåll och era kampanjer. Realtidsdata som rapporteras är mindre än två minuter latent och automatiska uppdateringar en minut i taget.

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/report-realtime.png)

Kontrollpanelen innehåller Adobe Analytics högfrekventa mätvärden och webbplatsanalyser för att visuellt rapportera trafik- och sidvytrender för dynamiska nyheter och butikswebbplatser. Realtid förstår trender i era data från minut till minut, inom sekunder från insamlingen. Den samlar in och strömmar data till ett automatiskt uppdaterat användargränssnitt med hjälp av korrelation i realtid och spårning av innehåll och viss konvertering.

Två av de vanligaste användningsscenarierna är utgivare som vill marknadsföra/nedgradera artiklar när användaraktiviteten ändras, och marknadsförare som vill spåra lanseringen av en ny produktlinje.

Som administratör kan du

* Skapa upp till tre realtidsrapporter per rapportserie med befintliga dimensioner eller klassificeringar och mätvärden. Använd de sekundära dimensionerna för att korrelera med (eller dela upp) den primära.
* Lägg till tre dimensioner (eller klassificeringar) per rapport (en primär och två sekundära), utöver ett platsomfattande mått.
* Använd en anpassad händelse, varukorshändelse eller instans.
* Visa upp till två timmars historikdata i realtid och ändra den här inställningen:

   * Senaste 15 minuterna: 1 minut granularitet
   * Senaste 30 minuterna: 1 minut granularitet
   * Senaste timmen: 2 minuters granularitet
   * Senaste 2 timmarna: 4-minuters granularitet

* Jämför till exempel förra veckans värden med förra årets värden (liksom med dagens totala värde).

Tänk på att eVars (konverteringsmått) inte stöds eftersom det inte finns något koncept för beständighet. Du kan välja konverteringsmått, men de fungerar bara om de är inställda på samma sida som dimensionerna. Mer information finns i varningsmeddelandet i [Konfigurera realtidsrapporter](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/t-realtime-admin.md).

Det är endast administratörer eller användare i behörighetsgrupperna All Report Access och Advanced Reporting som kan konfigurera och visa realtidsrapporter. Real-Time respekterar dock behörigheter. Om du till exempel inte har rätt att se intäkter kan du inte visa en realtidsrapport som innehåller intäktsdata.

## Datasvarstid som ett resultat av A4T-konfiguration {#section_806CE36354FC4C539A0DED9266A5C704}

När A4T-integreringen har aktiverats i Adobe Target får du ytterligare 5-10 minuters fördröjning i Adobe Analytics. Den här fördröjningsökningen gör att data från Analytics och Target kan lagras på samma träff, vilket gör att ni kan bryta ned tester per sida och webbplatsavsnitt.

Ökningen återspeglas i alla Adobe Analytics tjänster och verktyg, inklusive liveströmmen och realtidsrapporter, och gäller i följande scenarier:

* För liveströmmar, realtidsrapporter och API-begäranden samt aktuella data för trafikvariabler fördröjs bara träffar med ett extra data-ID.
* För aktuella data om konverteringsmått, slutförda data och dataflöden fördröjs alla träffar ytterligare 5-7 minuter.

Tänk på att latensökningen börjar efter att du har implementerat identitetstjänsten, även om du inte har implementerat den här integreringen fullständigt.
