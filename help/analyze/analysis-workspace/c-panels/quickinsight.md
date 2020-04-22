---
description: 'null'
title: Quick Insights Builder
translation-type: tm+mt
source-git-commit: 77b126b2add78113c266265f413240f27f89bced

---


# Quick Insights Builder

>[!IMPORTANT]
>
>Quick Insights är för närvarande i betatestning och är inte allmänt tillgängligt för alla Adobe Analytics-kunder än.

Quick Insights ger vägledning för icke-analytiker och nya användare av Analysis Workspace så att de snabbt och enkelt kan få svar på affärsfrågor. Det är också ett bra verktyg för avancerade användare som snabbt vill besvara en fråga utan att själva behöva skapa en tabell.

När du börjar använda den här Analysis Workspace första gången kanske du undrar vilka visualiseringar som skulle vara mest användbara, vilka dimensioner och mätvärden som skulle kunna underlätta insikter, var objekten ska dras och släppas, var ett segment ska skapas osv.

För att underlätta detta, baserat på det egna företagets användning av datakomponenter i Analysis Workspace, utnyttjar Quick Insights en algoritm som ger dig de populäraste dimensionerna, mätvärdena, segmenten och datumintervallen som ditt företag använder.

Snabba insikter hjälper dig

* Bygg en datatabell och tillhörande visualisering korrekt i Analysis Workspace.
* Lär dig terminologi och vokabulär för grundläggande komponenter och delar av Analysis Workspace.
* Gör enkla uppdelningar av dimensioner, lägg till flera mätvärden eller jämför segment enkelt i en frihandstabell.
* Ändra eller prova olika visualiseringstyper för att snabbt och intuitivt hitta sökverktyget för din analys.

## Grundläggande nyckelterminologi

Nedan följer några grundläggande termer som du måste känna till. Varje datatabell består av två eller flera byggstenar som du använder för att berätta din databerättelse.

| Byggblock | Definition |
|---|---|
| Dimension | Dimensioner är beskrivningar eller egenskaper för mätdata som kan visas, delas upp och jämföras i ett projekt. De är icke-numeriska värden och datum som delas upp i dimensionsobjekt. Till exempel är &quot;webbläsare&quot; eller &quot;sida&quot; dimensioner. |
| Dimensionsartikel | Dimensionsobjekt är enskilda värden för en dimension. Dimensionsobjekten för webbläsardimensionen är till exempel Chrome, Firefox och Edge. |
| Mått | Mätvärden är kvantitativ information om besökaraktivitet, t.ex. visningar, klickningar, omladdningar, genomsnittlig tid, enheter, order, intäkter och så vidare. |
| Visualisering | Workspace erbjuder [ett antal visualiseringar](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md) för att skapa visuella representationer av dina data. |
| Segment | Med segment kan du identifiera undergrupper av besökare baserat på egenskaper eller webbplatsinteraktioner. Du kan till exempel skapa besökarsegment baserat på attribut: webbläsartyp, enhet, antal besök, land, kön eller baserat på interaktioner: kampanjer, sökordssökningar, sökmotorer eller baserat på avslutningar och tävlingsbidrag: besökare från Facebook, en definierad landningssida, hänvisande domän eller baserad på anpassade variabler: formulärfält, definierade kategorier, kund-ID. |

## Kom igång med Quick Insights

1. Logga in på Adobe Analytics med de inloggningsuppgifter du har fått.
1. Gå till [!UICONTROL Workspace] och klicka **[!UICONTROL Create New Project]** och klicka sedan **[!UICONTROL Quick Insights Builder]**.

   ![](assets/qibuilder.png)

1. När du börjar ska du gå igenom den korta självstudiekurs som lär ut några av grunderna i Quick Insight Builder. Du kan också klicka för att **[!UICONTROL Skip Tutorial]**.
1. Markera dina byggstenar (kallas även komponenter): dimensioner (orange), mått (grönt), segment (blått) eller datumintervall (lila) Du måste välja minst en dimension och ett mått för att en tabell ska skapas automatiskt.

   ![](assets/qibuilder2.png)

   Du kan välja byggblock på tre olika sätt:
   * Dra och släpp dem från den vänstra listen
   * Om du vet vad du söker: Börja skriva namnet så fyller Quick Insights i tomrummet
   * Klicka på listrutan och sök i listan

1. När du har lagt till minst en dimension och ett mått skapas följande för dig:

   * En friformstabell med måtten till vänster (lodrätt) och måtten längst upp (vågrätt). Kolla in den här tabellen:

1. (Valfritt) Detaljera mått och visa dimensionsobjekt genom att klicka på > högerpilen bredvid dimensionen.



## Kända begränsningar

Om du försöker redigera direkt i tabellen kommer Quick Insight Builder (verktyget för att fylla i det tomma) att bli osynkroniserat. Du kan återställa den till de tidigare Quick Insight-inställningarna, men om du inte skapar den direkt kommer tabellen nu att fungera som en traditionell Freeform-tabell.

