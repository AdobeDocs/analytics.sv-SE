---
description: Använd linjevisualisering för att avbilda trenddata (tidsbaserade)
title: Linjediagram
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
translation-type: tm+mt
source-git-commit: c607489f14057be10a5582b8e6d9e07d7f075b6f
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 0%

---


# Linjediagram

Radvisualiseringen representerar mätvärden som använder en rad för att visa hur värden ändras under en tidsperiod. Ett linjediagram kan bara användas när tid används som dimension.

![Radvisualisering](assets/line-viz.png)

Klicka på kugghjulsikonen i det övre högra hörnet av linjevisualiseringen för att komma åt [**visualiseringsinställningarna**](freeform-analysis-visualizations.md) . Inställningarna är indelade i:

* **Allmänt**: Inställningar som är gemensamma för olika visualiseringstyper
* **Axel**: Inställningar som påverkar x- eller y-axeln i linjens visualisering
* **Övertäckningar**: Alternativ för att lägga till ytterligare kontext till de serier som visas i din radvisualisering.

![Visualiseringsinställningar](assets/viz-settings-modal.png)

## Ändra granularitet

Med en listruta för granularitet i [visualiseringsinställningarna](freeform-analysis-visualizations.md) kan du ändra en trendvisualisering (t.ex. rad, rad) från dag till vecka till månad, osv. Granulariteten uppdateras också i datakälltabellen.

## Visa min eller max

Under **[!UICONTROL Visualization Settings]** > **[!UICONTROL Overlays]** > **[!UICONTROL Show min/max]** kan du täcka över en etikett för minsta och högsta värde för att snabbt markera toppar och dalar i ett mätresultat. Obs! min/max-värdena härleds från de synliga datapunkterna i visualiseringen, inte från hela uppsättningen värden inom en dimension.

![Visa min/max](assets/min-max-labels.png)

## Visa trendlinjeövertäckning

Under **[!UICONTROL Visualization Settings]** > **[!UICONTROL Overlays]** > **[!UICONTROL Show trendline]** kan du välja att lägga till en regression eller en glidande medeltrendlinje i linjeserierna. Trendlinjer hjälper till att beskriva ett tydligare mönster i data.

>[!TIP]
>
>Vi rekommenderar att trendlinjer tillämpas på data som inte innehåller dagens (partiella data) eller framtida datum, eftersom de förvränger trendlinjen. Om du behöver ta med framtida datum tar du dock bort nollor från data för att undvika skevning för dessa dagar. Det gör du genom att gå till visualiseringens datakälltabell och välja måttkolumnen. Gå sedan till [!UICONTROL Column Settings] och kolla **[!UICONTROL Interpret zero as no value]**.)

![Linjär trendlinje](assets/show-linear-trendline.png)

Alla trendlinjer för regressionsmodellen passas in med vanliga minsta fyrkanter:

| Modell | Beskrivning |
| --- | --- |
| Linjär | Skapar en rät linje som passar bäst för enkla linjära datauppsättningar och är användbar när data ökar eller minskar med en konstant hastighet. Ekvation: `y = a + b * x` |
| Logaritmisk | Skapar en kurvformad linje som passar bäst och är användbar när ändringshastigheten i data snabbt ökar eller minskar och sedan Nivåer ut. En logaritmisk trendlinje kan använda negativa och positiva värden. Ekvation: `y = a + b * log(x)` |
| Exponentiell | Skapar en böjd linje och är användbar när data ökar eller minskar med konstant ökande hastighet. Det här alternativet ska inte användas om dina data innehåller noll eller negativa värden. Ekvation: `y = a + e^(b * x)` |
| Strömförsörjning | Skapar en böjd linje och är användbar för datauppsättningar som jämför mått som ökar med en viss hastighet. Det här alternativet ska inte användas om dina data innehåller noll eller negativa värden. Ekvation: `y = a * x^b` |
| Kvadratisk | Söker efter den bästa passningen för en datauppsättning som är formad som en parabola (konkav uppåt eller nedåt). Ekvation: `y = a + b * x + c * x^2` |
| Glidande medelvärde | Skapar en jämn trendlinje baserad på en uppsättning medelvärden. Exempel är 7 dagars glidande medelvärde eller 4 veckors glidande medelvärde. Ett glidande medelvärde, som också kallas rullande medelvärde, beräknar medelvärdet för ett tidigare intervall, använder det som trendlinjedatapunkt och går sedan till nästa period för att upprepas. Indata för Perioder definierar intervallet som ska användas för att beräkna medelvärdet över. |
