---
description: Dokumentation som beskriver hur du filtrerar och sorterar tabeller i Analysis Workspace.
title: Filtrera och sortera tabeller på frihand
feature: Freeform Tables
role: User, Admin
exl-id: 15fea9e2-f8d8-4489-9a44-e74a351b8f36
source-git-commit: 398d4ae264ce108c16a03cef086ae2614b442a2b
workflow-type: tm+mt
source-wordcount: '872'
ht-degree: 0%

---

# Filtrera och sortera tabeller på frihand

Frihandstabeller i Analysis Workspace är grunden för interaktiv dataanalys. De kan därför innehålla tusentals rader med information. Filtrering och sortering av data kan vara en viktig del av att effektivt kunna hitta den viktigaste informationen.

## Filtrera tabeller

Med filter i Analysis Workspace hittar du den viktigaste informationen.

>[!NOTE]
>
> Endast dynamiska dimensionsobjekt kan filtreras enligt beskrivningen i det här avsnittet. Statiska dimensionsobjekt kan inte filtreras. Mer information finns i [Dynamiska och statiska dimensionsobjekt i frihandstabeller](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

## Filtrera tabellrader på frihand

Du kan använda flera metoder för att filtrera rader från en frihandstabell. 

- Klicka på X i raden
- Tabellfilter
- Segmentering

Läs om hur varje metod påverkar [registersummor för frihand](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md).

### Exkludera snabbt specifika rader från en tabell

Du kan snabbt utesluta vissa rader från tabellen utan att behöva öppna filterdialogrutan.

>[!NOTE]
>
>När du utelämnar rader enligt beskrivningen i det här avsnittet, tillämpas automatiskt en [!UICONTROL **regel för att alltid utesluta objekt**] i den avancerade filterdialogrutan. (Du kan visa den tillämpade regeln genom att välja ikonen Filter och sedan [**[!UICONTROL Show advanced]**](#apply-a-simple-or-advanced-filter-to-a-table).)

Så här exkluderar du snabbt vissa rader från en friformstabell:

1. Håll pekaren över raden som du vill utesluta och välj sedan x-ikonen.

   Håll ned Skift-tangenten om du vill markera flera rader eller håll ned Kommando-tangenten (Mac) eller Ctrl-tangenten (Windows) om du vill markera flera rader.

<!--### Right-click > Delete selected rows

Note: this option does not seem to work. AN-338422

1. Select 1 or more rows. 
1. Right-click and select **[!UICONTROL Delete Selected Rows]**. 

   This action will remove the rows from the table and apply a table filter.-->

### Använda ett enkelt eller avancerat filter på en tabell

Så här filtrerar du data i frihandstabeller:

1. Håll markören över den kolumn som innehåller de data som du vill filtrera. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Välj ikonen **Filter** när den visas.

   ![Filterikon i en tabell](assets/table-filter-icon.png)

   Följande alternativ är tillgängliga:

   | Alternativ | Funktion |
   |---------|----------|
   | [!UICONTROL **Sök efter ord eller fras**] | Ange ett ord eller en fras som du vill filtrera efter. Endast rader som innehåller det angivna ordet eller den exakta frasen visas. |
   | [!UICONTROL **Inkludera ospecificerad (ingen)**] | Välj det här alternativet om du vill visa data i tabellen som inte faller inom någon av tabellens dimensioner. <!--what is this?--> |

1. (Valfritt) Om du vill filtrera efter olika villkor eller efter flera villkor väljer du [!UICONTROL **Visa avancerat**].

   Följande avancerade filteralternativ är tillgängliga:

   | Alternativ | Funktion |
   |---------|----------|
   | [!UICONTROL **Inkludera ospecificerad (ingen)**] | Välj det här alternativet om du vill visa data i tabellen som inte faller inom någon av tabellens dimensioner. <!--what is this?--> |
   | [!UICONTROL **Matcha**] | <p>Välj [!UICONTROL **Om alla villkor uppfylls**] om du bara vill visa data som uppfyller alla villkor som du anger. Det här alternativet ger vanligtvis mer förfinade data.</p> <p>Välj [!UICONTROL **Om något villkor uppfylls**] för att visa data som uppfyller något av de filtervillkor som du anger. Det här alternativet ger vanligtvis mindre förfinade data.</p> |
   | [!UICONTROL **Villkor**] | <p>Välj bland följande filteralternativ:</p><p>(Välj [!UICONTROL **Lägg till rad**] om du vill lägga till flera filtervillkor.) Det alternativ du väljer i avsnittet [!UICONTROL **Matcha**] avgör om alla eller några av villkoren du lägger till måste uppfyllas.)</p><ul><li><p>[!UICONTROL **Innehåller frasen**]: Endast data som innehåller den exakta frasen som du anger inkluderas i de filtrerade resultaten. Ord måste finnas i den ordning som anges i fältet [!UICONTROL **Sök efter ord eller fras**].<p>Det här är standardinställningen när du gör en enkel sökning.</p></p></li><li><p>[!UICONTROL **Innehåller valfri term**]: Endast data som innehåller ett eller flera ord från den fras du anger inkluderas i filtrerade resultat. </p></li><li><p>[!UICONTROL **Innehåller alla termer**]: Endast data som innehåller alla ord från frasen som du anger inkluderas i filtrerade resultat. Ord behöver inte vara i den ordning som anges i fältet [!UICONTROL **Sök efter ord eller fras**].</p></li><li><p>[!UICONTROL **Innehåller inte någon term**]: Endast data som inte innehåller något av orden från den fras du anger inkluderas i filtrerade resultat. </p></li><li><p>[!UICONTROL **Innehåller inte frasen**]: Endast data som inte innehåller den exakta frasen som du anger inkluderas i filtrerade resultat. Ord måste finnas i den ordning som anges i fältet [!UICONTROL **Sök efter ord eller fras**].</p></li><li><p>[!UICONTROL **Lika med**]: Endast data som exakt matchar den fras du anger inkluderas i filtrerade resultat. </p></li><li><p>[!UICONTROL **Är inte lika med**]: Endast data som inte exakt matchar frasen som du anger inkluderas i filtrerade resultat. </p></li><li><p>[!UICONTROL **Börjar med**]: Endast data som börjar med ordet eller den exakta frasen som du anger inkluderas i filtrerade resultat. </p></li><li><p>[!UICONTROL **Slutar med**]: Endast data som slutar med ordet eller den exakta frasen som du anger inkluderas i filtrerade resultat. </p></li></ul> |
   | [!UICONTROL **Uteslut alltid objekt**] | Ange namnet på alla objekt som du vill utesluta från filtrerade data. |

1. Välj [!UICONTROL **Använd**] om du vill filtrera data.

   Den **filtrerade tabellen** med ikonen ![ Filter ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) blir blå när ett filter tillämpas på tabellen.

### Segmentering

Mer information finns i [Segmenteringsdokumentationen](/help/components/segmentation/seg-home.md).

## Sortera tabeller

Du kan sortera data i en frihandstabell efter en kolumn i Analysis Workspace som är ett mätvärde.

En nedpilsikon ![Nedåtpilsikon, sorterad tabellkolumn](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg), visas i kolumnrubriken som data sorteras efter.

Så här sorterar du data i en frihandstabell efter en viss kolumn:

1. Håll pekaren över kolumnrubriken som du vill sortera data efter.

2. Välj nedpilen när den visas.

   ![Ikonen med nedpil (sorterad tabellkolumn)](assets/table-sort.png)

   Tabelldata sorteras efter den markerade kolumnen.
