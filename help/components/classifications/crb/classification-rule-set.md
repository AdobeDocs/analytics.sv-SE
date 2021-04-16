---
description: En regeluppsättning är en grupp klassificeringsregler för en specifik variabel. Du använder en variabel för regeluppsättningen. Om du vill skapa flera regeluppsättningar för en variabel måste du tillämpa varje regeluppsättning på flera rapportsviter.
subtopic: Classifications
title: Uppsättningar med klassificeringsregler
feature: Administratörsverktyg
uuid: c4d7b77c-fa98-44be-955f-9aee7f73480b
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 3%

---


# Uppsättningar med klassificeringsregler

En regeluppsättning är en grupp klassificeringsregler för en specifik variabel. Du använder en variabel för regeluppsättningen. Om du vill skapa flera regeluppsättningar för en variabel måste du tillämpa varje regeluppsättning på flera rapportsviter.

## Skapandesida för klassificeringsregel {#section_C60B0888C76D49C596EF19F11808B718}

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]**

Följande fält och alternativ är tillgängliga på [!UICONTROL Classifications Rule Builder].

<table id="table_A5D92409969747E39E041216A5AA32CD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><a href="/help/components/classifications/crb/classification-rule-set.md"  > Lägg till regeluppsättning</a> </p> </td> 
   <td colname="col2"> <p>Skapar en regeluppsättning. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Regler </p> </td> 
   <td colname="col2"> Visar antalet regler i uppsättningen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Status </p> </td> 
   <td colname="col2"> Visar regeluppsättningens aktivitetsstatus, till exempel Utkast eller Aktiv. Aktiva regler bearbetas dagligen och klassificeringsuppgifterna undersöks, vanligtvis en månad tillbaka. Reglerna söker automatiskt efter nya värden och överför klassificeringarna. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Senast ändrad </p> </td> 
   <td colname="col2"> Anger när regeluppsättningen redigerades. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Duplicera </p> </td> 
   <td colname="col2"> Duplicerar (kopierar) en regeluppsättning så att du kan tillämpa regeluppsättningen på en annan variabel eller på samma variabel i en annan rapportserie. </td> 
  </tr> 
 </tbody> 
</table>

## Skapa en klassificeringsregeluppsättning {#create-classification-rule-set}

Ge klassificeringsregeluppsättningen ett namn, använd variabeln och ange överskrivningsinställningar.

1. (Förutsättning) Definiera klassificeringsstrukturen i **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

   (Se [Klassificeringar](https://docs.adobe.com/content/help/en/analytics/components/classifications/c-classifications.html) i Admin Tools-hjälpen om hur du lägger till klassificeringar.)

   Variabler visas bara på panelen [!UICONTROL New Rule Set] när de har minst en klassificering definierad för den variabeln.

   Du kan skapa klassificeringar för en variabel i **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Traffic]** > **[!UICONTROL Traffic Classifications]** (eller **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Classifications]**). Markera sedan variabeln och klicka på **[!UICONTROL Add Classification]**.

1. Om du vill skapa regeluppsättningen klickar du på **[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]** > **[!UICONTROL Add Rule Set]**.

   ![](assets/new_rule_set.png)

1. Namnge regeluppsättningen och klicka sedan på **[!UICONTROL Create Rule Set]**.
1. Markera regeluppsättningen för redigering.

   ![](assets/classification_rules_page.png)

1. Klicka på **[!UICONTROL Select Report Suites and Variables]**.

   Rapportsviten och variabellistan fylls i med alla klassificerade variabler som är tillgängliga i alla rapportsviter i ditt inloggningsföretag. En enskild variabel i en rapportserie kan bara tillhöra en regeluppsättning.

   Mer information finns i *`Variable`* i definitionerna för sidan [Klassificeringsregelbyggaren](/help/components/classifications/crb/classification-rule-definitions.md).
1. Ange de rapportsviter och variabler som ska användas och klicka sedan på **[!UICONTROL Save]**.
1. Fortsätt med [att lägga till klassificeringsregler](/help/components/classifications/crb/classification-rule-set.md) i regeluppsättningen.
