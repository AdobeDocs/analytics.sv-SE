---
description: Beskrivningar av rapporttyper som används i Experience Cloud.
title: Rapporttyper
topic: Ad hoc analysis
uuid: 357102eb-a172-40ec-a302-01c87abaacb5
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Rapporttyper

Beskrivningar av rapporttyper som används i Experience Cloud.

## Rankade rapporter {#concept_E1710FFFBB334F3D9DB63A1626DBCB01}

Visar en tabell med rankade objekt, med siffror och procenttal i mätvärden. En [!UICONTROL Pages Report] rankar till exempel sidorna på webbplatsen baserat på trafik, och detaljtabellen visar procenttal och siffror för mätvärden som Sidvyer och Intäkter. Ett vågrätt stapeldiagram är standarddiagramtypen. Diagram visar en färg för varje mätvärde. Rankade rapporter kan visa flera mätvärden i en rapport.

<!-- 

c_reports_ranked.xml

 -->

Rankade diagram har som standard fem objekt, men du kan skapa diagram med upp till trettio objekt i diagramalternativen.

## Trendrapporter {#concept_65FEA92704024232BB21A5952939711F}

Gör att du kan undersöka hur konverteringar och händelser trendar under en viss tidsperiod (timme, dag, vecka, månad, kvartal eller år) under en rapporteringsperiod.

<!-- 

c_reports_trended.xml

 -->

I diagrammet visas de spårade objekten på den lodräta axeln. Den vågräta axeln visar tidgranulariteten. I tabellen kan du göra en trend från en viss cell och sedan starta en fullständig rapport från cellen. Datumet eller tiden som används baseras på cellens värde.

Du kan också markera flera celler och starta en trendrapport utifrån en vald granularitet. När du trendar från flera celler visar rapportkolumnerna data för hela rapportperioden.

A [!UICONTROL Products Report] är ett exempel på en trendrapport. Du kan se hur mycket intäkter en produkt har haft under den valda perioden. Om rapportperioden är en vecka kan du se hur mycket intäkter den produkten genererade för varje dag i tidsperioden. Du kan visa ett trenddiagram för en viss produkt den dagen eller öppna en separat trendrapport för valet.

## Trend från celler {#task_AD9275BED5CE4D61AC25778D144406A4}

Steg som beskriver hur du startar en trendrapport från en eller flera celler i en tabell.

<!-- 

t_trend_row.xml

 -->

**Till trend från celler**

1. Öppna en rankad rapport.
1. Leta reda på cellen i tabellen och klicka på **[!UICONTROL Trend]**.

   ![](assets/TrendInspector_Buttcon.png)

1. Om du vill visa en fullständig rapport från cellen klickar du på **[!UICONTROL Launch Trend Report]**.

   Du kan också högerklicka på cellen och sedan klicka **[!UICONTROL Trend Cell]**. Du kan även utföra den här åtgärden när du har markerat flera celler.

## Summarapport {#concept_48E23FB3BCCD43DFB486A048960800A8}

<!-- 

c_reports_totals.xml

 -->

En rapport på chefsnivå som visar siffror i resultatet. Den innehåller information om totala intäkter, sidvisningar och beställningar. Du kan segmentera rapporten och lägga till ytterligare mått för att visa ytterligare data.

## Flödesrapporter {#concept_3E417D018F1B4566973F694B01E6439F}

Flödesrapporter visar de vanligaste sökvägarna som användare tar över sidor, webbplatsavsnitt och servrar.

<!-- 

c_reports_flow.xml

 -->

**Nästa flöde**

Rapportgruppen har tre rapporter: [!UICONTROL Next Flow] [!UICONTROL Next Page Flow], [!UICONTROL Next Section Flow]och [!UICONTROL Next Server Flow]. Rapporterna i den här gruppen visar de vanligaste sidorna, webbplatsavsnitten och servrarna som en besökare har haft tillgång till efter att ha öppnat sidan, webbplatsavsnittet eller servern som du anger. De här rapporterna visar de vanligaste sökvägarna till din webbplats.

**Föregående flöde**

Tidigare Flödesrapporter liknar rapporterna för nästa flöde, förutom att du inte kan se var besökarna kom efter en vald sida, utan var besökarna befann sig innan du besökte en viss sida. Kontrollerna för att använda rapporten är identiska med kontrollerna för rapporterna för nästa flöde.

## Nästa sidflöde {#concept_F7565234927942BEAF75D5D94A7AB47D}

Visar banvyer eller antalet gånger och procenttal som en sida har visats inom sökvägarnas begränsningar. En integritetspolicy-sida kan till exempel ha totalt 10 000 sidvisningar, men endast 500 av dessa sidvyer inträffade omedelbart före en hemsida. I det här fallet ser du 500 banvyer. Du kan visa rapporten på besöks- eller besöksnivå. Procenttal för varje sida visas bredvid sidans namn. Bredden på en linje som är kopplad till en sida visar den relativa andelen besök.

<!-- 

c_reports_next_page_flow.xml

 -->

Som standard visar den här rapporten de 10 översta sidorna som användarna gick till efter den sida du valde. Du kan klicka på en understruken sida för att expandera diagrammet ytterligare. Det finns ingen gräns för hur många sidor du kan ha i diagrammet, och du kan hovra över en sida för att se besöks- och intäktsdata för sidan.

Använd den här rapporten för att:

* Förstå vilka steg som utförs oftast när du har visat en markerad sida.
* Optimera sajtens sökvägsdesign för att flytta trafiken till önskad målsida.
* Identifiera vart besökarna ska åka istället för de önskade målsidorna.

## Nästa serverflöde {#concept_DB8C20E18AEA4051903C47A16C0E9C4E}

Visar navigeringsdata mellan servrar på platsen. När du väljer ett servernamn från din plats visar rapporten antalet besökare som navigerade från den servern till de andra servrarna på din plats under ett enda besök eller mellan besök.

<!-- 

c_reports_next_server_flow.xml

 -->

Om du till exempel har specifika data på olika servrar eller har speglade data på separata servrar visar rapporten sökvägen mellan servrar som användarna träffar på. Detta gäller även domäner på webbplatsen. Du kan till exempel se hur många användare som har gått från en `https://www.mysite.com` till `https://info.mysite.com` eller `https://sales.mysite.com`.

## Nästa avsnittsflöde {#concept_7C9C8567E7DF477DA186E47DD3FD47A4}

Rapporten [!UICONTROL Next Section Flow] liknar [!UICONTROL Next Page Flow] rapporten. Här visas data för webbplatsavsnitt (grupper med relaterade webbsidor). Om det finns en sida i mer än ett webbplatsavsnitt visas data för alla webbplatsavsnitt i rapporten.

<!-- 

c_reports_next_section_flow.xml

 -->

En webbutik kan till exempel ha avsnitt för sina produkter och avsnitt för produktvarumärken. I det här fallet kan en produktwebbsida omfattas av flera sektioner. Även om en produktsida bara har visats en gång, visar rapporten en sidvy för varje synavsnitt som är kopplat till sidan. [!UICONTROL Next Section Flow]

## Föregående sidflöde {#concept_ADEAEBAE3F37401B977A27E03B5A523B}

Liknar [!UICONTROL Next Page Flow] rapporten. I [!UICONTROL Previous Page Flow] rapporten visas flera nivåer av de mest populära sidorna som besökarna ser före den valda sidan. Rapporten markerar också sidor där besökare kommer in på webbplatsen.

<!-- 

c_reports_previous_page_flow.xml

 -->

Använd den här rapporten för att:

* Förstå vilka steg som utförs oftast innan du visar en markerad sida.
* Optimera sajtens sökvägsdesign för att flytta trafiken till önskad målsida.

## Föregående avsnittsflöde {#concept_30688D97B48449E1958866BAF376FA8C}

Rapporten [!UICONTROL Previous Section Flow] liknar [!UICONTROL Previous Page Flow] rapporten. Här visas data för webbplatsavsnitt (grupper med relaterade webbsidor). Om en sida finns i mer än ett webbplatsavsnitt visar rapporten data för alla webbplatsavsnitt.

<!-- 

c_reports_previous_section_flow.xml

 -->

En webbutik kan till exempel ha avsnitt för sina produkter och avsnitt för produktvarumärken. I det här fallet kan en produktwebbsida omfattas av flera sektioner. Även om en produktsida bara har visats en gång, visar rapporten en sidvy för varje synavsnitt som är kopplat till sidan. [!UICONTROL Previous Section Flow]

## Föregående serverflöde {#concept_8E43208CAF2C4C358F19D4669B73822F}

Den här rapporten visar navigeringsdata mellan servrar på din plats. När du väljer ett servernamn från din plats visar rapporten antalet besökare som navigerade till den servern från de andra servrarna på din plats under ett enda besök eller vid flera besök.

<!-- 

c_reports_previous_server_flow.xml

 -->

Om du till exempel har specifika data på olika servrar eller har speglade data på separata servrar visar rapporten sökvägen mellan servrar som användarna träffar på. Detta gäller även domäner på webbplatsen. Du kan till exempel se hur många användare som har gått från en `www.mysite.com` till `info.mysite.com` eller `sales.mysite.com`.

## Konverteringstrattrapporter {#concept_35A2EB61E84441CBB670C2E02CA26F81}

Konverteringstrattrapporter visar konverteringsprocentsatser mellan specifika måtthändelser. Du kan använda den här rapporten för att förstå antalet klickningar som genererar försäljning och antalet sålda enheter. En rapport visar t.ex. andelen händelser i kundvagnen som är relaterade till besökshändelser och visar sedan summorna för beställningar, intäkter och enheter baserat på dessa händelser. [!UICONTROL Products Conversion]

<!-- 

c_reports_conversion_funnel.xml

 -->

Följande trattrapporter är tillgängliga:

* [!UICONTROL Purchase Conversion Funnel]: Visar besök (rapportspecifika), kundvagnar, beställningar, enheter och intäkter.
* [!UICONTROL Cart Conversion Funnel]: Visar besök (rapportspecifika), kundvagnar, utcheckningar, beställningar och intäkter.
* [!UICONTROL Custom Event Funnel]: Visar anpassade händelser på din plats. Den visar anpassade händelser 1-5 som standard.
* [!UICONTROL Campaign Conversion Funnel]: Visar genomklickningar, utcheckningar, beställningar och intäkter.

Rapporttabellen visar statistik för genomsnittlig försäljning per klickfrekvens och genomsnittliga enheter som säljs per klickfrekvens. Du kan lägga till mått och anpassade händelser från andra rapporteringsgrupper i dessa rapporter. Dessa trattar har många likheter men baseras på olika variabler och händelser. Du kan använda de här rapporterna för att se vilka procentsatser och allmänna trender för användare som utlöser specifika händelser som du anger. Du kan se var användarna inte följer med till händelser, vilket ger insikt i just den punkten i konverteringsprocessen.

## Platsanalysrapport {#concept_65694C6BDE424714B7975764F95497A4}

[!UICONTROL Site Analysis] visar hur besökare rör sig genom angivna sidor och händelser. Du kan till exempel se hur trafiken flödar mellan sidorna, hur produkterna och marknadsföringskanalerna ser ut och hur kampanjer och kanaler flödar till produktbeställningar. Du kan dra sidor, dimensionsobjekt (och listor) och måtthändelser. Varje cylinder representerar en eller flera dimensionsobjekt (sidor) eller en händelse. Pilar representerar flödet mellan cylindervärdena. Mätvärden tilldelas cylinderpositioner (X och Y), cylinderbredd, cylinderhöjd och färg. Placeringen, storleken och färgen ändras beroende på måttvärdena.

<!-- 

c_reports_site_analysis.xml

 -->

Dra objekt från verktygspaneler för att lägga till dem i diagrammet eller i måttfältet.

Högerklicka på cylindrarna för att redigera eller ta bort dem.

<!-- Meike, UICONTROL and DNL stripped from tables. Re-add. -->

| Alternativ | Beskrivning |
|--- |--- |
| Visa webbplatsanalys (besök eller besökare) | Gör att du kan växla mellan Besök och Besök för att analysera besökarbanan. Dessa inställningar hjälper er att förstå besökarnas engagemang på besökarnivå, oavsett besök. Webbplatsanalys-, flödes- och bortfallsrapporter är aktiverade för besökspassning. Om du ändrar den här inställningen returneras rapporten, vilket begränsar data till markeringen. |
| Lägg till kontrollpunkt | Visar kontrollpunktsredigeraren, där du kan välja mått eller händelser som ska läggas till i visningen. |
| Ersätt diagram | Ersätter platsanalysdiagrammet med de kontrollpunkter som du lägger till i redigeraren. |
| Anpassa till skärm | Återställer diagrammets ursprungliga vy. |
| Flygvy | Ger en nedrullningsbar vy av diagrammet. |
| Växla stödraster | Aktiverar och inaktiverar stödrastret. |
| Dimension | Den artikel som du rapporterar för. Dra objektet från Dimensioner. |

| Alternativ | Beskrivning |
|--- |--- |
| Redigera | Gör att du kan lägga till eller ta bort sidor i en cylinder. |
| Ta bort | Du kan ta bort en cylinder. |
| Rapporter | Du kan starta en annan rapport från behållaren. |
| Spara diagram som | Gör att du kan spara diagrammet som .png eller .jpg. Om du ändrar diagramkontrollerna (diagramvinkel, storlek) innan du sparar dem bevaras ändringarna i utdata. |
| Kopiera diagram till Urklipp | Kopierar diagrammet för inklistring till ett annat program. Om du ändrar diagramkontrollerna (diagramvinkel, storlek) innan du sparar dem bevaras ändringarna i utdata. |
