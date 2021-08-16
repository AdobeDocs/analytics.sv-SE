---
description: Använd linjevisualisering för att avbilda trenddata (tidsbaserade)
title: Linjediagram
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
feature: Visualiseringar
role: User, Admin
exl-id: d177b39f-add7-4011-977a-1bdf3a9368cb
source-git-commit: 804cf43f2e5f1270e04644affd629c06583816ec
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 0%

---

# Linjediagram

Visualiseringen [!UICONTROL Line] representerar mätvärden som använder en rad för att visa hur värden ändras under en tidsperiod. Ett [!UICONTROL Line]-diagram kan bara användas när tid används som dimension.

![Radvisualisering](assets/line-viz.png)

Klicka på kugghjulsikonen i det övre högra hörnet av visualiseringen [!UICONTROL Line] för att komma åt [**Visualiseringsinställningarna**](freeform-analysis-visualizations.md) som är tillgängliga. Inställningarna är indelade i:

* **Allmänt**: Inställningar som är gemensamma för olika visualiseringstyper
* **Axel**: Inställningar som påverkar x- eller y-axeln i linjens visualisering
* **Övertäckningar**: Alternativ för att lägga till ytterligare kontext till de serier som visas i din radvisualisering.

![Visualiseringsinställningar](assets/viz-settings-modal.png)

## Ändra granularitet

Med en listruta för granularitet i [visualiseringsinställningarna](freeform-analysis-visualizations.md) kan du ändra en anpassad visualisering (t.ex. rad, bar) från dag till vecka till månad, osv. Granulariteten uppdateras också i datakälltabellen.

## Visa min eller max

Under **[!UICONTROL Visualization Settings]** > **[!UICONTROL Overlays]** > **[!UICONTROL Show min/max]** kan du täcka över en etikett för minsta och högsta värde för att snabbt markera toppar och dalar i ett mätresultat. Obs! min/max-värdena härleds från de synliga datapunkterna i visualiseringen, inte från hela uppsättningen värden inom en dimension.

![Visa min/max](assets/min-max-labels.png)

## Visa trendlinjeövertäckning

Under **[!UICONTROL Visualization Settings]** > **[!UICONTROL Overlays]** > **[!UICONTROL Show trendline]** kan du välja att lägga till en regression eller en glidande medeltrendlinje i radserien. Trendlinjer hjälper till att beskriva ett tydligare mönster i data.

Här är en video om hur du lägger till trendlinjer i linjevisualiseringar:

>[!VIDEO](https://video.tv.adobe.com/v/330176/?quality=12)

>[!TIP]
>
>Vi rekommenderar att trendlinjer tillämpas på data som inte innehåller dagens (partiella data) eller framtida datum, eftersom de skevar trendlinjen. Om du behöver ta med framtida datum tar du dock bort nollor från data för att undvika skevning för dessa dagar. Det gör du genom att gå till visualiseringens datakälltabell, välja måttkolumnen och sedan aktivera **[!UICONTROL Column Settings]** > **[!UICONTROL Interpret zero as no value]**.

![Linjär trendlinje](assets/show-linear-trendline.png)

Alla trendlinjer för regressionsmodellen passas in med vanliga minsta fyrkanter:

| Modell | Beskrivning |
| --- | --- |
| Linjär | Skapar en rät linje som passar bäst för enkla linjära datauppsättningar och är användbar när data ökar eller minskar med en konstant hastighet. Ekvation: `y = a + b * x` |
| Logaritmisk | Skapar en kurvformad linje som passar bäst och är användbar när ändringshastigheten i data snabbt ökar eller minskar och sedan Nivåer ut. En logaritmisk trendlinje kan använda negativa och positiva värden. Ekvation: `y = a + b * log(x)` |
| Exponentiell | Skapar en böjd linje och är användbar när data ökar eller minskar med konstant ökande hastighet. Det här alternativet ska inte användas om dina data innehåller noll eller negativa värden. Ekvation: `y = a + e^(b * x)` |
| Strömförsörjning | Skapar en böjd linje och är användbar för datauppsättningar som jämför mått som ökar med en viss hastighet. Det här alternativet ska inte användas om dina data innehåller noll eller negativa värden. Ekvation: `y = a * x^b` |
| Kvadratisk | Söker efter den bästa passningen för en datauppsättning som är formad som en parabola (konkav uppåt eller nedåt). Ekvation: `y = a + b * x + c * x^2` |
| Glidande medelvärde | Skapar en jämn trendlinje baserad på en uppsättning medelvärden. Ett glidande medelvärde kallas även för ett rullande medelvärde och använder ett visst antal datapunkter (som bestäms av ditt urval av &#39;Perioder&#39;), jämför dem och använder medelvärdet som en punkt på raden. Exempel är 7 dagars glidande medelvärde eller 4 veckors glidande medelvärde. |
