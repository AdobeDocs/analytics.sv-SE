---
description: Information om mallen för datakälla .txt.
subtopic: Data sources
title: Importera filreferens
topic-fix: Developer and implementation
uuid: cc58f8d8-cb6e-4908-846f-0a41c6da805d
exl-id: 7966b156-04bf-4d39-a720-ab47a665d1e2
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 2%

---

# Importera filreferens

Information om mallen för datakälla .txt.

Använd guiden Datakällor för att generera en importmall. Importfilen för datakällor innehåller följande data:

* En nummersymbol (#) identifierar raden som en kommentar.
* Du kan lägga till ytterligare kommentarer i filen efter behov.
* En kommentar som visar mallfilens rubrik.
* En kommentar som listar de externa mått- och datamängdsnamnen som anges i [!UICONTROL Data Source Activation Wizard].

Kolumnrubriker används för att identifiera data i varje kolumn i datakällfilen. Det finns tre typer av kolumnrubriker:

**Datum**: (Obligatoriskt) En tidsstämpel för varje datarad i filen, i formatet  `m/d/yyyy`.

**Variabler**: Namnen på rapportvariablerna mappade till datakällans datamått.

**Händelser**: Namnen på händelserna mappade till datakällans mått.

Använd mallen Datakälla för att skapa en datakällfil som innehåller data som du vill överföra. Tänk på följande när du skapar en datakällfil:

* Varje rad i datakällfilen innehåller i själva verket en datapost, där varje post består av en serie tabbavgränsade fält. Kolumnrubrikerna i mallen Datakälla definierar ordningen för dessa fält. Exempel:

   ```
     #Sample data file for mycorp_report_suite 
     #Imported data for ad impressions applied to Event 6
     Date     Tracking Code      Event 6 
     1/1/2009     NYT8453A      8754
     1/1/2009     WSJ4453B      9492
     1/1/2009     BHG44563      10553
     1/2/2009     NYT8453A      6452
     1/2/2009     WSJ4453B      7237
     1/2/2009     BHG44563      9031
   ```

* Om du överför flera datafiler läser datakällor in dem i alfabetisk ordning. Filer som behöver bearbetas kronologiskt måste namnges så att deras alfabetiska ordning motsvarar deras kronologiska ordning. Exempel:

   ```
   log_2009-01-01_13:00.txt
   log_2009-01-01_13:15.txt
   log_2009-01-01_13:30.txt
   ```

* För att påskynda bearbetningen av din datakällfil rekommenderar Adobe att händelsedata samlas i en rad per datum.

   Om din datakällfil till exempel mappar och visningsdata till Event 6, skapar du en enda datarad som innehåller det totala antalet annonsvisningar för varje dag, i stället för att skapa en separat dataradspost för varje annonsintryck som inträffade en viss dag.
* Om du behöver överföra data från datum som infaller innan rapportsvitens skapandedatum, kontaktar du din Account Manager för att ändra det äldsta datum som du kan köra rapporter för.

**.FIN-fil**

När du har fyllt i datakällfilen kan du FTP-lägga den i Analytics. Det krävs dock ytterligare en fil för att dina data ska kunna behandlas. Du måste överföra en tom textfil med samma namn som datafilen, men med filnamnstillägget [!DNL .fin].

Om du till exempel överför en (tabbavgränsad) datafil med namnet [!DNL myproductdata.txt], måste du även överföra en tom textfil med namnet [!DNL myproductdata.fin]. Utan [!DNL .fin]-filen skulle data aldrig bearbetas.
