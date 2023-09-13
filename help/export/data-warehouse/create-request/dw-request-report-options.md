---
description: Steg som beskriver hur du skapar en begäran om Data Warehouse.
title: Konfigurera rapportalternativ för en Data Warehouse-förfrågan
feature: Data Warehouse
source-git-commit: 0abf0c76f38b481c0b72d113fe49e0da03ddd8cd
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 0%

---

# Konfigurera rapportalternativ för en Data Warehouse-förfrågan

>[!AVAILABILITY]
>
>Vissa av de Data Warehouse som beskrivs i den här artikeln (och andra artiklar i den här Datan Warehouse) är endast tillgängliga i den begränsade testfasen av releasen och är kanske inte tillgängliga i din miljö ännu.
>
>Information om vilka funktioner som ännu inte är tillgängliga för alla kunder, samt information om tidslinjen för releasen av dessa funktioner, finns i [versionsinformation](/help/release-notes/latest.md).
>
>Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Analytics-processen finns i [Adobe Analytics funktionsreleaser](/help/release-notes/releases.md).

Det finns olika konfigurationsalternativ tillgängliga när du skapar en Data Warehouse. Följande information beskriver hur du konfigurerar rapportalternativ för begäran.

Mer information om hur du börjar skapa en begäran och länkar till andra viktiga konfigurationsalternativ finns i [Skapa en begäran om Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Så här konfigurerar du rapportalternativ för en Data Warehouse:

1. Börja skapa en begäran i Adobe Analytics genom att välja **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Lägg till**].

   Mer information finns i [Skapa en begäran om Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. På sidan Ny Data Warehouse väljer du [!UICONTROL **Rapportalternativ**] -fliken.

   ![Målflik för rapport](assets/dw-report-options.png) <!-- update screenshot to include Sort by metrics -->

1. Ange följande fält:

   | Alternativ |  -funktion |
   |---------|----------|
   | Filnamn | Identifierar rapporten. |
   | Lägg till rapportdatumintervall till filnamn | Lägger till datumintervallet i rapportfilens namn. <p>Om du till exempel begär data från 1 maj till 7 maj 2024 inkluderar filnamnet datumintervallet 20240501 - 20240507.</p> |
   | CSV | Levererar rapporter i ett CSV-filformat för att visa data i ett kalkylblad. |
   | Tableu (TDE) | Levererar rapporter i ett TDE-filformat (Tableau Data Extract) som kan användas för att visualisera data och lager i ytterligare data i Tableau. |
   | Skicka rapport som komprimerad fil (ZIP) | Levererar rapporter i komprimerat filformat (ZIP). Vi rekommenderar att du aktiverar det här alternativet när du använder e-post som [rapportmål](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | Antal rader i tabellen | Antalet rader som kan inkluderas i rapporten. Använd 0 för att inkludera alla rader (det här är standardvalet). <!-- when would you want to limit the rows? To improve performance? Do we have recommendations? --> |
   | Kommentarer | Lägg till eventuella kommentarer som du vill ska ingå i rapporten. Kommentarerna visas i början av rapporten. |
   | Sortera efter mått | Tillhandahåller rankade uppdelningsrapporter i Data Warehouse, sorterade efter fallande måttvärde. Sortering efter mätvärden gör det enklare för er att tolka Data Warehouse-rapporter, och de här rapporterna blir enklare att jämföra med andra analytiska rapporter.<p>Mer information finns i [Sortera efter mått](/help/export/data-warehouse/sorting-by-metric.md).</p> |
   | Skicka manifestfil | Inkluderar metadata om de filer som ingår i rapporten.<!-- What kind of metadata is included in the manifest file? --> |
   | Skicka digital signaturfil | Låter rapportmottagarna verifiera att filen kommer från Adobe och att den inte har ändrats. |
   | Skicka en tom fil när det inte finns några data i rapporten | Skickar en rapport även när rapporten inte innehåller några data. |

   {style="table-layout:auto"}

1. Fortsätt konfigurera din Data Warehouse-förfrågan på [!UICONTROL **Schemaläggningsalternativ**] -fliken. Mer information finns i [Konfigurera schemaläggningsalternativ för en Data Warehouse-förfrågan](/help/export/data-warehouse/create-request/dw-request-scheduling.md).