---
title: Konsolideringsprocess för klassificeringsuppsättning
description: Hela processen med att konsolidera klassificeringsuppsättningar.
source-git-commit: 496b4891d447ed9dd091a6498a792146a2d5aceb
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---

# Konsolideringsprocess för klassificeringsuppsättning

Använd det här gränssnittet för att skapa en konsolidering av klassificeringsuppsättningar från början till slut.

## Skapande

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Consolidations]** > **[!UICONTROL Add]**

Följande fält är tillgängliga när du skapar en konsolidering:

* **[!UICONTROL Name]**: Konsolideringens namn.
* **[!UICONTROL Notify of issues]**: En kommaavgränsad lista med e-postadresser som har informerats om problem med den här konsolideringen.
* **[!UICONTROL Dataset to match]**: En nedrullningsbar lista med alla klassificeringsuppsättningar.

När du har valt en klassificeringsuppsättning visas en tabell med två kolumner:

* Den högra kolumnen innehåller alla klassificeringsuppsättningar som du vill konsolidera. Den börjar med den klassificeringsuppsättning som valts i listrutan ovan.
* Den vänstra kolumnen innehåller alla klassificeringsuppsättningar som kan sammanfogas med den ursprungligen valda datauppsättningen. **Scheman måste exakt matcha för att vara berättigade till konsolidering**. Om scheman inte matchar den valda klassificeringsuppsättningen visas de inte i den vänstra kolumnen.

Dra de önskade klassificeringsuppsättningarna från den tillgängliga kolumnen till vänster till konsolideringskolumnen till höger. När konsolideringen har fått ett namn och två eller flera klassificeringsuppsättningar finns i den högra kolumnen klickar du på **[!UICONTROL Save & Continue]**.

## Validering

När du har skapat en konsolidering visas en lista med källdatauppsättningar till höger. The **[!UICONTROL Validate]** kontrollerar att varje enskild klassificeringsuppsättning är giltig för denna konsolidering. Du kan ändra ordningen på klassificeringsstegen här för att bestämma prioritet i fall av felmatchade klassificeringsvärden. **Den högsta klassificeringsuppsättningen i listan skriver över värden som inte matchar i andra klassificeringsuppsättningar.**

## Kör

När en konsolidering har validerats kan du köra den. När du kör en konsolidering visas en likhetsrapport med följande tabellkolumner:

* **[!UICONTROL Dataset name]**: Klassificeringsuppsättningens namn.
* **[!UICONTROL Mismatch]**: Procentandelen rader där nyckelvärden inte matchade källklassificeringsuppsättningen. Om felmatchningsprocenten är hög är det möjligt att klassificeringsdata är för olika. Kontrollera att de valda klassificeringsuppsättningarna har liknande klassificeringsdata.
* **[!UICONTROL Absent]**: Procentandelen rader där nyckelvärden fanns i den klassificeringen men inte i källklassificeringen. Alla rader som inte finns läggs till i den konsoliderade klassificeringsuppsättningen.

## Godkänn

Fungerar som ett sista anrop innan de enskilda klassificeringsuppsättningarna tas bort och en konsoliderad klassificeringsuppsättning skapas. Kontrollera att allt är korrekt och klicka sedan på **[!UICONTROL Approve]**.

När den har godkänts skapas den konsoliderade klassificeringsuppsättningen. Statusen är inställd på [!UICONTROL Complete]och inga ytterligare åtgärder krävs för konsolideringen.
