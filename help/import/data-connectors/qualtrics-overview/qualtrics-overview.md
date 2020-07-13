---
description: Integrationen kombinerar Qualtrics Research Suites funktioner för kundforskning med de omfattande data ni samlar in i Adobe Analytics för att skapa kraftfulla analyser och optimeringsmöjligheter för er organisation.
subtopic: Qualtrics
title: Qualtrics Data Connector för Adobe Analytics
topic: Data connectors
uuid: f1fa90b6-1b80-4da4-a39b-efb8bac1692a
translation-type: tm+mt
source-git-commit: 0fed9fd179feadae26a364a2ca79ac396251e8f6
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 4%

---


# Qualtrics Data Connector för Adobe Analytics{#qualtrics-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>Vi upphör med Adobe Data Connector-tekniken i mitten av slutet av 2021. [Läs mer …](/help/import/data-connectors/data-connectors-eol.md)

Integrationen kombinerar Qualtrics Research Suites funktioner för kundforskning med de omfattande data ni samlar in i Adobe Analytics för att skapa kraftfulla analyser och optimeringsmöjligheter för er organisation.

Denna tvåvägsintegrering kopplar först svarsdata från Qualtrics-undersökningen till besökarens klickströmsdata. Sedan injiceras relevanta beteendebeteenden och attribut från Adobe Analytics tillbaka i Qualtrics enkätsvar.

## Viktiga fördelar och funktioner{#key-benefits-and-features}

* Bygg användarsegment baserat på de svar användarna ger på specifika enkätfrågor.
* Trafik- och konverteringsrapportering baserad på enkät-, fråge- och svarsnivådetaljer.
* Använder endast en ListVar-, 1 eVar- och 1-händelse för att integrera ett obegränsat antal Qualtrics-undersökningar.
* Förbättra Qualtrics-rapporteringen med upp till 5 anpassade konverteringsdimensioner, 5 anpassade trafikdimensioner, 5 anpassade framgångsaktiviteter och mer än 20 andra standardvärden och dimensioner som spåras med Adobe Analytics.
* Integrerade enkätdata i Adobe Analytics flödar i&quot;live&quot; efterhand som enkäterna skickas in. Export till Qualtrics sker dagligen.

## Before you Activate this Connector{#before-you-activate-this-connector}

### Krav från Adobe {#section-fd37a66150c34cd6b494d13f75e5fb0d}

* Måste vara en befintlig kund till Adobe Analytics.
* Måste vara en administratörsanvändare.
* Du måste ha 1 tillgänglig och aktiverad List-variabel i rapportsviten.
* Måste ha 1 tillgänglig och aktiverad eVar-variabel (eller prop-variabel) i rapportsviten.
* Det måste finnas 1 tillgänglig anpassad händelse i rapportsviten.

### Förutsättningar för testversioner {#section-dbb780af47c145d7b6ae12acde3ca94c}

* Måste vara en befintlig kund till Qualtrics Research Suite.
* Måste vara en användare som har fått behörighet att aktivera Adobe Analytics Integration.
* Måste kunna generera en Adobe Analytics-token inom **[!UICONTROL Qualtrics IDs]** området för Research Suite.
