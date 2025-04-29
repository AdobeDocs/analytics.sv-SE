---
title: Konsolideringsprocess för klassificeringsuppsättning
description: Hela processen med att konsolidera klassificeringsuppsättningar.
exl-id: f36bcbcb-0ed0-44a7-a6a9-b28fd244fb27
feature: Classifications
source-git-commit: 828f41bf45c1954c3b68ad71a7746e24626b9eed
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 0%

---

# Konsolideringsprocess för klassificeringsuppsättning

Med klassificeringskonsolideringar kan du ta klassificeringar från flera datauppsättningar och kombinera dem till en. Använd det här gränssnittet för att skapa en konsolidering av klassificeringsuppsättningar från början till slut. Det här gränssnittet är mest värdefullt för organisationer som går från en äldre klassificeringsarkitektur till en arkitektur för klassificeringsuppsättningar. De flesta organisationer som redan är med i arkitekturen för klassificeringsuppsättningar behöver vanligtvis inte använda det här konsolideringsarbetsflödet.

## Skapande

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Consolidations]** > **[!UICONTROL Add]**

Följande fält är tillgängliga när du skapar en konsolidering:

* **[!UICONTROL Name]**: Konsolideringens namn.
* **[!UICONTROL Notify of issues]**: En kommaavgränsad lista med e-postadresser som har meddelats om problem med den här konsolideringen.
* **[!UICONTROL Dataset to match]**: En nedrullningsbar lista med alla klassificeringsuppsättningar.

När du har valt en klassificeringsuppsättning visas en tabell med två kolumner:

* Den högra kolumnen innehåller alla klassificeringsuppsättningar som du vill konsolidera. Den börjar med den klassificeringsuppsättning som valts i listrutan ovan.
* Den vänstra kolumnen innehåller alla klassificeringsuppsättningar som kan sammanfogas med den ursprungligen valda datauppsättningen. **Scheman måste matcha exakt för att vara berättigade till konsolidering**. Om scheman inte matchar den valda klassificeringsuppsättningen visas de inte i den vänstra kolumnen.

Dra de önskade klassificeringsuppsättningarna från den tillgängliga kolumnen till vänster till konsolideringskolumnen till höger. När konsolideringen har fått ett namn och två eller flera klassificeringsuppsättningar finns i den högra kolumnen klickar du på **[!UICONTROL Save & Continue]**.

## Validering

När du har skapat en konsolidering visas en lista med källdatauppsättningar till höger. Knappen **[!UICONTROL Validate]** kontrollerar att varje enskild klassificeringsuppsättning är giltig för den här konsolideringen. Du kan ändra ordningen på klassificeringsstegen här för att bestämma prioritet i fall av felmatchade klassificeringsvärden. **Den högsta klassificeringsuppsättningen i listan skriver över värden som inte matchar i andra klassificeringsuppsättningar.**

## Kör

När en konsolidering har validerats kan du köra den. När du kör en konsolidering visas en likhetsrapport med följande tabellkolumner:

* **[!UICONTROL Dataset name]**: Namnet på klassificeringsuppsättningen.
* **[!UICONTROL Mismatch]**: Procentandelen rader där nyckelvärden inte matchade källklassificeringsuppsättningen. Om felmatchningsprocenten är hög är det möjligt att klassificeringsdata är för olika. Kontrollera att de valda klassificeringsuppsättningarna har liknande klassificeringsdata.
* **[!UICONTROL Absent]**: Procentandelen rader där nyckelvärden fanns i den klassificeringsuppsättningen men inte i källklassificeringsuppsättningen. Alla rader som inte finns läggs till i den konsoliderade klassificeringsuppsättningen.

## Godkänn

Sista anropet innan enskilda klassificeringsuppsättningar togs bort och ersattes med en konsoliderad klassificeringsuppsättning. Verifiera att allt är korrekt och välj sedan **[!UICONTROL Approve]**.

När den har godkänts skapas den konsoliderade klassificeringsuppsättningen. Statusen är inställd på [!UICONTROL Complete] och ingen ytterligare åtgärd krävs för konsolideringen.
