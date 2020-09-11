---
description: En panel är en samling tabeller och visualiseringar
title: Översikt över paneler
translation-type: tm+mt
source-git-commit: 8cfd2106df3aed48136ec82bca7d2cb19a479d61
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 3%

---


# Översikt över paneler

En panel är en samling tabeller och visualiseringar. Du kommer åt panelerna från den övre vänstra ikonen i arbetsytan. Paneler är användbara när du vill ordna dina projekt efter tidsperioder, rapportsviter eller användningsfall för analyser. Följande paneltyper är tillgängliga i Analysis Workspace:

| Panelnamn | Beskrivning |
|---|---|
| [Tom panel](blank-panel.md) | Välj bland tillgängliga paneler och visualiseringar för att starta analysen. |
| [Panelen Snabbinsikter](quickinsight.md) | Bygg snabbt ett frihandsbord och en medföljande visualisering för att analysera och hitta insikter snabbare. |
| [Analyser för målpanelen](a4t-panel.md) | Analysera Target-aktiviteter och -upplevelser i Analysis Workspace. |
| [Panelen Attribution](attribution.md) | Jämför och visualisera snabbt valfritt antal attribueringsmodeller med alla mått och konverteringsvärden. |
| [Frihandspanel](freeform-panel.md) | Utför obegränsade jämförelser och uppdelningar och lägg sedan till visualiseringar för att berätta en utförlig databerättelse. |
| [Panelen för samtidiga medieanvändare](media-concurrent-viewers.md) | Analysera samtidiga tittare över tid, med information om maximal samtidighet och möjlighet att dela upp och jämföra. |
| [Segmentjämförelsepanel](c-segment-comparison/segment-comparison.md) | Jämför snabbt två segment över alla datapunkter för att automatiskt hitta relevanta skillnader. |

Snabbinsikter, tomma paneler och frihandspaneler är bra platser att starta analysen på, medan Analytics for Target, Attribution IQ, Media Concurrent Viewer och Segment Comparison är mer avancerade analyser. En `"+"` knapp är tillgänglig i projekt, så du kan när som helst lägga till tomma paneler.

Standardstartpanelen är friformspanelen, men du kan även göra den [tomma panelen](/help/analyze/analysis-workspace/c-panels/blank-panel.md) till standard.

## Panel report suite {#report-suite}

Tabeller och visualiseringar i en panel hämtar data från rapportsviten som valts i panelens övre högra hörn. Rapportsviten avgör också vilka komponenter som är tillgängliga i den vänstra listen. Inom ett projekt kan du använda en eller [flera rapportsviter](https://docs.adobe.com/content/help/sv-SE/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html) beroende på dina analysexempel.

## Panelkalender {#calendar}

Panelkalendern styr rapporteringsintervallet för tabeller och visualiseringar inom en panel. Obs! Om en (lila) datumintervallkomponent används i en tabell, visualisering eller paneldropzon åsidosätts panelkalendern.

## Panelens dropzon {#dropzone}

Med panelens listruta kan du tillämpa segment- och listrutefilter på alla tabeller och visualiseringar i en panel. Du kan använda ett eller flera filter på en panel. Titeln ovanför varje filter kan ändras genom att du klickar på redigeringspennan eller så kan du högerklicka för att ta bort den helt.

### Segmentfilter

Dra och släpp ett segment från den vänstra listen i panelens släppzon för att börja filtrera panelen.

### Egna segmentfilter

Komponenter som inte tillhör segment kan också dras direkt till dropzone för att skapa **adhoc-segment**, vilket sparar tid och kraft åt att gå till Segment Builder. Segment som skapas på det här sättet definieras automatiskt som träffnivåsegment. Du kan ändra den här definitionen genom att klicka på informationsikonen (i) bredvid segmentet, sedan den pennformade redigeringsikonen och redigera den i segmentbyggaren.

Adhoc-segment är lokala för projektet och visas inte i den vänstra listen om du inte gör dem offentliga.

### Nedrullningsbara filter {#dropdown-filter}

Förutom segmentfilter gör **nedrullningsbara filter** att du kan interagera med data på ett kontrollerat sätt. Du kan t.ex. lägga till ett nedrullningsbart filter för mobila enhetstyper så att du kan segmentera panelen via Surfplatta, Mobiltelefon eller Skrivbord.

Nedrullningsbara filter kan även användas för att konsolidera flera projekt till ett. Om du till exempel har många versioner av samma projekt med olika landssegment tillämpade, kan du konsolidera alla versioner till ett enda projekt och lägga till ett nedrullningsbart landsfilter.

**Skapa och använda nedrullningsbara filter:**

1. Om du vill skapa ett nedrullningsbart filter med hjälp av objekt i Dimensionen, till exempel värden i marknadsföringskanalen, klickar du på markeringen bredvid dimensionen i det vänstra fältet. Då visas alla tillgängliga objekt. Markera ett eller flera komponentobjekt i den vänstra listen och släpp dem i panelens dropzon **samtidigt som du håller ned Skift**. Komponenterna blir då ett nedrullningsbart filter i stället för ett enda segment.
1. Om du vill skapa ett nedrullningsbart filter med hjälp av andra komponenter, som mått, segment eller datumintervall, väljer du en komponenttyp i den vänstra listen och släpper i panelens listruta **samtidigt som du håller ned Skift-tangenten**.
1. Välj ett av alternativen i listrutan om du vill ändra data på panelen. Du kan också välja att inte filtrera paneldata genom att markera **[!UICONTROL No filter]**.

[Titta på videon](https://www.youtube.com/watch?v=vpJywtsFVPI) och lär dig mer om hur du lägger till nedrullningsbara filter i ett projekt.
