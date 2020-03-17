---
description: Ranknings- och villkorsstyrda filter som du konfigurerar med hjälp av boolesk logik med AND/OR-sökuttryck.
title: Mest populära filtrering
topic: Report builder
uuid: 558fa592-41be-4e66-8705-81262afe1fc7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Mest populära filtrering

Ranknings- och villkorsstyrda filter som du konfigurerar med hjälp av boolesk logik med AND/OR-sökuttryck.

De flesta populära filter är uttrycksfilter som du konfigurerar med hjälp av boolesk logik med AND/OR-villkor, till exempel [!UICONTROL Page does not contain]*`<product name>`* med villkor eller grupper med villkor som [!UICONTROL Includes All], [!UICONTROL Includes Any]eller [!UICONTROL Excludes All]. Du kan [spara](/help/analyze/report-builder/layout/c-filter-dimensions/saved-filters.md) dessa uttryck för andra förfrågningar i den här arbetsboken eller i andra arbetsböcker.

**Skapa ett mest populärt filter**

1. Skapa eller redigera en förfrågan och fortsätt till [!UICONTROL Request Wizard: Step 2].

   ![Steginformation](assets/dimension_filter.png)

1. Klicka på länken [!UICONTROL Request Wizard: Step 2]bredvid dimensionen i rutnätet och välj sedan **[!UICONTROL Filter]**.
1. Aktivera [!UICONTROL Choose Page] och konfigurera sedan följande alternativ i **[!UICONTROL Most Popular]** formuläret:

   **Startram:** Startrangordningen för en dimension. Standardrangordningen 1 anger den översta posten i listan över rapporterade data. För dimensionen [!UICONTROL Page]indikerar till exempel startmarkeringen 1 den mest begärda sidan på din plats. Du kan ange 10 eller ett annat värde som inledande rankningscell, vilket skapar en rapport som börjar med 10 som högst. Måtten ordnas i fallande ordning, så att radobjekt med störst aktivitet rapporteras först i listan. Om du behöver fler än 50 000 sidnamn i en begäran, men har tusentals sidor att rapportera på, kan du kopiera begäran och ändra startordningen för att hämta rätt data i block om 50 000.

   **Antal poster:** ( [!UICONTROL Pivot Layout] endast) Definierar hur många artiklar som rapporteras för ett visst mätvärde över ett datumintervall. Vissa mätvärden kan visa hundra poster för ett mätresultat medan andra bara kan visa några få. För dimensionen [!UICONTROL Site Section]anger till exempel ett antal poster på 25 att rapporten visar de 25 mest besökta sidorna.

   Med pilar kan du ändra [!UICONTROL Starting Rank] och [!UICONTROL Number of Entries] för bladets första datapunkt. Som standard [!UICONTROL Starting Rank] är värdet 1 och 10 [!UICONTROL Number of Entries] . Dessa värden kan justeras från minst ett till högst 50 000 för vissa mätvärden. Varje mätvärde har ett eget tak på [!UICONTROL Number of Entries]. Inga negativa värden eller noll tillåts i dessa fält. Om du väljer [!UICONTROL Starting Rank] som 15 och [!UICONTROL Number of Entries] som 10 returnerar dataförfrågningar för måttet de tio mest besökta sidorna, där den första besökta sidan är nummer 15 i listan för det angivna datumintervallet. Alla de mest önskade sidorna, rankade 15 till 25, listas i fallande ordning.

   >[!NOTE]
   >
   >Om du använder filter på befintliga begäranden ändras de data som visas. Anta att du har mappat de tio översta [!UICONTROL Pages] till cellerna $A$1 till $A$10, med 1 för [!UICONTROL Starting Rank] och 10 för [!UICONTROL Number of Entries]. Om du ändrar dessa värden så att de visar 1 för [!UICONTROL Starting Rank] och endast 3 för [!UICONTROL Number of Entries], visas inte längre de data som tidigare fyllde i cellerna $A$4 till $A$10.

1. Om du vill skapa ett sökuttryck klickar du på **[!UICONTROL Add]**.

   ![Steginformation](assets/expressions_define_filter.png)

1. Konfigurera de villkor som passar dina behov i [!UICONTROL Define Filter] formuläret.

   ![select_cell_icon.png](assets/select_cell_icon.png): Gör att du kan hitta ett villkor som definieras i värdet för en cell.

   **Lägg till villkor:** Lägger till ett villkor i uttrycket. Det finns ingen gräns för hur många villkor du kan lägga till.

1. Klicka på **[!UICONTROL OK]**.

   ![Steginformation](assets/choose_page_02.png)

1. Klicka på i [!UICONTROL Choose Page] formuläret **[!UICONTROL Save]** för att spara uttrycket.
1. Klicka på **[!UICONTROL OK]**.
