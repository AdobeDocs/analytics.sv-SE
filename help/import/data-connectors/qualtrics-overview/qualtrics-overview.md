---
description: Integrationen kombinerar Qualtrics Research Suites funktioner för kundundersökningar med de omfattande data ni samlar in inom Adobe Analytics för att skapa kraftfulla analyser och optimeringsmöjligheter för er organisation.
subtopic: Qualtrics
title: Qualtrics Data Connector för Adobe Analytics
feature: Data Connectors
uuid: f1fa90b6-1b80-4da4-a39b-efb8bac1692a
exl-id: 5c1234b1-bca8-4e7a-981e-1379e88821b8
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 5%

---

# Qualtrics Data Connector för Adobe Analytics{#qualtrics-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>Adobe Data Connector-tekniken upphör den 1 augusti 2021. [Läs mer …](/help/import/data-connectors/data-connectors-eol.md)

Integrationen kombinerar Qualtrics Research Suites funktioner för kundundersökningar med de omfattande data ni samlar in inom Adobe Analytics för att skapa kraftfulla analyser och optimeringsmöjligheter för er organisation.

Denna tvåvägsintegrering kopplar först svarsdata från Qualtrics-undersökningen till besökarens klickströmsdata. Sedan injiceras relevanta beteendebeteenden och attribut, från Adobe Analytics, tillbaka i Qualtrics-enkätrapporten.

## Viktiga fördelar och funktioner{#key-benefits-and-features}

* Bygg användarsegment baserat på de svar användarna ger på specifika enkätfrågor.
* Trafik- och konverteringsrapportering baserad på enkät-, fråge- och svarsnivådetaljer.
* Använder endast en ListVar-, 1 eVar- och 1-händelse för att integrera ett obegränsat antal Qualtrics-undersökningar.
* Förbättra Qualtrics-rapporteringen med upp till 5 anpassade konverteringsdimensioner, 5 anpassade trafikdimensioner, 5 anpassade lyckade händelser och mer än 20 andra standardvärden och dimensioner spårade med Adobe Analytics.
* Integrerade enkätdata i Adobe Analytics strömmar in &quot;live&quot; allteftersom enkäterna lämnas in. Export till Qualtrics sker dagligen.

## Innan du aktiverar den här kopplingen{#before-you-activate-this-connector}

### Förutsättningar för Adobe {#section-fd37a66150c34cd6b494d13f75e5fb0d}

* Måste vara Adobe Analytics nuvarande kund.
* Måste vara en administratörsanvändare.
* Du måste ha 1 tillgänglig och aktiverad List-variabel i rapportsviten.
* Måste ha 1 tillgänglig och aktiverad variabel (eller prop) inom rapportsviten.
* Det måste finnas 1 tillgänglig anpassad händelse i rapportsviten.

### Förutsättningar för kvaltrik {#section-dbb780af47c145d7b6ae12acde3ca94c}

* Måste vara en befintlig kund till Qualtrics Research Suite.
* Måste vara en användare som har fått behörighet att aktivera Adobe Analytics Integration.
* Måste kunna generera en Adobe Analytics-token inom **[!UICONTROL Qualtrics IDs]**-området i Research Suite.
