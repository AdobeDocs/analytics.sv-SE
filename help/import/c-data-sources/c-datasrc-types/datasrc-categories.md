---
description: Datakällkategorier identifierar olika typer av datakällor som erbjuder liknande funktionalitet.
subtopic: Data sources
title: Översikt över datatyper och kategorier
topic-fix: Developer and implementation
uuid: b5004cdc-b68a-4a82-a159-a7cd7b8bfe21
exl-id: d459fd06-a0fe-49e6-8624-b42f0c60ee6e
source-git-commit: 0b31585f5a928d68083764b80f3a08927b407387
workflow-type: tm+mt
source-wordcount: '827'
ht-degree: 6%

---

# Översikt över datatyper och kategorier

Datakällkategorier identifierar olika typer av datakällor som erbjuder liknande funktionalitet.

Med kategorier kan du gruppera datakällor utifrån användarens perspektiv. När du skapar en datakälla via [!DNL Data Sources] Användargränssnittet väljer först en datakällkategori och sedan en viss typ av datakälla. Varje kategori innehåller typer av datakällor som stöder liknande typer av data. [!DNL Data Sources] innehåller följande kategorier för datakällor:

## Webbplatsanvändning {#web-usage}

| Datakälla | Bearbetningstyp | Beskrivning |
| --- | --- | --- |
| [!UICONTROL Web Server Log Files] | [Webblogg](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md) | De flesta webbservrar genererar loggfiler som registrerar varje sida som hanteras. Med den här datakällan kan du bearbeta loggfilerna från de flesta webbserverdata och lägga till dessa data i dina rapporter. |
| [!UICONTROL Advertising Cloud Bulk Upload] | [Konvertering](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Ger manuella och Excel-automatiserade massöverföringar i [!DNL Advertising Cloud]. |
| [!UICONTROL Site-level Traffic Data Source] | [Trafik](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) | Importerar trafikdata för hela webbplatsen. Exempel, [!UICONTROL Page Views]. |
| [!UICONTROL Breakdown Traffic Data Source] | [Trafik](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) | Importerar trafikdata som har delats upp av en annan webbplatsvariabel. Till exempel: [!UICONTROL Page Views] uppdelat efter [!UICONTROL Product]. |

## Annonskampanjer {#ad-campaigns}

| Datakälla | Bearbetningstyp | Beskrivning |
| --- | --- | --- |
| [!UICONTROL Generic Ad Server] | [Konvertering](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Gör att ni kan integrera visningar och annan toppnivåstatistik om era annonsserveraktiviteter i marknadsföringsrapporter. Detta är den allmänna datakällan för annonsservern och bör användas om din specifika annonsserver inte stöds. |
| [!UICONTROL Generic Email Campaign Server] | [Konvertering](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Gör att ni kan integrera mätvärden från era e-postkampanjservrar i marknadsföringsrapporter.  Vanliga inbyggda mätvärden är antalet skickade meddelanden, skickade meddelanden och lästa meddelanden. Detta är den allmänna datakällan för e-postkampanjen och bör användas om din specifika e-postkampanjserver inte stöds. |
| [!UICONTROL Generic Pay-Per-Click Service] | [Konvertering](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Gör att du kan importera data om hur mycket du betalar per klick, inklusive visningar, klickningar och kostnader.  Detta är den generiska datakällan för betalning per klick och bör användas om din specifika tjänst för betalning per klick inte stöds. |

## CRM (Customer Relationship Management) {#crm}

| Datakälla | Bearbetningstyp | Beskrivning |
| --- | --- | --- |
| [!UICONTROL Generic Call Center] | [Konvertering](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Gör att ni kan integrera information om ert callcenter i marknadsföringsrapporter. De vanligaste mätvärdena är antalet samtal, telefontid, agenten och den totala försäljningen.  Den här datakällan är den generiska datakällan för call center och bör användas om din specifika call center-programvara inte stöds. |
| [!UICONTROL Generic Customer Support Application] | [Konvertering](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Här kan ni integrera information från era kundsupportprogram i marknadsföringsrapporter. Det innehåller mätvärden som antalet nya incidenter, antalet åtgärdade incidenter och hur lång tid som har ägnats åt att lösa incidenter.  Detta är den allmänna datakällan för kundsupport och bör användas om ditt specifika kundtjänstprogram inte stöds. |

## Nöjda kunder {#csat}

| Datakälla | Bearbetningstyp | Beskrivning |
| --- | --- | --- |
| [!UICONTROL Generic Survey Data] | [Konvertering](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Gör att ni kan integrera undersökningsresultat från ett tredjepartsverktyg i marknadsföringsrapporter och visa hur nöjda kunderna är genom deras interaktioner med er webbplats.  Detta är den allmänna datakällan för undersökningen och bör användas om din specifika datatjänst för undersökningen inte stöds. |

## Webbplatsprestanda {#performance}

| Datakälla | Bearbetningstyp | Beskrivning |
| --- | --- | --- |
| [!UICONTROL Generic Site Download Speed] | [Konvertering](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Gör att du kan integrera data från ett program eller en tjänst som spårar hastigheten på dina hämtningar med dina data. Detta är den allmänna datakällan för nedladdningshastighet och bör användas om din specifika programvara eller tjänst för nedladdningshastighet inte stöds. |

## Allmän {#generic}

| Datakälla | Bearbetningstyp | Beskrivning |
| --- | --- | --- |
| [!UICONTROL Generic Data Source (Summary Data Only)] | [Konvertering](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Använd den här datakällan när det inte finns någon bättre matchning mot den typ av data som du vill importera till marketing reports and analytics. |
| [!UICONTROL Generic Data Source (Full Processing)] | Fullständig bearbetning | Adobe ersatte datakällor för fullständig bearbetning den 31 januari 2022. [Läs mer](/help/import/c-data-sources/c-datasrc-types/datasrc-fullproc-eol.md). Adobe rekommenderar att du använder [API för massdatainmatning (BDIA](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) i stället. |
| [!UICONTROL Generic Data Source (Transaction ID)] | <ul><li>Transaktions-ID</li><li>Besökar-ID</li></ul> | Gör att du kan koppla en offlinehändelse till en onlinehändelse. The [!UICONTROL Transaction ID] fungerar som en nyckel mellan offline- och onlinehändelserna. |

## Onlineköp {#purchases}

| Datakälla | Bearbetningstyp | Beskrivning |
| --- | --- | --- |
| [!UICONTROL Product Returns] | [Konvertering](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Gör att du kan importera produktreturdata som ska kopplas till ett köp-ID så att du kan identifiera sökmotorer, nyckelord, kampanjer och andra attribut som är mer benägna att generera returer. |
| [!UICONTROL Product Cost] | [Konvertering](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Här kan du ange den faktiska kostnaden för produkter som köpts och levererats från din webbplats genom att associera kostnad eller vinst med enskilda produkter så att du kan rapportera korrekt om de mest lönsamma kampanjerna, nyckelorden och interna kampanjerna för din webbplats. |
| [!UICONTROL Order Status] | [Konvertering](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Här kan du använda mätvärden för att identifiera status för varje beställning som gjorts, inklusive beställningar som annullerats, skickats, slutförts eller bedömts vara bedrägliga. Orderstatusrapportering kan identifiera vilka förvärvsmetoder som genererar den högsta orderslutförandefrekvensen. |

## Leads och citattecken {#leads}

| Datakälla | Bearbetningstyp | Beskrivning |
| --- | --- | --- |
| [!UICONTROL Lead Generation] | [Konvertering](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Här kan du överföra information om resultatet av leads för varje lead som genereras på din webbplats, inklusive faktiska intäkter som genereras.  När intäkterna har tilldelats till lead-ID:n kan ni identifiera era mest lönsamma kampanjer och kampanjer. |
| [!UICONTROL Online Quote] | [Konvertering](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Här kan du överföra information om resultatet av leads för varje lead som genereras på din webbplats, inklusive faktiska intäkter som genereras.  När intäkterna har tilldelats till lead-ID:n kan ni identifiera era mest lönsamma kampanjer och kampanjer. |
| [!UICONTROL Call Center Data] | [Konvertering](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Gör att du kan överföra kundtjänsttransaktioner så att du kan identifiera taktiker (kampanjer, kampanjer och så vidare). som får kunderna att ringa. |
