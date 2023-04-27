---
description: Dokumentation som beskriver hur du filtrerar och sorterar tabeller i Analysis Workspace.
title: Filtrera och sortera tabeller
feature: Freeform Tables
role: User, Admin
exl-id: 15fea9e2-f8d8-4489-9a44-e74a351b8f36
source-git-commit: c546058b83be79f4ffb94811727a12b30dd14033
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 0%

---

# Filtrera och sortera tabeller

Frihandstabeller i Analysis Workspace är grunden för interaktiv dataanalys. De kan därför innehålla tusentals rader med information. Filtrering och sortering av data kan vara en viktig del av att effektivt kunna hitta den viktigaste informationen.

## Filtrera tabeller

Med filter i Analysis Workspace hittar du den viktigaste informationen.

>[!NOTE]
>
> Endast dynamiska dimensionsobjekt kan filtreras enligt beskrivningen i det här avsnittet. Statiska dimensionsobjekt kan inte filtreras. Mer information finns i [Dynamiska jämfört med statiska dimensionsobjekt i frihandstabeller](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

Så här filtrerar du data i frihandstabeller:

1. Håll markören över den kolumn som innehåller de data som du vill filtrera i en friformstabell. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Välj **Filter** -ikonen när den visas.

   ![Filterikon i en tabell](assets/table-filter-icon.png)

1. I [!UICONTROL **Sök efter ord eller fras**] anger du ett ord eller en fras som du vill filtrera efter. Endast rader som innehåller det angivna ordet eller den exakta frasen visas.

1. (Valfritt) Om du vill filtrera efter olika villkor eller efter flera villkor väljer du [!UICONTROL **Visa avancerat**].

   Följande alternativ är tillgängliga

   | Alternativ |  -funktion |
   |---------|----------|
   | [!UICONTROL **Inkludera ospecificerad (ingen)**] | Välj det här alternativet om du vill visa data i tabellen som inte faller inom någon av tabellens dimensioner. <!--what is this?--> |
   | [!UICONTROL **Matcha**] | <p>Välj [!UICONTROL **Om alla villkor är uppfyllda**] om du bara vill visa data som uppfyller alla villkor som du anger. Det här alternativet ger vanligtvis mer förfinade data.</p> <p>Välj [!UICONTROL **Om något villkor uppfylls**] om du vill visa data som uppfyller något av de filtervillkor som du anger. Det här alternativet ger vanligtvis mindre förfinade data.</p> |
   | [!UICONTROL **Kriterier**] | <p>Välj bland följande filteralternativ:</p><p>(Välj [!UICONTROL **Lägg till rad**] om du vill lägga till flera filtervillkor. Det alternativ du väljer i dialogrutan [!UICONTROL **Matcha**] -avsnittet avgör om alla eller några av villkoren som du lägger till måste uppfyllas.)</p><ul><li><p>[!UICONTROL **Innehåller frasen**]: Endast data som innehåller den exakta frasen som du anger inkluderas i de filtrerade resultaten. Orden måste vara i den ordning som anges i [!UICONTROL **Sök efter ord- eller frasfält**].<p>Det här är standardinställningen när du gör en enkel sökning.</p></p></li><li><p>[!UICONTROL **Innehåller alla termer**]: Endast data som innehåller ett eller flera ord från den fras du anger inkluderas i de filtrerade resultaten. </p></li><li><p>[!UICONTROL **Innehåller alla termer**]: Endast data som innehåller alla ord från den fras du anger inkluderas i de filtrerade resultaten. Orden behöver inte vara i den ordning som anges i [!UICONTROL **Sök efter ord- eller frasfält**].</p></li><li><p>[!UICONTROL **Innehåller inga termer**]: Endast data som inte innehåller något av orden från den fras du anger inkluderas i de filtrerade resultaten. </p></li><li><p>[!UICONTROL **Innehåller inte frasen**]: Endast data som inte innehåller den exakta frasen som du anger inkluderas i de filtrerade resultaten. Orden måste vara i den ordning som anges i [!UICONTROL **Sök efter ord- eller frasfält**].</p></li><li><p>[!UICONTROL **Lika med**]: Endast data som exakt matchar den fras du anger inkluderas i de filtrerade resultaten. </p></li><li><p>[!UICONTROL **Är inte lika med**]: Endast data som inte exakt matchar den fras du anger inkluderas i de filtrerade resultaten. </p></li><li><p>[!UICONTROL **Börjar med**]: Endast data som börjar med ordet eller den exakta frasen som du anger inkluderas i de filtrerade resultaten. </p></li><li><p>[!UICONTROL **Slutar med**]: Endast data som slutar med ordet eller den exakta frasen som du anger inkluderas i de filtrerade resultaten. </p></li></ul> |
   | [!UICONTROL **Uteslut alltid objekt**] | Ange namnet på alla objekt som du vill utesluta från filtrerade data. |

1. Välj [!UICONTROL **Använd**] för att filtrera data.

   The **Filter** icon ![Filtrerad tabell med blå filterikon](assets/table-filter-blue-icon.png) blir blå när ett filter används i tabellen.

## Sortera tabeller

Du kan sortera data i en frihandstabell efter en valfri kolumn i Analysis Workspace som är ett mått.

En nedåtpil ![Ikonen nedpil, sorterad tabellkolumn](assets/table-sort-arrow-icon.png) är synlig i kolumnrubriken som data sorteras efter.

Så här sorterar du data i en frihandstabell efter en viss kolumn:

1. Håll pekaren över kolumnrubriken som du vill sortera data efter.

1. Välj nedpilen när den visas.

   ![Ikonen nedpil, sorterad tabellkolumn](assets/table-sort.png)

   Tabelldata sorteras efter den markerade kolumnen.
