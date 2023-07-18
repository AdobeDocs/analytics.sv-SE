---
description: Använd flödesvisualisering i ett Workspace-projekt.
title: Konfigurera en flödesvisualisering
feature: Visualizations
role: User, Admin
exl-id: c2fdcc96-81ac-4d3b-b255-ff805b6ff0ea
source-git-commit: d1c2966bfd7cb5e397de23adf45bb38fca34e416
workflow-type: tm+mt
source-wordcount: '1254'
ht-degree: 1%

---

# Konfigurera en flödesvisualisering

Flödesvisualiseringar hjälper er att förstå den resa som härrör från eller leder fram till en specifik konverteringshändelse på er webbplats eller i er app. Den spårar en bana genom dina dimensioner (och dimensionsobjekt) eller mätvärden.

Med flödesvisualiseringar kan du konfigurera början eller slutet av den sökväg du är intresserad av, eller analysera alla banor som flödar genom en dimension eller dimensionspost.

![nytt flödesgränssnitt](assets/new-flow.png)

## Skapa en flödesvisualisering {#configure}

1. Lägg till en tom panel i projektet och klicka på visualiseringsikonen i den vänstra listen.

   eller

   Lägg till en visualisering på något av de sätt som beskrivs i avsnittet Lägg till visualiseringar i en panel i [Översikt över visualiseringar](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Förankra Flödesvisualiseringen med något av följande alternativ:

   * [!UICONTROL **Börjar med**] (mått, dimensioner eller objekt), eller
   * [!UICONTROL **Innehåller**] (mått, eller objekt), eller
   * [!UICONTROL **Slutar med**] (mått, dimensioner eller objekt)

   Var och en av dessa kategorier visas på skärmen som en&quot;släppzon&quot;. Du kan fylla i släppzonen på tre sätt:

   * Använd listrutan för att välja mått eller mått.
   * Dra mått eller mätvärden från den vänstra listen.
   * Börja skriva namnet på en dimension eller ett mått och markera det sedan när det visas i listrutan.

   >[!IMPORTANT]
   >
   >Beräknade mått kan inte användas i  **[!UICONTROL Starts with]** eller **[!UICONTROL Ends with]** fält.

1. Om du väljer ett mätvärde måste du även ange [!UICONTROL **Dimensionen Banor**] som du kan använda som bana som leder till eller går från den markerade komponenten, vilket visas här. Standardvärdet är [!UICONTROL **Sida**].

   ![målningsdimension](assets/pathing-dim.png)

1. (Valfritt) Välj **[!UICONTROL Show advanced settings]** om du vill konfigurera något av följande alternativ:

   ![avancerade inställningar](assets/adv-settings.png)

   | Inställning | Beskrivning |
   | --- | --- |
   | **[!UICONTROL Wrap labels]** | Etiketterna på Flow-elementen trunkeras normalt för att spara skärmutrymme, men du kan göra hela etiketten synlig genom att markera den här rutan.  Standard = avmarkerat. |
   | **[!UICONTROL Include repeat instances]** | Flödesvisualiseringar baseras på instanser av en dimension. Den här inställningen ger dig möjlighet att inkludera eller exkludera upprepade instanser, t.ex. sidomladdning. Det går dock inte att ta bort upprepningar från Flow-visualiseringar som innehåller flervärdesdimensioner, som listVars, listProps, s.product, merchandising eVars osv. <p>Det här alternativet är inaktiverat som standard.</p> |
   | **[!UICONTROL Limit to first/last occurrence]** | Begränsa banor till dem som börjar/slutar med den första/sista förekomsten av en dimension/artikel/mått. Se avsnittet nedan [Exempelscenario för &#39;begränsa till första/sista förekomsten&#39;](#example-scenario-for-limit-to-firstlast-occurrence), för en mer detaljerad förklaring. |
   | **[!UICONTROL Number of columns]** | Antalet kolumner som du vill ha i flödesdiagrammet. |
   | **[!UICONTROL Items expanded per column]** | Antalet objekt som du vill ha i varje kolumn. |
   | **[!UICONTROL Flow container]** | <ul><li>Gå in på</li><li>Besökare</li></ul> Gör att du kan växla mellan Besök och Besök för att analysera besökarbanan. Dessa inställningar hjälper er att förstå besökarnas engagemang på besökarnivå (mellan besök) eller begränsa analysen till ett enda besök. |

1. Välj **[!UICONTROL Build]**.

>[!INFO]
>
>**Exempel:** Anta att du vill spåra sökvägen som användare tog både till och från de mest populära sidorna på din webbplats.
>
>För att göra detta skulle du
>1. Börja skapa en flödesvisualisering enligt beskrivningen ovan.
>1. Dra [!UICONTROL **Sida**] dimensionen i **[!UICONTROL Contains]** fält och sedan markera [!UICONTROL **Bygge**].
>1. Flödesvisualiseringen byggs med den mest visade sidan synlig i fokusnoden mitt i visualiseringen. Du kan även se de översta sidorna som leder till den sidan (till vänster om fokusnoden) samt de översta sidorna som leder ut från fokussidan (till höger om fokusnoden).
>1. Analysera data i flödet enligt beskrivningen i [Visa och ändra flödesutdata](#view-and-change-the-flow-output).


## Visa och ändra flödesutdata {#output}

![flödesutdata](assets/flow-output.png)

En sammanfattning av flödeskonfigurationen visas högst upp i diagrammet. Tjockleken på en bana i diagrammet är proportionell mot dess aktivitet, med banor med mer aktivitet som ser tjockare ut än de med mindre aktivitet.

Om du vill gå längre ned i informationen har du flera alternativ:

* Flödesdiagrammet är interaktivt. För musen över diagrammet för att ändra de detaljer som visas.

* När du markerar en nod i diagrammet visas information om den noden. Markera noden igen om du vill komprimera den.

  ![nodinformation](assets/node-details.png)

* Du kan filtrera en kolumn så att endast vissa resultat visas, t.ex. inkludera och exkludera, ange villkor osv.

* Markera plustecknet (+) till vänster för att expandera en kolumn.

* Använd de högerklicksalternativ som förklaras nedan för att anpassa utdata ytterligare.

* Välj pennikonen bredvid konfigurationssammanfattningen om du vill redigera flödet ytterligare eller återskapa det med olika alternativ.

* Du kan också exportera och ytterligare analysera flödesdiagrammet som en del av ett projekts .CSV-fil genom att gå till **[!UICONTROL Project]** > **[!UICONTROL Download CSV]**.

## Filtrering

Ovanför varje kolumn visas ett filter när du håller pekaren över den. Genom att välja filtret får du samma filterdialogruta som finns i friformstabellen idag. Det här filtret fungerar på samma sätt som i frihandstabellen.

* Använd avancerade inställningar för att inkludera eller exkludera vissa villkor med vår lista över operatorer.
* När du har filtrerat ett objekt från listan återspeglas filtreringen i den kolumnen. (Filtret minskar det antingen så att bara det objekt som är tillåtet i filtret visas, eller så tas alla objekt bort utom det som du vill ha i filtret.
* Alla kolumner som är nedströms och uppströms ska finnas kvar så länge som det finns data som flödar in i de återstående noderna.
* När filterikonen har använts visas den i blått ovanför den kolumn den filtrerar.
* Om du vill ta bort ett filter väljer du filterikonen för att öppna filtermenyn. Ta bort eventuella filter som använts och markera sedan **[!UICONTROL Save]**. Flödet bör återgå till det tidigare, ofiltrerade läget.

## Alternativ för högerklick {#right-click}

| Alternativ | Beskrivning |
|--- |--- |
| [!UICONTROL Start over] | Returnerar dig till Frihand-diagramverktyget, där du kan skapa ett nytt flödesdiagram. |
| [!UICONTROL Create segment for this path] | Skapa ett segment. Då kommer du till segmentbyggaren där du kan konfigurera det nya segmentet. |
| [!UICONTROL Breakdown] | Dela upp noden efter tillgängliga Dimensioner, mått eller tid. |
| [!UICONTROL Trend] | Skapa ett trenddiagram för noden. |
| Visa nästa kolumn/Visa föregående kolumn | Visar nästa (höger) eller föregående (vänster) kolumn i visualiseringen. |
| Dölj kolumn | Döljer den markerade kolumnen från visualiseringen. |
| [!UICONTROL Expand entire column] | Expandera en kolumn om du vill visa alla noder. Som standard visas bara de fem översta noderna. |

## Exempelscenario för &#39;begränsa till första/sista förekomsten&#39;

Tänk på följande när du använder det här alternativet:

* **[!UICONTROL Limit to first/last occurrence]** räknar endast den första/sista förekomsten i serien. Alla andra förekomster av **[!UICONTROL Starts with]** eller **[!UICONTROL Ends with]** villkor ignoreras.
* Om den används med en **[!UICONTROL Starts with]** Flöde, inkluderas bara den första förekomsten som matchar startvillkoret.
* Om den används med en **[!UICONTROL Ends with]** Flöde, inkluderas endast den sista förekomsten som matchar slutvillkoret.
* Serien som används skiljer sig åt beroende på behållaren. Om du använder **[!UICONTROL Visit]** -behållaren, serien träffar blir sessionen. Om du använder **[!UICONTROL Visitor]** -behållaren kommer alla träffar för en viss användare i det angivna datumintervallet.
* The **[!UICONTROL Limit to first/last occurrence]** kan konfigureras i de avancerade inställningarna när du använder ett måttobjekt eller ett Dimension-objekt i fälten &quot;Börjar med&quot; eller &quot;Slutar med&quot;.

Exempelserie med träffar:

Hem > Produkter > Lägg till i kundvagn > Produkter > Lägg till i kundvagn > Fakturering > Orderbekräftelse

### Fundera på en flödesanalys med följande inställningar:

* Börja med[!UICONTROL  Add to cart] (Dimension)
* [!UICONTROL Page] målningsdimension
* [!UICONTROL Visit] container

If **[!UICONTROL Limit to first/last occurrence]** är *inaktiverad*, kommer den här serien träffar att räkna till två förekomster av&quot;Lägg i kundvagnen&quot;.
Förväntat flöde: &quot;Lägg i kundvagnen&quot; (2) —> &quot;Produkter&quot; (1) -> &quot;Fakturering&quot; (1)

Om **[!UICONTROL Limit to first/last occurrence]** är *aktiverad*ingår endast den första förekomsten av&quot;Lägg i varukorgen&quot; i analysen.
Förväntat flöde: &quot;Lägg i kundvagnen&quot; (1) —> &quot;Produkter&quot; (1)

### Tänk på samma serie träffar men med följande inställningar:

* Slutar med [!UICONTROL Add to cart] (Dimension)
* [!UICONTROL Page] målningsdimension
* [!UICONTROL Visit] container

If **[!UICONTROL Limit to first/last occurrence]** är *inaktiverad*, kommer den här serien träffar att räkna till två förekomster av&quot;Lägg i kundvagnen&quot;.
Förväntat flöde: &quot;Produkter&quot; (2) &lt;— &quot;Lägg i kundvagn&quot; (2)

Om **[!UICONTROL Limit to first/last occurrence]** är *aktiverad*, bara den sista förekomsten av [!UICONTROL Add to cart] skulle ingå i analysen.
Förväntat flöde: &quot;Produkter&quot; (1) &lt;— &quot;Lägg i kundvagn&quot; (1)
