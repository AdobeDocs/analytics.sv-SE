---
description: Använd linjevisualisering för att avbilda trenddata (tidsbaserade)
title: Linjediagram
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
translation-type: tm+mt
source-git-commit: 34db4e99589827fd41f642788e3409834b96d78a
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 2%

---


# Linjediagram

Den här visualiseringen representerar mätvärden som använder en rad för att visa hur värden ändras under en tidsperiod. Ett linjediagram kan bara användas när tid används som dimension.

## Visualiseringsinställningar

>[!IMPORTANT]
>
> Vissa inställningar för linjevisualisering, till exempel Visa trendlinje, är för närvarande i begränsad testning. [Läs mer](https://docs.adobe.com/content/help/sv-SE/analytics/landing/an-releases.html).

Klicka på kugghjulsikonen i det övre högra hörnet av linjevisualiseringen för att komma åt [**visualiseringsinställningarna**](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html#section_D3BB5042A92245D8BF6BCF072C66624B) . Inställningarna är indelade i:

* Allmänt - inställningar som är gemensamma för olika visualiseringstyper
* Axel - inställningar som påverkar x- eller y-axeln i linjens visualisering
* Övertäckningar - alternativ för att lägga till ytterligare kontext till serien som visas i linjevisualiseringen.

### Ändra granularitet

Med en listruta för granularitet i [visualiseringsinställningarna](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#section_D3BB5042A92245D8BF6BCF072C66624B) kan du ändra en trendvisualisering (t.ex. rad, rad) från dag till vecka till månad, osv. Granulariteten uppdateras också i datakälltabellen.

### Visa min eller max

Under **Visualiseringsinställningar > Övertäckningar > Visa min/max** kan du överlappa en etikett för minsta och högsta värde för att snabbt markera toppar och dalar i ett mätresultat.

### Visa trendlinjeövertäckning

Under **Visualiseringsinställningar > Övertäckningar > Visa trendlinje** kan du välja att lägga till en regressionstrendlinje i din radserie. Trendlinjer hjälper till att beskriva ett tydligare mönster i data.

Alla modeller passas in med vanliga minsta fyrkanter:

| Modell | Beskrivning |
|---|---|
| Linjär | Skapar en rät linje som passar bäst för enkla linjära datauppsättningar och är användbar när data ökar eller minskar med en konstant hastighet. Ekvation: y = a + b * x |
| Logaritmisk | Skapar en kurvformad linje som passar bäst och är användbar när ändringshastigheten i data snabbt ökar eller minskar och sedan Nivåer ut. En logaritmisk trendlinje kan använda negativa och positiva värden. Ekvation: y = a + b * log(x) |
| Exponentiell | Skapar en böjd linje och är användbar när data ökar eller minskar med konstant ökande hastighet. Det här alternativet ska inte användas om dina data innehåller noll eller negativa värden. Ekvation: y = a +<sup>eb * x |
| Strömförsörjning | Skapar en böjd linje och är användbar för datauppsättningar som jämför mått som ökar med en viss hastighet. Det här alternativet ska inte användas om dina data innehåller noll eller negativa värden. Ekvation: y = a *<sup>xb |
| Kvadratisk | Söker efter den bästa passningen för en datauppsättning som är formad som en parabola (konkav uppåt eller nedåt). Ekvation: y = a + b * x + c * x<sup>2 |
| Polynomik | Användbar när datauppsättningen ändras, till exempel när du analyserar vinster och förluster i en stor datauppsättning. Ekvation: y = a + b * x + ... + k *<sup>xorder |
