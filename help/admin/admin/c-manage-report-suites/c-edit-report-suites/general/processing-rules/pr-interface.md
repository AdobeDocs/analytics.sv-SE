---
title: Bearbetar regelgränssnitt
description: Navigera i gränssnittet för att skapa, redigera eller ta bort bearbetningsregler.
feature: Processing Rules
role: Admin
source-git-commit: c2adf6d2e328378332cc290ba2dfd75ee6587ef6
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 0%

---

# Bearbetar regelgränssnitt

Med bearbetningsregelgränssnittet kan du skapa, redigera eller ta bort bearbetningsregler.

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Välj rapportserie > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Processing rules]**

>[!WARNING]
>
>Bearbetning av regler påverkar direkt datainsamlingen och kan orsaka dataförlust om de används felaktigt. Testa alltid bearbetningsregler i en utvecklingsrapportsserie innan du aktiverar dem i en produktionsrapportsserie för att minska problem med datakvaliteten.

## Övergripande struktur

Gränssnittet innehåller två huvudkomponenter:

* **[!UICONTROL Processing order]**: Regler körs exakt i den ordning som du har angett, med början i regel 1. Varje träff går igenom alla regler; det finns inga tidiga villkor. Se till att villkoren för varje bearbetningsregel passar för varje träff som skickas till rapportsviten.
* **[!UICONTROL Rule sets]**: Definitionerna för alla bearbetningsregler.

Du kan ha upp till 150 bearbetningsregler och upp till 30 villkor per bearbetningsregel. Det finns ingen rimlig gräns för antalet åtgärder per bearbetningsregel.

## Regeluppsättningsstruktur

Varje bearbetningsregel innehåller följande avsnitt:

* **Regelrubrik**: Regelns etikett. Det påverkar inte logiken för bearbetningsregler, men är värdefullt för att hålla reda på vad regeln gör.
* **Villkor**: Visas som texten [!UICONTROL If any/all of the following are true]. Om du inte inkluderar ett villkor körs regeln alltid vid varje träff.
* **Åtgärd**: Om det inte finns något villkor visas texten som [!UICONTROL Always execute]. Om det finns ett villkor visas texten som [!UICONTROL Then do the following]. Om ovanstående villkor utvärderas till `true` kan alla åtgärder som anges i det här avsnittet köras. Förutom en regel kan du _även_ koppla villkor till enskilda åtgärder. Följande åtgärder är tillgängliga:
   * **[!UICONTROL Overwrite value of]**: Skriver över den önskade variabeln med en annan variabel, ett statiskt värde eller ett sammanfogat värde.
   * **[!UICONTROL Delete value of]**: Tar bort det önskade variabelvärdet för träffen.
   * **[!UICONTROL Set event]**: Startar den önskade händelsen. Vanligtvis ställer du in händelser på ett anpassat värde på `1`. Det går också att ställa in händelser på andra värden än `1` eller till och med att ställa in dem på värden som angetts i kontextdatavariabler.
* **Annars åtgärd**: Om det finns ett villkor visas det här avsnittet som [!UICONTROL Otherwise do the following]. Om ovanstående villkor utvärderas till `false` kan alla åtgärder som anges i det här avsnittet köras. Det här avsnittet följer samma regelåtgärder som ovan, inklusive möjligheten att skriva över värden, ta bort värden och ange händelser.
* **Orsak**: Spela in vem som begärde regeln och vad den är beroende av. Det påverkar inte logiken för bearbetningsregler, men är värdefullt för att hålla reda på varför regeln finns.

I [Dimensioner och mätvärden som är tillgängliga för bearbetningsregler](pr-variables.md) finns en omfattande lista med variabler som du kan använda i det här gränssnittet.

* Alla variabler som tillåter &quot;Läs&quot; kan användas i ett villkor.
* Alla variabler som tillåter &quot;Write&quot; kan användas i en åtgärd.
