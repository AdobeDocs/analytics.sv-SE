---
description: Steg som beskriver hur du skapar en begäran om Data Warehouse.
title: Konfigurera rapportalternativ för en Data Warehouse-förfrågan
feature: Data Warehouse
exl-id: b273bddb-431c-44d9-82a5-cb088829b3a3
source-git-commit: 4e4b5e1c362778223be01f78b173a698c53f9b32
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 0%

---

# Konfigurera rapportalternativ för en Data Warehouse-förfrågan

Det finns olika konfigurationsalternativ tillgängliga när du skapar en Data Warehouse. Följande information beskriver hur du konfigurerar rapportalternativ för begäran.

Mer information om hur du börjar skapa en begäran och länkar till andra viktiga konfigurationsalternativ finns i [Skapa en begäran om Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Så här konfigurerar du rapportalternativ för en Data Warehouse:

1. Om du inte redan har gjort det börjar du skapa en förfrågan i Adobe Analytics genom att välja **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Lägg till**].

   Mer information finns i [Skapa en begäran om Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. På sidan Ny Data Warehouse väljer du [!UICONTROL **Rapportalternativ**] -fliken.

   ![Målflik för rapport](assets/dw-report-options.png) <!-- update screenshot to include Sort by metrics -->

1. Ange följande fält:

   | Alternativ | Funktion |
   |---------|----------|
   | [!UICONTROL **Filnamn**] | Identifierar rapporten. <p>Om något av följande specialtecken används i filnamnet går det inte att spara begäran: <code>! &quot; # $ &amp; &#39; ( ) * + , / : ; > = &lt; ? @ [ ] \ ^ ` { } \| ~</code> </p><p>Tecknet % kan bara användas om det följs av&quot;R&quot;,&quot;rsid&quot; eller&quot;id&quot; enligt följande: <code>%R</code>, <code>%rsid</code>och <code>%id</code>.</p> |
   | [!UICONTROL **Lägg till rapportdatumintervall till filnamn**] | Lägger till datumintervallet i rapportfilens namn. <p>Om du till exempel begär data från 1 maj till 7 maj 2024 inkluderar filnamnet datumintervallet 20240501 - 20240507.</p> |
   | [!UICONTROL **CSV**] | Levererar rapporter i ett CSV-filformat för att visa data i ett kalkylblad. |
   | [!UICONTROL **Tableu (TDE)**] | Levererar rapporter i ett TDE-filformat (Tableau Data Extract) som kan användas för att visualisera data och lager i ytterligare data i Tableau. |
   | [!UICONTROL **Skicka rapport som komprimerad fil (ZIP)**] | Levererar rapporter i komprimerat filformat (ZIP). Vi rekommenderar att du aktiverar det här alternativet när du använder e-post som [rapportmål](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | [!UICONTROL **Returnera alla rader**] | När det här alternativet är aktiverat inkluderas alla rader i rapporten. Inaktivera det här alternativet om du vill ange antalet rader som ska inkluderas. |
   | [!UICONTROL **Början av rapportkommentarer**] | Lägg till eventuella kommentarer som du vill ska ingå i rapporten. Kommentarerna visas i början av rapporten. |
   | [!UICONTROL **Sortera efter mått**] | Tillhandahåller rankade uppdelningsrapporter i Data Warehouse, sorterade efter fallande måttvärde. Sortering efter mätvärden gör det enklare för er att tolka Data Warehouse-rapporter, och de här rapporterna blir enklare att jämföra med andra analytiska rapporter.<p>Mer information finns i [Sortera efter mått](/help/export/data-warehouse/sorting-by-metric.md).</p> |
   | [!UICONTROL **Skicka en manifestfil**] | Inkluderar metadata om de filer som ingår i rapporten.<!-- What kind of metadata is included in the manifest file? --> |
   | [!UICONTROL **Skicka en digital signaturfil**] | Låter rapportmottagarna verifiera att filen kommer från Adobe och att den inte har ändrats. |
   | [!UICONTROL **Skicka en tom fil när det inte finns några data i rapporten**] | Skickar en rapport även när rapporten inte innehåller några data. |

   {style="table-layout:auto"}

1. Fortsätt konfigurera din Data Warehouse-förfrågan på [!UICONTROL **Schemaläggningsalternativ**] -fliken. Mer information finns i [Konfigurera schemaläggningsalternativ för en Data Warehouse-förfrågan](/help/export/data-warehouse/create-request/dw-request-scheduling.md).
